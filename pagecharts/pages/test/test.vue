<template>
	<view class="test">
		<van-button type="primary">测试分包页面</van-button>
		<card class="card"></card>
		<red-button></red-button>
	</view>
</template>

<script>
	import redButton from '../../components/button/button.vue'
	export default {
		components: {
			redButton
		},
		data() {
			return {

			};
		}
	}
</script>

<style lang="scss" scoped>
	.test {
		/deep/ .card {
			display: flex;
			margin-top: 30rpx;

			.van-button {
				transform: rotate(90deg);
			}
		}
	}
</style>
