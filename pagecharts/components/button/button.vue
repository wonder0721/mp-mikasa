<template>
	<view>
		<button class="btn">{{text}}</button>
	</view>
</template>

<script>
	export default {
		name: 'redButton',
		data() {
			return {
				text: 'button'
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
.btn{
	color: red;
}
</style>
