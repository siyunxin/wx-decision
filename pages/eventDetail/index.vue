<template>
	<view class="eventdetail">
		<u-cell-group>
			<u-cell-item title="事件编号" value="1001"></u-cell-item>
			<u-cell-item title="事件来源" value="发布中心"></u-cell-item>
			<u-cell-item title="事件类别" value="A"></u-cell-item>
			<u-cell-item title="事件名称" value="维修暖气"></u-cell-item>
			<u-cell-item title="事件事件" value="2021-4-26"></u-cell-item>
			<u-cell-item title="所属街道" value="XXX街道"></u-cell-item>
			<u-cell-item title="发生地点" value="XXX楼xxx号"></u-cell-item>
			<u-cell-item title="事件概述" value="维修暖气,维修暖气"></u-cell-item>
		</u-cell-group>
		<view class="eventstep">
			
		</view>
		<view class="eventoperation">
			<button class="event-button" @click="eventOperation">参与处置</button>
		</view>
		<evaluate v-show="evaluateShow" @closeEvaluate="closeEvaluate"></evaluate>
	</view>
</template>

<script>
	import Evaluate from '@/components/Evaluate/index.vue'
	export default {
		name: "event-detail",
		components: {
			Evaluate
		},
		data() {
			return {
				evaluateShow: false
			}
		},
		methods:{
			eventOperation() {
				console.log("事件")
				this.evaluateShow = true
			},
			closeEvaluate() {
				this.evaluateShow = false
			}
		}
	}
</script>

<style lang="scss" scoped>
	.event-button {
		width: 60%;
		background: #007AFF;
		color: #fff;
		margin: 30rpx auto;
		font-size: 28rpx;
	}
</style>
