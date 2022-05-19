<template>
	<div class="app">
		<h3>我是App组件</h3>
		<Suspense>
			<template v-slot:default>
				<Child/>
			</template>
			<template v-slot:fallback>
				<h3>加载中.....</h3>
			</template>
		</Suspense>
	</div>
</template>

<script>
import {defineAsyncComponent} from 'vue'
const Child = defineAsyncComponent(()=>import('./components/child.vue'))
export default {
  name: '660App',
  components:{Child}

};
</script>

<style lang="scss" scoped>

</style>