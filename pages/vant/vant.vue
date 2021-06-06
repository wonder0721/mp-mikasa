<template>
	<view>
		<van-search :value="value" placeholder="请输入搜索关键词" shape="round" show-action @search="onSearch" @cancel="onCancel" />
		<van-button type="primary" @click="showpopup">弹出popup</van-button>
		<!-- <view class="test"></view> -->
		<van-popup
		  :show="show"
		  position="bottom"
			round
		  custom-style="height: 400rpx;"
		  @click-overlay="onClose"
			@after-leave="afterLeave"
		/>
		<van-toast id="van-toast" />
	</view>
</template>

<script>
	import card from '../../components/card/card.vue'
	import Toast from '../../wxcomponents/vant/toast/toast'
	export default {
		components:{
			card
		},
		data() {
			return {
				value: '',
				show: false
			}
		},
		methods: {
			onSearch() {},
			onCancel() {
				uni.navigateBack({

				})
			},
			showpopup(){
				this.show = true
			},
			onClose(){
				this.show = false
			},
			afterLeave(){
				console.log('popup leave')
				Toast('popup leave')
			}
		}
	}
</script>

<style lang="scss" scoped>
.test{
	height: 88rpx;
	width: 176rpx;
	background-color: #ff0;
}
</style>
