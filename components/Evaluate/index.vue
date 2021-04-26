<template>
	<view>
		<view class="model-warp">
			<view class="model-header">结果评价</view>
			<view class="model-close" @click="handleClose">X</view>
			<view class="content">
				<view class="subhead">处置打分</view>
				<view class="start-warp">
					<view class="start">
						<view v-for="i in 5" class="start-m" @click="startClick(i)">
							<image :src="i>score?destart:starton" mode=""></image>
						</view>
					</view>
					<view class="result-text">
						满意
					</view>
				</view>
				<view class="suggest-warp">
					<view class="subhead">处置评价</view>
					<view>
						<textarea autofocus="autofocus" placeholder="请输入您的处置评价" cols="20" rows="3"></textarea>
					</view>
				</view>
				<view>
					<button type="primary" @click="submit">提交</button>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				starton: require('../../static/image/evaluate/starton.png'),
				destart: require('../../static/image/evaluate/destart.png'),
				score: 3

			}
		},
		methods: {

			startClick(i) {
				if (i == 1 && this.score == 1) {
					this.score = 0;
					return
				}
				this.score = i;
			},
			handleClose() {
				console.log(1)
				this.$emit("closeEvaluate")
			},
			submit() {
				this.$emit("closeEvaluate")
			}
		}
	}
</script>

<style lang="scss" scoped>
	.model-warp {
		background-color: #fff;
		min-width: 60%;
		max-width: 92%;
		height: 900rpx;
		border: 1px solid #C0C0C0;
		border-radius: 50rpx;
		position: fixed;
		top: 0;
		right: 0;
		left: 0;
		bottom: 0;
		margin: auto;
		z-index: 999;
		.model-header {
			height: 90rpx;
			line-height: 90rpx;
			font-weight: 600;
			font-size: 35rpx;
			padding-left: 10rpx;
			// border-bottom: 1px solid #666666;
		}

		.content {
			width: 95%;
			margin: 0 auto;

			.subhead {
				height: 60rpx;
				line-height: 60rpx;
				font-size: 30rpx;
				margin-bottom: 15rpx;
			}

			.start-warp {
				display: flex;
				align-items: center;
				margin-bootom: 25rpx;

				.start {
					width: 80%;
					display: flex;
					margin-top: 25rpx;
					align-items: center;
					justify-content: space-between;

					.start-m {
						image {
							width: 90rpx;
							height: 90rpx;
						}
					}
				}

				.result-text {
					width: 15%;
					display: flex;
					align-items: center;
					justify-content: flex-end;


				}
			}

			.suggest-warp {
				margin-bottom: 35rpx;

				textarea {
					border: 1px solid #ccc;
					width: 90%;
					padding: 25rpx;
				}
			}
		}
	}
	.model-close {
		position: absolute;
		top: 20rpx;
		right: 40rpx;
	}
</style>
