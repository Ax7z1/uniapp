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
		
		<button @click="removeBtn">清楚key3</button>
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

			// uni.setStorage({
			// 	key:"demo",
			// 	data:123123,
			// 	success:res =>{
			// 		console.log(res);
			// 	}
			// })
			uni.setStorageSync('mykey1', '我的测试');
			uni.setStorageSync('mykey2', 'vue项目');
			uni.setStorageSync('mykey3', {name:'张三',age:17});
			
			
			
		},
		methods: {
			removeBtn(){
				uni.removeStorageSync("mykey1")
				// uni.clearStorage() 清楚全部数据缓存
			},
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
