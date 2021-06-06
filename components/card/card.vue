<template>
	<view class="cardcom">
		<van-button type="primary" class="rotate90">主要按钮</van-button>
	</view>
</template>

<script>
	export default {
		name: "card",
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss" scoped>
	.cardcom {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 200rpx;
		width: 200rpx;
		border: 1px solid #000;
		border-radius: 20rpx;
		padding: 16rpx;
		box-sizing: border-box;
		// box-shadow: 0 8px 12px #ebedf0;

		.rotate90 {
			transform: rotate(90deg);
		}
	}
</style>
