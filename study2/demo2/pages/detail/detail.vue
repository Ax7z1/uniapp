<template>
	<view>
		<view class="detail">
			<view class="title">{{objectData.title}}</view>
			<view class="content">{{objectData.body}}</view>
		</view>

		<view class="comments">
			<view class="text">评论</view>
			<view class="row">
				<view class="top">
					<view class="name">名称</view>
					<view class="email">1111111@qq.com</view>
					</viwe>
				</view>
				<view class="body">
					评论的主体内容
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				objectData: {},
				id: 1
			};
		},
		onLoad(e) {
			console.log(e)
			this.id = e.id
			this.getDatail()
		},
		methods: {
			getDatail() {
				uni.showLoading({
					title: "数据加载中...",
					mask: true
				})
				uni.request({
					url: 'https://jsonplaceholder.typicode.com/posts/' + this.id,
					success: res => {
						console.log(res);
						this.objectData = res.data
					},
					complete() {
						uni.hideLoading()
					}
				})
			}
		}
	}
</script>

<style lang="scss">
	.detail {
		padding: 30rpx;

		.title {
			font-size: 46rpx;
			color: #000;
			padding-bottom: 20rpx;
		}

		.conten {
			font-size: 30rpx;
			color: #666;
			padding-bottom: 60rpx;
		}
	}

	.comments {
		padding: 30rpx;
		background: #f8f8f8;
		.text {
			font-size: 46rpx;
			margin-bottom: 30rpx;
		}
		.row {
			border-bottom: 1px solid #e8e8e8;
			padding: 20rpx 0;
			.top {
				display: flex;
				justify-content: space-between;
				font-size: 22rpx;
				color:#999;
				padding-bottom: 10rpx;
			}
			.body{
				font-size: 28rpx;
				color:#555;
			}
		}
	}
</style>