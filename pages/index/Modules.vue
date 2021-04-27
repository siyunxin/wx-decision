<template>
	<view class="wrap">
		<view class="box" v-for="i in modulesList" :key="i.id" @click="handleRedirect(i)">
			<view class="icon">
				<image :src="i.icon"></image>
			</view>
			<view class="label">
				<text>{{i.name}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				modulesList: [
					{
						id: 1,
						name: "事件决策",
						icon:require('../../static/image/modules_icon/jc.png'),
						redirect: "/pages/eventDecision/index",
					},
					{
						id: 2,
						name: "事件地图",
						icon:require('../../static/image/modules_icon/dt.png'),
						redirect: '/pages/map/index'
					},
					{
						id: 3,
						name: "金普供热",
						icon:require('../../static/image/modules_icon/gr.png'),
					},
					{
						id: 4,
						name: "金普供水",
						icon:require('../../static/image/modules_icon/gs.png'),
					},
					{
						id: 5,
						name: "金普气象",
						icon:require('../../static/image/modules_icon/qx.png'),
					},
					{
						id: 6,
						name: "事件管理",
						icon:require('../../static/image/modules_icon/gl.png'),
						redirect: '/pages/eventAdmin/index'
					},
					{
						id: 7,
						name: "全部功能",
						icon:require('../../static/image/modules_icon/gd.png'),
					},
					
				]
			}
		},
		methods:{
			handleRedirect(module) {
				const { redirect }  = module
				uni.navigateTo({
					url: redirect
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	$boxWidth: 25%;
	$boxHheight: 150rpx;
	$iconWidth: 60rpx;
	.wrap {
		display: grid;
		grid-template-columns: repeat(4, 25%);
		padding: 10rpx 0;
		.box {
			height: $boxHheight;
			
			.icon {
				width: $iconWidth;
				height: $iconWidth;
				margin: 0 auto;
				margin-top: 10rpx;
				image {
					width: 100%;
					height: 100%;
				}
			}
			
			.label {
				font-size: 26rpx;
				text-align: center;
				padding: 6rpx 0;
				margin-top: 20rpx;
			}
			
		}
	}
</style>
