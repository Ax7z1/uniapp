<template>
	<view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		onLoad(){
			// uni.setNavigationBarTitle({
			// 	title: 'js操作的title'
			// });
			// uni.setNavigationBarColor({
			//     frontColor: '#ffffff',  // 必须6位
			//     backgroundColor: '#1AA034',
			//     animation: {
			//         duration: 400,
			//         timingFunc: 'easeIn'
			//     }
			// })

			uni.showNavigationBarLoading();
			
			setTimeout(()=>{
				uni.hideNavigationBarLoading();
				
			},1500)
		}
	}
</script>

<style lang="scss">

</style>
