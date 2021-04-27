<template>
	<view class="wrap">
		<view class="left">
			|
		</view>
		<view class="center">
			{{label}}
		</view>
		<view class="right">
			<text v-show="showMore">更多>></text>
			<slot></slot>
		</view>
	</view>
</template>

<script>
	export default{
		props: {
			label: "",
			showMore: {
				type: Boolean,
				default: true
			}
		}
	}
</script>

<style lang="scss" scoped>
	.wrap {
		display: flex;
		align-items: center;
		width: 100%;
		height: 92rpx;
		background: #C0C0C0;
		margin: 8rpx 0;
		.left {
			padding: 0 10rpx;
		}
		.center {
			font-weight: bold;
		}
		.right {
			margin-left: auto;
			padding-right: 8rpx;
			font-size: 28rpx;
		}
	}
</style>
