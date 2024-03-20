<template>
	<view>
		<view @click="onClick">标题：{{title}}</view>
		<input type="text" v-model:value="title" />
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: "测试v-model"
			};
		},
		methods:{
			onClick(){
				this.title = Math.random()
			}
		}
	}
</script>

<style lang="scss">
input{
	border: 1px,solid #ccc;
}
</style>
