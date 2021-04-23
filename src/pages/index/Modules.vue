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
						icon:require('../../static/jc.png'),
						redirect: "/pages/eventDecision/EventReported",
					},
					{
						id: 2,
						name: "事件地图",
						icon:require('../../static/dt.png'),
					},
					{
						id: 3,
						name: "金普供热",
						icon:require('../../static/gr.png'),
					},
					{
						id: 4,
						name: "金普供水",
						icon:require('../../static/gs.png'),
					},
					{
						id: 5,
						name: "金普气象",
						icon:require('../../static/qx.png'),
					},
					{
						id: 6,
						name: "事件管理",
						icon:require('../../static/gl.png'),
					},
					{
						id: 7,
						name: "全部功能",
						icon:require('../../static/gd.png'),
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
	$iconWidth: 80rpx;
	.wrap {
		display: grid;
		grid-template-columns: repeat(4, 25%);
		
		.box {
			height: $boxHheight;
			
			.icon {
				width: $iconWidth;
				height: $iconWidth;
				margin: 0 auto;
				// border: 1rpx solid #4CD964;
				image {
					width: 100%;
					height: 100%;
				}
			}
			
			.label {
				font-size: 26rpx;
				text-align: center;
				padding: 6rpx 0;
			}
			
		}
	}
</style>
