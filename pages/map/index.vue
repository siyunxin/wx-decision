<template>
	<view>
		<view>
			<text>经度: {{ longitude }}</text>
			<text>纬度: {{ latitude}}</text>
			<button @click="getLocation">获取当前位置</button>
		</view>
		<map id="map1" ref="map1" style="width: 100%; height: 700rpx;" :latitude="latitude" :longitude="longitude"
			:show-compass="true" :show-location="true" @tap="handleTap">
		</map>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				latitude: '', //纬度
				longitude: '', //经度
			}
		},
		methods: {
			getLocation() {
				var that = this
				uni.getLocation({
				    type: 'gcj02', //返回可以用于uni.openLocation的经纬度
				    success: function (res) {
				        const latitude = res.latitude;
				        const longitude = res.longitude;
						that.latitude = latitude;
						that.longitude = longitude;
				        uni.openLocation({
				            latitude: latitude,
				            longitude: longitude,
				            success: function (openRes) {
				                console.log('success', openRes);
				            }
				        });
				    }
				});
			},
			//获取是否授权
			getSetting() {
				const that = this
				uni.getSetting({
					success(res) {
						console.log(res)
						if (res.authSetting['scope.userLocation']) {
							that.getLocation()
						} else {
							that.getAuthorize()
						}
					}
				})
			},
			//用户授权
			getAuthorize() {
				const that = this
				uni.authorize({
					scope: 'scope.userLocation',
					success(res) {
						that.getLocation()
					},
					// 授权失败
					fail(err) {
						uni.showModal({
							title: '提示',
							content: '请授权位置获取附近的商家!',
							showCancel: false,
							confirmText: '确认授权',
							success() {
								uni.openSetting({
									success(res) {
										console.log(res)
									},
									fail(err) {
										console.log(err)
									}
								})
							}
						})
					}
				})
			},
			//点击地图时触发
			handleTap(e) {
				console.log(e)
			}
		},
		onReady() {
			this.getLocation()
		}
	}
</script>

<style>
</style>
