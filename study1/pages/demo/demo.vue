<template>
	<view>
		<view>当前标题：{{title}}</view>
		<view>{{num}}</view>
		<view>{{arr}}</view>
		<view>{{arr[2]}}</view>
		<view>{{obj}}</view>
		<view>{{obj.name}}</view>
		
		-----------------
		
		<view v-if="day==1">周一</view>
		<view v-else-if="day==2">周二</view>
		<view v-else-if="day==3">周三</view>
		<view v-else-if="day==4">周四</view>
		<view v-else-if="day==5">周五</view>
		<view v-else-if="day==6">周六</view>
		<view v-else-if="day==7">周日</view>
		<view v-else>格式错误</view>
		
		
		---------v-if----------
		
		
		<view v-if="state">uniapp</view>
		<View v-else>html5css3</View>
		
		
		---------v-show---------
		<view v-show="state">uniapp</view>
		<view v-show="!state">html5css3</view>	
		
		-----for------
		<view v-for="(item,index) in arr" class="out">
			<view class="row">{{(index)+1 +'-'+item}}</view>
		</view>
		
		<view class="goods" v-for="(item,index) in goods" v-bind:key="index">
			<view>商品名称：{{item.title}}  - 价格： ￥{{item.price}}</view>
		</view>
		
		------for object----
		<view v-for="(value,name,index) in obj">
			<!-- {{name +":"+value}} -->
			{{index}} - {{name}} : {{value}}
		</view>
		
		------vHtml--------
		<view>{{title}}</view>
		<view v-html="title"></view>
		------------------
		<view>{{code}}</view>
		<view v-html="code"></view>
		<h2>小程序</h2>
		
		-----v-bind------
<!-- 		<image v-bind:src="img" mode=""></image>
		<image :src="img" mode=""></image> -->
		---------------------
		
		<image :src="'../../static/images/pic'+item+'.jpg'" mode="" v-for="item in [1,2,3]"></image>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				img: "../../static/images/pic1.jpg",
				code:"<h1>测试v-Html</h1><em>uniapp</em>",
				title :'微信小程序',
				num: 123,
				arr:["aaa","bbb","uni","123"],
				obj:{name:"zhangsan",age :22},
				state: true,
				day :2,
				goods:[
					{
						id:1,
						title:"商品1",
						price:22.5,
					},{
						id:2,
						title:"商品2",
						price:99.9
					}
				]
			};
		}
	}
	
</script>

<style lang="scss">
.out{
	.row{
		font-size: 50rpx;
		border-bottom: 1px solid #ccc;
	}
}
</style>
