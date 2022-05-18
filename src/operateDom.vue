<template>
 <div>
  <!-- 模板中无需使用.value，会被自动编译转换成真实数据 -->
  <div ref="box">{{ num }}</div>
 </div>
</template>
<script setup>
import { ref,nextTick ,onMounted} from "vue";
let num = ref(1);
// 需要拿取box这个元素，那么只需要定义一个名字为上方ref相同的名字即可
let box =ref(null);
// 这么拿取的话会是undefined，需要等dom渲染完成后才能拿取到，因为setup时候dom还没渲染
console.log(box.value);//undefined
nextTick(()=>{
  console.log('我是nextTIck执行');
  box.value.style.color = 'red'
//  console.log();

})
onMounted(()=>{
 console.log('我是mouted执行',box);
 console.log(box.value);
})
</script>