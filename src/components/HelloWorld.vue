<template>
  <button class="hello" @click="sayHi">
    props,emit相关
  </button>
</template>
<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  emits:['sayHi'],
  setup(props,ctx){
    function sayHi(){
      ctx.emit('sayHi','apple')
      // console.log('sayHi',props);
    }
    return {
      sayHi
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

</style>
