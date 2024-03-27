<template>
	<view>
		<pubTitle title="我们" subtitle="about page"></pubTitle>
		<navigator url="/pages/index/index">首页</navigator>
		<navigator url="/pages/list/list">列表页</navigator>
		----------------------------------------
		<myevent title="组件间传值" @myenv="onmyenv"></myevent>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			onmyenv(e){
				console.log(e)
			}
		}
	}
</script>

<style lang="scss">

</style>
