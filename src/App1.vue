<template>
  <h3>{{name}}</h3>
  <HelloWorld @sayHi="sayHi" msg="20220509"></HelloWorld>
  <button @click="changeName">修改内容</button>
</template>

<script>
import { ref, reactive, watch, watchEffect } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import usePoint from './hooks/usePoint'
export default {
  name: 'App',
  components:{HelloWorld},
  setup(){







    
    // let name = ref("my name is kiki");
    let name = ref({
      age:18,
      job:'programmer',
      hobby:{
        soccer:80,
        basketball:90
      }
    });
    console.log(name,'name')
    let intro = reactive({
      age:18,
      job:'programmer',
      hobby:{
        soccer:80,
        basketball:90
      }
    });
    const point = usePoint()
    console.log('point===click',point);
    
    // reactive 定义的数据自带{deep:true}
    // watch([name,intro],(newV,oldV)=>{
    //   console.log('newV',newV,oldV);
    // });
    
    // watch(intro.hobby.soccer,(newV,oldV)=>{
    //   console.log('newV',newV,oldV);
    // },{deep:true});//此处监听的是reactive对象中的某个属性，所以deep有用

    // watchEffect(() => {
    //   console.log(root.value)
    // }, 
    // {
    //   flush: 'post'
    // })
    watchEffect(()=>{
      const newName = name.value
      console.log('newName','监听的name发生变化',newName);
      
    })
    function sayHi(value){
      console.log('value',value);
    }
    function changeName(){
      intro.age++
      name.value = "my name is qiaqia";
      console.log('intro==',intro);
    }
    return {
      name,
      changeName,
      sayHi,
      watch
    }
  }
}
</script>

<style>

</style>
