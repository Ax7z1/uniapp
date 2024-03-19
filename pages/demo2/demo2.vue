<template>
	<view>
		<view v-on:click="onClick">{{title}}</view>
		<button @click="clickNum">数值：{{num}}</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title:"demo2测试",
				num: 1
			};
		},
		methods:{
			onClick:function(){
				this.title="点击后文字变成这句话。"
			},
			clickNum(){
				this.num++;
			}
		}
	}
</script>

<style lang="scss">

</style>
