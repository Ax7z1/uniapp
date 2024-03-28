<template>
	<view>
		<view v-on:click="onClick">{{title}}</view>
		<button @click="clickNum">数值：{{num}}</button>
		
		<view class="box" :style="{background: bgcolor}" @click="clickBg">
			{{random}}
		</view>
		
		<view class="block" :class="{myActive:state}" @click="clickBlock"></view>
		
		<!-- 采用三目运算符（三元表达式）的方式 -->
		<view class="block" :class="state ? 'myActive' : '' "></view> 
		
		<view class="nav">
			<view class="item" :class="navIndex == index ? 'active':'' " v-for="(item,index) in navArr" :key="item.id" 
			@click="clickNav(index)">{{item.title}}</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title:"demo2测试",
				num: 1,
				bgcolor:"#c00",
				random: 0,
				state:false,
				navArr:[
					{id:1,title:"首页"},
					{id:2,title:"介绍"},
					{id:3,title:"教程"},
					{id:4,title:"组件"}
				],
				navIndex:0
			};
		},
		methods:{
			onClick:function(){
				this.title="点击后文字变成这句话。"
			},
			clickNum(){
				this.num++;
			},
			clickBg(){
				let color="#" + String(Math.random()).substring(3,6); //随机色 #342
				console.log(color)
				this.bgcolor=color
				
				this.random = Math.ceil((Math.random() * 100) + 1);
				//Js中: Math.ceil 向上取整； Math.floor 向下取整 
			},
			clickBlock(){
				this.state =!this.state
			},
			clickNav(e){
				// console.log(e)
				this.navIndex = e
			}
		}
	}
</script>

<style lang="scss">
.box{
	width: 200rpx;
	height: 200rpx;
	background: pink;
}
.block{
	width: 300rpx;
	height: 300rpx;
	background: blue;
}
.myActive{
	width: 400rpx;
	background: hotpink;
	border-radius: 20rpx;
}
.nav{
	display: flex;
	justify-content: space-around;
	align-items: center;
	.item{
		flex:1;
		line-height: 90rpx;
		background: #ccc;
		text-align: center;
		&.active{
			background: #1AA034;
			color: #fff;
		}
	}
}
</style>
