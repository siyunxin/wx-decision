<template>
	<view class="login-container">
		<view class="wrap">
			<view class="logo">
				<!-- <image :src="userInfo.avatarUrl"></image> -->
			</view>
			<view class="label">新模式，心治理</view>
			<!-- <button class="btn" @click="handleLogin">微信一键登录</button> -->
			<button class="sys_btn" open-type="getUserInfo" lang="zh_CN" @getuserinfo="appLoginWx">小程序登录授权</button>
			<!-- <button class="btn" @click="toIndex">toIndex</button> -->
		</view>
	</view>
</template>

<script>
	export default {
		name: "login",
		data() {
			return {
				userInfo: {}
			}
		},
		methods: {
			appLoginWx() {

				uni.getProvider({
					service: 'oauth',
					success: function(res) {
						if (~res.provider.indexOf('weixin')) {
							uni.login({
								provider: 'weixin',
								success: (res2) => {
									uni.getUserInfo({
										provider: 'weixin',
										success: (info) => { //这里请求接口
											console.log(res2);
											console.log(info);

										},
										fail: () => {
											uni.showToast({
												title: "微信登录授权失败",
												icon: "none"
											});
										}
									})

								},
								fail: () => {
									uni.showToast({
										title: "微信登录授权失败",
										icon: "none"
									});
								}
							})

						} else {
							uni.showToast({
								title: '请先安装微信或升级版本',
								icon: "none"
							});
						}
					}
				});
			},
			toIndex() {
				uni.navigateTo({
					url: "/pages/index/index"
				})
			}
		}
	}
</script>

<style scoped>
	.login-container {
		width: 100%;
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.wrap {
		width: 50%;
		height: 500rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;

	}

	.logo {
		width: 180rpx;
		height: 100rpx;
		border: 1rpx solid #000;
		margin: 8rpx;
	}

	.label {
		margin: 10rpx;
	}

	.btn {
		margin-top: 100rpx;
	}

	image {
		width: 100%;
		height: 100%;
	}
</style>
