<template>
  <div>
    <input type="text" v-model="state.count">
    <!-- <input type="text" v-model="num"> -->
    <button style="width:100px;height:50px" @click="changeValue()">改变属性值</button>
  </div>
</template>

<script>
import { ref ,watch,reactive} from 'vue'
export default {
  name: '660Watch',
  setup(){
  //  const state = reactive({count: 1});

  // //侦听一个reactive定义的数据,修改count值时会触发 watch的回调
  //   watch(()=>state.count,(newCount,oldCount)=>{
  //     console.log('newCount:',newCount);  
  //     console.log('oldCount:',oldCount);
  //   })
  //   //侦听一个ref
  //   const num = ref(0);
  //   // 多个数据监听
  //   watch([()=>state.count,num],([newCount,newNum],[oldCount,oldNum])=>{
  //     console.log('new:',newCount,newNum);
  //     console.log('old:',oldCount,oldNum);
  //   })
// 多层数据
  const state = reactive({
    person: {
      name: '张三',
      fav: ['帅哥','美女','音乐']
    },
  });
  watch(
    () => state.person,
    (newType, oldType) => {
      console.log("新值:", newType, "老值:", oldType);
    },
    { deep: true,immediate:true}
  );
   function changeValue(){
    state.person.name = '李四'
    console.log('state.person.name', state.person.name);
  }
    return {
      state,
      changeValue
      // num
    }
  }

};
</script>

<style lang="scss" scoped>

</style>