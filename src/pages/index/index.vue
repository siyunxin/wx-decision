<template>
	<view class="content">
		<scroll-view 
		 class="scrollView"
		 scroll-y="true"
		 refresher-enabled
		 :refresher-triggered="refresherTriggered"
		 @refresherrefresh="refresherrefresh"
		 @scrolltolower="scrollToLower"
		 :lower-threshold="lowerThreshold"
		 >
			<view class="swiper-wrap">
				<swiper class="swiper" indicator-dots circular>
					<swiper-item>
						<image style="width:100%" src="../../static/lb1.jpg"></image>
					</swiper-item>
					<swiper-item><image src="../../static/lb2.jpg"></image></swiper-item>
					<swiper-item><image src="../../static/lb3.jpg"></image></swiper-item>				
				</swiper>
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
	import News from './Nes.vue'
	import uniLoadMore from '../../uni_modules/uni-load-more/components/uni-load-more/uni-load-more.vue'
	export default {
		data() {
			return {
				title: 'Hello',
				showDownRefresh: false,
				lowerThreshold: 45, //距离底部45 px 是触发 
				refresherTriggered: false  ,//是否在下拉状态
				loadMoreStatus: "more"  //加载更多状态
			}
		},
		components:{
			ModulesFun,
			News,
			uniLoadMore
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
		},
		onLoad() {
		
		},
	}
</script>

<style lang="scss" scoped>
	.content {
		width: 100%;
		height: 100%;
		overflow: hidden;
		.scrollView {
			height: 100%;
		}
		.swiper-wrap {
			width: 100%;
			height: 320rpx;
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
