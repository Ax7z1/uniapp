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
				title: 'Hello',
				arr : ["三国演义", "西游记", "红楼梦", "水浒传"]
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
				// uni.showModal({
				// 	title:"手机验证",
				// 	editable:true,
				// 	placeholderText:"请输入手机号",
					
				// 	success:res=>{
				// 		console.log(res)
						
				// 	}
				// });
				
				// success方法不是箭头函数，所以里面的this指的是方法对象，而不是vm对象
				// 解决方法一：外面定义一个that=this 
				// let that = this
				// uni.showActionSheet({
				// 	itemList: this.arr,
				// 	success: function (res) {
				// 		console.log(res);
				// 		// console.log('选中了第' + (res.tapIndex + 1) + '个按钮');
				// 		console.log(that.arr[res.tapIndex]);
				// 	}
				// });
				
				// 解决方法二：使用箭头函数
				uni.showActionSheet({
					title: "-名著选择-",
					itemList: this.arr,
					success: (res)=>{
						console.log(this.arr[res.tapIndex])
					}
				});
				
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
