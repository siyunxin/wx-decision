<template>
	<view class="content">
		<scroll-view class="scrollView" scroll-y="true" refresher-enabled :refresher-triggered="refresherTriggered"
			@refresherrefresh="refresherrefresh" @scrolltolower="scrollToLower" :lower-threshold="lowerThreshold">
			<view class="swiper-wrap">
				<u-swiper :list="list" :height="340"></u-swiper>
			</view>
			<view class="modules-wrap">
				<modules-fun></modules-fun>
			</view>
			<view class="news-wrap">
				<news></news>
			</view>
			<uni-load-more :status="loadMoreStatus"></uni-load-more>
		</scroll-view>
	</view>
</template>

<script>
	import ModulesFun from './Modules.vue'
	import News from './News.vue'
	export default {
		components:{
			ModulesFun,
			News
		},
		data() {
			return {
				list: [{
						image: '/static/image/news/lb1.jpg',
					},
					{
						image: '/static/image/news/lb2.jpg',
					},
					{
						image: '/static/image/news/lb3.jpg',
					},
					{
						image: '/static/image/news/lb4.jpg',
					}
				],
				showDownRefresh: false,
				lowerThreshold: 45, //距离底部45 px 是触发 
				refresherTriggered: false  ,//是否在下拉状态
				loadMoreStatus: "more"  //加载更多状态
			}
		},
		methods: {
			toLogin() {
				uni.navigateTo({
					url:"/pages/login/index"
				})
			},
			//下拉刷新
			refresherrefresh() {
				console.log('refresh', this.refresherTriggered)
				var that = this
				if(!this.refresherTriggered) {
					this.refresherTriggered = true
					setTimeout(function() {
						that.refresherTriggered = false
					}, 1000)
				}
			},
			
			//scrollToLower
			scrollToLower() {
				console.log("lower")
				var that = this
				
				this.loadMoreStatus = "loading",
				
				setTimeout(function () {
					that.loadMoreStatus = "noMore"
				},3000)
			}
		}
	}
</script>

<style lang="scss">
	.content {
		width: 100%;
		height: 100%;
		overflow: hidden;
		.scrollView {
			height: 100%;
		}
		.swiper-wrap {
			width: 100%;
			height: 340rpx;
			.swiper {
				margin: 10rpx;
				// border: 1rpx solid #007AFF;
			}	
		}
		
		.modules-wrap {
			width: 100%;
			// height: 260rpx;
		}
	}
</style>
