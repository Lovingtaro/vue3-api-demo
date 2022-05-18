<template>
  <div>
    <h1>{{name}}</h1>
  </div>
</template>

<script>
import { reactive,toRefs,toRef } from 'vue'
export default {
  name: '660ToRefToRefs',
  setup(){
    //数据
			let person = reactive({
				name:'张三',
				age:18,
				job:{
					j1:{
						salary:20
					}
				}
			})

			// const name1 = person.name
			// console.log('%%%',name1)

			// const name2 = toRef(person,'name')
			// console.log('####',name2)

			const x = toRefs(person)
			console.log('******',x)

			return {
				person,
				name:toRef(person,'name'),
				age:toRef(person,'age'),
				salary:toRef(person.job.j1,'salary'),
				...toRefs(person)
			}

}

};
</script>

<style lang="scss" scoped>

</style>