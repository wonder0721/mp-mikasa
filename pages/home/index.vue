<template>
	<view class="content">
		<image class="logo" src="/static/logo.png" @click="showImg"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<view class="box">
			<van-grid clickable square style="width: 100%;">
				<van-grid-item icon="https://img.yzcdn.cn/vant/logo.png" text="vant" link-type="navigateTo"
					url="/pages/vant/vant">
				</van-grid-item>
				<van-grid-item icon="/static/image/charts.png" text="echarts" link-type="navigateTo"
					url="/pagecharts/pages/echarts/echarts">
				</van-grid-item>
				<van-grid-item icon="more" text="subPackage" link-type="navigateTo"
					url="/pagecharts/pages/test/test">
				</van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
				<van-grid-item icon="question" text="question"></van-grid-item>
			</van-grid>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello uni-app'
			}
		},
		onLoad() {

		},
		methods: {
			goPage(value) {
				uni.navigateTo({
					url: `../${value}/${value}`
				})
			},
			showImg(){
				uni.getImageInfo({
					src:'/static/logo.png',
					success(res) {
						console.log(res);
						uni.previewImage({
							urls:[res.path]
						})
					}
				})
				
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
		padding: 32rpx;
	}

	.logo {
		border-radius: 50%;
		height: 200rpx;
		width: 200rpx;
		margin-top: 30rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.box {
		width: 100%;
		box-sizing: border-box;
		background-color: #f9f9f9;
		margin-top: 50rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
		border: 1rpx solid #f6f6f6;
		border-radius: 10rpx;
		overflow: hidden;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
