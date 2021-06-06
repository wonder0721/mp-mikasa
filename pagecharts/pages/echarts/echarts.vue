<template>
	<view class="content">
		<van-button @click="showChart">{{title}}</van-button>
		<van-button @click="updateChart">updateChart</van-button>
		<view class="charts-wrapper">
			<ec-canvas id="mychart" canvas-id="mychart" :ec="ec"></ec-canvas>
		</view>
	</view>
</template>

<script>
	import * as option from './option.js'
	let chart = null
	let defaultOption = option.default
	function initChart(echarts, canvas, width, height, dpr) {
		chart = echarts.init(canvas, null, {
			width: width,
			height: height,
			devicePixelRatio: dpr // 像素
		});
		canvas.setChart(chart);
		chart.setOption(defaultOption);
		return chart;
	}

	export default {
		data() {
			return {
				title: 'showChart',
				ec: {
					// onInit: initChart,
					lazyLoad: true
				},
				ecComponent: null
			}
		},
		methods: {
			showChart() {
				this.ecComponent.init(initChart)
			},
			updateChart(){
				defaultOption.series.forEach(v => {
					v.data.reverse()
				})
				this.showChart()
			}
		},
		onReady() {
			this.ecComponent = this.selectComponent('#mychart');
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		height: 100vh;
		background-color: #fff;

		.charts-wrapper {
			height: 500rpx;
			width: 100%;
		}
	}
</style>
