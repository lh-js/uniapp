<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<button type="default" @click="test()">点击</button>
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

		},
		methods: {
			test(){
				wx.showLoading({
				  title: '加载中',
				  mask:true
				})
				wx.cloud.callFunction({
				  // 云函数名称
				  name: 'test',
				  // 传给云函数的参数
				  data: {
				    a: 1,
				    b: 2,
				  },
				})
				.then(res => {
				  console.log(res) // 3
				  wx.hideLoading()
				})
				.catch(console.error)
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
