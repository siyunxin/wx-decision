<template>
	<view class="comprehensive">
		<label-cell :label="'水电热'" :showMore="false"></label-cell>
		<view class="wrap">
			<view>
				<mpvue-echarts id="main" ref="mapChart" :echarts="echarts" @onInit="echartsRender" />
			</view>
			<view></view>
			<view></view>
		</view>
		<label-cell :label="'基础设施'" :showMore="false"></label-cell>
		<view class="wrap">
			<view></view>
			<view></view>
			<view></view>
		</view>
		<label-cell :label="'气象监测'" :showMore="false"></label-cell>
		<view class="wrap">
			<view></view>
			<view></view> 
			<view></view>
		</view>
	</view>
</template>

<script>
	import LabelCell from '@/components/LabelCell/index.vue'
	import * as echarts from '@/common/echarts.min';
	import mpvueEcharts from '@/components/mpVueEcharts/echarts.vue';
	export default {

		components: {
			LabelCell,
			mpvueEcharts
		},
		data() {
			return {
				echarts
			}
		},
		methods: {
			echartsRender() {
				var option = {
					tooltip: {
						trigger: 'item'
					},
					legend: {
						top: '5%',
						left: 'center'
					},
					series: [{
						name: '访问来源',
						type: 'pie',
						radius: ['40%', '70%'],
						avoidLabelOverlap: false,
						itemStyle: {
							borderRadius: 10,
							borderColor: '#fff',
							borderWidth: 2
						},
						label: {
							show: false,
							position: 'center'
						},
						emphasis: {
							label: {
								show: true,
								fontSize: '40',
								fontWeight: 'bold'
							}
						},
						labelLine: {
							show: false
						},
						data: [{
								value: 1048,
								name: '搜索引擎'
							},
							{
								value: 735,
								name: '直接访问'
							},
							{
								value: 580,
								name: '邮件营销'
							},
							{
								value: 484,
								name: '联盟广告'
							},
							{
								value: 300,
								name: '视频广告'
							}
						]
					}]
				};
				// console.log(echarts)
				// console.log(this.echarts)
				// this.echarts.setCanvasCreator(() => canvas);
				// const chart = this.echarts.init(canvas, null, {
				// 	width: '320rpx',
				// 	height: '220rpx',
				// });
				// chart.setOption(optionMap);
				// this.$refs.mapChart.setChart(chart);
			}
		}
	}
</script>

<style lang="scss" scoped>
	.wrap {
		width: 100%;
		height: 240rpx;
		display: flex;

	}
</style>
