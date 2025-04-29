<template>
	<div class="person">
		<p>姓名：{{ name }}</p>
		<button @click="changeName">修改名字</button>
		<p>性别：{{ sex }}</p>
		<button @click="showSex">显示性别</button>
		<p>年龄：{{ age }}</p>
		<button @click="changeAge">修改年龄</button>
		<p>电话：{{ tel }}</p>
		<button @click="showTel">显示电话</button>
		{{ sum }}
	</div>
</template>

<script lang="ts" setup>
import { ref, reactive, toRefs } from 'vue'

let obj = reactive({
	name: '张三',
	sex: '保密',
	age: 18,
	tel: '',
})
let sum = ref(0)
console.log(sum)
const changeName = () => {
	obj.name = '李四'
}
const showSex = () => {
	obj.sex = '武装直升机'
	// Object.assign(obj, { sex: '沃尔玛购物袋' })

	console.log('obj', obj)
}
const changeAge = () => {
	obj.age += 1
}
const showTel = () => {
	obj.tel = '12345678901'
}

const { name, sex, age, tel } = toRefs(obj)
</script>

<style scoped>
.person {
	color: green;
	font-size: 16px;
}
</style>
