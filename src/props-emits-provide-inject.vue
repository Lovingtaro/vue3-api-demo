<template>
  <div>
    <!-- <input type="text" v-model="state.count"> -->
    <!-- <input type="text" v-model="num"> -->
    <hello-world @sayHi="sayHi" :msg="父子组件传值演示"></hello-world>
    <inject></inject>
    <button style="width:100px;height:50px" @click="changeValue()">改变属性值</button>
  </div>
</template>

<script>
import { provide } from 'vue'
import { ref ,reactive} from 'vue'
import Inject from './components/inject.vue'
import HelloWorld from './components/HelloWorld.vue'
export default {
  name: '660Watch',
  components:{Inject,HelloWorld},
  setup(){
    let car = reactive({name:'奔驰',price:'40万'})
    provide('car',car) // 给自己的后代组件传递数据
    function sayHi(){
      console.log('子组件时间触发')
    }
    return {
      car,
      sayHi
    }
  }
};
</script>

<style lang="scss" scoped>

</style>