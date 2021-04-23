//单条新闻
<template>
	<view class="news">
		<view class="news-image">
			<image :src="newsInfo.img" style="width: 100%;"></image>
		</view>
		<view class="news-info">
			<view class="text">{{newsInfo.text}}</view>
			<view class="bottom">
				<view class="source">
					{{newsInfo.source}}
				</view>
				<view class="browse">
					<icon type="success" size="14"></icon>
					<text class="browse-count">{{newsInfo.browseCount}}</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: "news-item",
		props:{
			newsInfo: {
				type: Object,
				require: true
			}
		},
		data() {
			return {
				
			}
		},
		methods:{
			
		}
	}
</script>

<style lang="scss" scoped>
	$textSize: 32rpx;
	$operationSize: 28rpx;
	$operationColor: #999999;
	.news {
		display: flex;
		width: 100%;
		height: 92px;
		padding: 6rpx 8rpx;
		// border: 1rpx solid yellow;
		.news-image {
			width: 240rpx;
			height: 180rpx;
			// border: 1rpx solid red;
			
			image {
				width: 100%;
				height: 100%;
			}
		}
		.news-info {
			flex: 1;
			height: 100%;
			display: flex;
			flex-direction: column;
			.text {
				height: 130rpx;
				padding: 4rpx 8rpx;
				font-size: $textSize;
			}
			.bottom {
				display: flex;
				justify-content: space-between;
				height: 50rpx;
				padding: 4rpx 20rpx 4rpx 8rpx;
				font-size: $operationSize;
				color: $operationColor;
				.browse {
					width: 110rpx;
					display: flex;
					align-items: center;
					.browse-count {
						padding-left: 8rpx;
					}
				}
			}
			
		}
	}
</style>
