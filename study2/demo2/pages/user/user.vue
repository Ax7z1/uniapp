<template>
	<view>
		<view @click="clickUser">用户信息</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			clickUser(){
				uni.removeTabBarBadge({
					index:2
				})
			}
		},
		onLoad(){
			// uni.setTabBarItem({
			// 	index:0,
			// 	text:"123123",
				
			// })
			// uni.hideTabBar()
			uni.setTabBarBadge({
				index:2,
				text:'3'
			})
			
			//小红点
			uni.showTabBarRedDot({
				index:1
			})
			
			let key= uni.getStorageSync("mykey");
			console.log(key)
		}
	}
</script>

<style lang="scss">

</style>
