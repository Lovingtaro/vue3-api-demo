<template>
  <div>
    <p>{{car.name}}</p>
    <p>{{car.price}}</p>
  </div>
</template>

<script>
import { inject } from 'vue'
export default {
  name: '660Inject',
  setup(props,context){
    const car = inject('car') // 拿到祖先的数据
    console.log('car',car)
    return {car}
  }
};
</script>

<style lang="scss" scoped>

</style>