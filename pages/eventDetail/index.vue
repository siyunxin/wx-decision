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
			<u-steps :list="numList" :current="3"></u-steps>
		</view>
		<view class="eventoperation">
			<button class="event-button" @click="eventOperation">参与处置</button>
			<!-- <button class="event-button" @click="popupShow = true">打开弹窗</button> -->
		</view>
		<!-- <u-popup v-model="popupShow" mode="center"border-radius="10"  closeable>
			<evaluate></evaluate>
		</u-popup> -->
		<u-popup v-model="popupShow" mode="center"border-radius="10"  closeable>
			<urge-manage></urge-manage>
		</u-popup>
		
	</view>
</template>

<script>
	import Evaluate from '@/components/Evaluate/index.vue'
	import UrgeManage from '@/components/UrgeManage/index.vue'
	export default {
		name: "event-detail",
		components: {
			Evaluate,
			UrgeManage
		},
		data() {
			return {
				popupShow: false,
				evaluateShow: false,
				numList: [{
						name: ' 一'
					}, {
						name: '二'
					}, {
						name: '三'
					}, {
						name: '四'
					},
					{
						name: '五'
					},
					{
						name: '六'
					},
				],
			}
		},
		methods: {
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
