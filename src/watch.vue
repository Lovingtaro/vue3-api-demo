<template>
  <div>
    <input type="text" v-model="msg">
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: '660Watch',
  setup(){
    let msg = ref('bongbong')
    return {
      msg
    }
  }

};
</script>

<style lang="scss" scoped>

</style>