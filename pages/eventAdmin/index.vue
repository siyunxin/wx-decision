<template>
	<view>
		<u-cell-group>
				<u-cell-item icon="setting-fill" title="事件1" value="事件中心" @click="handleEvent"></u-cell-item>
				<u-cell-item icon="integral-fill" title="事件2" value="事件中心"></u-cell-item>
				<u-cell-item icon="file-text" title="事件3" value="事件中心"></u-cell-item>
				<u-cell-item icon="file-text-fill" title="事件4" value="事件中心"></u-cell-item>
				<u-cell-item icon="wifi-fill" title="事件5" value="事件中心"></u-cell-item>
				<u-cell-item icon="integral-fill" title="事件6" value="事件中心"></u-cell-item>
				<u-cell-item icon="integral-fill" title="事件7" value="事件中心"></u-cell-item>
			</u-cell-group>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			handleEvent() {
				uni.navigateTo({
					url: "/pages/eventDetail/index"
				})
			}
		}
	}
</script>

<style>
</style>
