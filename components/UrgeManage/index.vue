<template>
		<view class="urge">
			<view class="urge-title">
				事件催办
			</view>
			<view class="urge-form">
				<u-form>
					<u-form-item label="牵头单位:" label-width="130" :border-bottom="false">
						<input placeholder="请选择牵头单位">
					</u-form-item>
					<u-form-item label="协办单位:" label-width="130" :border-bottom="false">
						<input placeholder="请选择协办单位" />
					</u-form-item>
					<u-form-item label="催办意见:" label-position="top" :border-bottom="false">
						<textarea placeholder="请输入催办意见" />
					</u-form-item>
				</u-form>
			</view>
			<view class="urge-bottom">
				<view class="urge-btn">
					<button>保存</button>
				</view>
				<view class="urge-btn">
					<button>派发</button>
				</view>
			</view>
		</view>

</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
		.urge {
			background-color: #fff;
			margin: 0 auto;
			width:600rpx ;
			height:750rpx;
			.urge-close {
				position: absolute;
				top: 10rpx;
				right: 18rpx;
			}

			.urge-title {
				padding: 20rpx 0 0 12rpx;
				font-size: 34rpx;

			}

			.urge-form {
				padding: 0 12rpx;

				input {
					width: 100%;
					height: 60rpx;
					line-height: 60rpx;
					border: 2rpx solid #606266;
					font-size: 28rpx;
					border-radius: 8rpx;
					padding: 4rpx 6rpx
				}

				textarea {
					width: 100%;
					font-size: 28rpx;
					height: 200rpx;
					border: 2rpx solid #606266;
					border-radius: 8rpx;
					padding: 4rpx 6rpx
				}
			}

			.urge-bottom {
				display: flex;
				margin-top: 12rpx;
				justify-content: center;

				.urge-btn {
					width: 200rpx;
					margin: 0 16rpx;

					button {
						font-size: 28rpx;
						background: #007AFF;
						color: #FFFFFF;
					}
				}
			}
		}
</style>
