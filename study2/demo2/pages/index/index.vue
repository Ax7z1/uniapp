<template>
	<view class="content">
		<image class="logo" src="/static/logo.png" @click="clickImg"></image>
		
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		
		<view>
			<navigator url="/pages/demo/demo">跳转到demo</navigator>
		</view>
	
		<view class="box" @click="clickBox"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {
			// uni.showLoading({
			// 	title: "数据加载中..."
			// })
			
			// setTimeout(()=>{
			// 	uni.hideLoading()
			// }, 2000);
			
		},
		methods: {
			clickImg(){
				uni.showToast({
					title: "测试测试！",
					icon: "none",
					// image: "/static/logo.png",
					mask: true
				})
				
			setTimeout(function() {
				uni.navigateTo({
					url: "/pages/demo/demo"
				})
			}, 1500)
			},
			clickBox(){
				// uni.showModal({
				// 	title: "手机验证",
				//     // content:"继续进入下一页",
				// 	// showCancel: false,
				// 	// cancelText: "否",
				// 	// cancelColor: "red"
				// 	// editable: true,
				// 	// placeholderText:"请输入手机号"
				// 	success:res=>{
				// 		console.log(res);
				// 		if (res.confirm == true) {
				// 			uni.navigateTo({
				// 				url: '/pages/demo/demo',
				// 			});
				// 		} else{
				// 			uni.showToast({
				// 				title:"取消",
				// 				icon:"none"
				// 			})
				// 		}
				// 	}
				// })
				uni.showModal({
					title:"手机验证",
					editable:true,
					placeholderText:"请输入手机号",
					
					success:res=>{
						console.log(res)
						
					}
				})
			}
		}
	}
</script>

<style lang="scss">
	.box{
		height: 200rpx;
		width: 200rpx;
		background: pink;
	}
</style>
