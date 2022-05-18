<template>
  <div>
    <div>{{changeValue}}</div>
    <p>{{computeValue}}</p>
    <button @click="change">改变changeValue的值</button>
  </div>
</template>

<script setup>
import {ref,computed} from 'vue'
// export default {
  // setup(){
  // 情况1
    let changeValue = ref(0)
    let computeValue = computed(()=>{
      return changeValue.value+'hahaha'
    })
    // 上面形式的值是readOnly
    console.log("computeValue",computeValue.value++)


  // 情况2
    // let changeValue = ref(0)
    // let computeValue = computed({
    //  get(){
    //   return changeValue.value+'haha'
    //  },
    //  set(val){
    //    changeValue.value = val-1
    //  }
    // })
    // computeValue.value=1
    // console.log(computeValue.value,'可读可写计算属性')
    // function change(){
    //   changeValue.value++
    // }
  // }
</script>

<style lang="scss" scoped>

</style>