<template>
	<view class="out">
		<navigator url="/pages/demo4/demo4?wd=uniapp">跳转到demo4</navigator>
		
		<view style="width: 200rpx; height: 200rpx; background: pink;" @click="goDemo4"></view>
		
		
		<pubTitle :list="[4,5,6]" :user="{user:'张三',gender:'女'}" :time="time" :title="test" subtitle="index page"></pubTitle>
		<!-- 父向子传值 子组件通过props接收父组件传过来的值 -->
		<!-- <pub-title></pub-title> 可以把驼峰转为-横线-->
		<navigator url="/pages/list/list">新闻列表</navigator>
		<navigator url="/pages/list/list" open-type="reLaunch">新闻列表</navigator>
		<navigator url="/pages/about/about" open-type="redirect">关于我们</navigator>
		
		<navigator url="/pages/list/list">
			<image src="/static/images/pic2.jpg" mode=""></image>
		</navigator>
		
		
		<button type="primary">确认提交</button>
		<button size="mini" type="warn">确认提交</button>
		<button size="mini" type="warn" plain loading>确认提交</button>
		
		<input type="text" />
		
		<image src="/static/images/pic4.jpg" mode="" class="myimg"></image>
		<!-- <img src="/static/images/pic4.jpg" alt="" /> -->
		<image src="https://qiniu-web-assets.dcloud.net.cn/unidoc/zh/uni-app.png" mode=""></image>
		
		<view class="box"> div </view>
		<scroll-view class="scroll" scroll-x scroll-y>
			<view class="group">
				<view class="item">
					111
				</view>
				<view class="item">
					111
				</view>
				<view class="item">
					111
				</view>
				<view class="item">
					111
				</view>
				<view class="item">
					111
				</view>
			</view>
		</scroll-view>
		
		<swiper class="swiper" circular autoplay interval="3000" duration="300" indicator-dots indicator-color="rgba(255,255,255,0.5)" indicator-active-color="white">
			<swiper-item class="item">
				<image src="/static/images/pic1.jpg" mode="aspectFill"></image>
			</swiper-item>
			<swiper-item class="item">
				<image src="/static/images/pic2.jpg" mode="aspectFill"></image>
			</swiper-item>
			<swiper-item class="item">
				<image src="/static/images/pic3.jpg" mode="aspectFill"></image>
			</swiper-item>
		</swiper>
		<view style="height: 500rpx;">
			
		</view>
	</view>
</template>

<script>
	export default {
		data(){
			return {
				test: "测试",
				time:Date.now()
			}
		},
		methods:{
			goDemo4(){
				uni.navigateTo({
					url:"/pages/demo4/demo4?wd=uniapp&author=ax7z1"
				})
			}
		}
	}
</script>

<style lang="scss">
	.myimg{
		width: 260rpx;
		height: 260rpx;
	}
.out {
	.box {
		width: 200px;
		height: 200px;
		background: pink;
	}
}
.scroll{
	border: 1px solid red;
	box-sizing: border-box;
	height: 100rpx;
	.group{
		height: 220rpx;
		white-space: nowrap;
		.item{
			width: 220rpx;
			height: 220rpx;
			background: royalblue;
			display: inline-block;
			margin-right: 10rpx;
		}
	}
}
.swiper{
	height: 350rpx;
	margin-top: 100rpx;
	.item{
		padding: 20rpx;
		box-sizing: border-box;
		image{
			width: 100%;
			height: 350rpx;
		}
	}
}
</style>