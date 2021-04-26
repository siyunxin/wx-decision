<template>
	<view>
		<u-form :value="formData" ref="form" validate-trigger="bind" err-show-type="undertext">
				<u-form-item  required label="事件类别:" label-width="150" >
					<uni-combox  :candidates="candidates" placeholder="事件类型" v-model="formData.lx"></uni-combox>
				</u-form-item>
				<u-form-item  required label="事件名称:" label-width="150">
					<input type="text" v-model="formData.age" class="uni-input-border form-input" 
					 placeholder="">
				</u-form-item>
				<u-form-item required label="上报时间:" label-width="150">
					<input type="text" v-model="formData.date" class="uni-input-border form-input"
					 placeholder="">
				</u-form-item>
				<u-form-item  required label="发生地点:" label-width="150">
				<input type="text" v-model="formData.city" class="uni-input-border form-input"
				 placeholder="">
				</u-form-item>

				<u-form-item  required label="时间概述:" label-width="150">
					<input type="text" v-model="formData.info" class="uni-input-border form-input"
					 placeholder="">
				</u-form-item>

				<u-form-item  label="相关附件:" label-width="150">
					<image src="../../static/upload.png" style="width: 80rpx;height: 80rpx;"></image>
				</u-form-item>
			<view class="example">
				<button class="button" type="submit">提交</button>
			</view>
		</u-form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				formData: {
					age:' ',
					city:' ',
					date:' ',
					info:' ',
					lx:''
				},
				candidates: [
					'城市部件', '城市事件'
				],

				

			}
		},
	
		methods: {
			
		}
	}
</script>

<style>
	@charset "UTF-8";

	/* 头条小程序组件内不能引入字体 */
	/* #ifdef MP-TOUTIAO */
	@font-face {
		font-family: uniicons;
		font-weight: normal;
		font-style: normal;
		src: url("~@/static/uni.ttf") format("truetype");
	}

	/* #endif */
	/* #ifndef APP-NVUE */
	page {
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		min-height: 100%;
		height: auto;
	}

	view {
		font-size: 14px;
		line-height: inherit;
	}

	.example {
		padding: 0 15px 15px;
	}

	.example-info {
		padding: 15px;
		color: #3b4144;
		background: #ffffff;
	}

	.example-body {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: center;
		padding: 0;
		font-size: 14px;
		background-color: #ffffff;
	}

	/* #endif */
	.example {
		padding: 0 15px;
	}

	.example-info {
		/* #ifndef APP-NVUE */
		display: block;
		/* #endif */
		padding: 15px;
		color: #3b4144;
		background-color: #ffffff;
		font-size: 14px;
		line-height: 20px;
	}

	.example-info-text {
		font-size: 14px;
		line-height: 20px;
		color: #3b4144;
	}

	.example-body {
		flex-direction: column;
		padding: 15px;
		background-color: #ffffff;
	}

	.word-btn-white {
		font-size: 18px;
		color: #FFFFFF;
	}

	.word-btn {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		align-items: center;
		justify-content: center;
		border-radius: 6px;
		height: 48px;
		margin: 15px;
		background-color: #007AFF;
	}

	.word-btn--hover {
		background-color: #4ca2ff;
	}

	.example {
		padding: 0 10px 10px;
	}

	.uni-input-border,
	.uni-textarea-border {
		width: 100%;
		font-size: 14px;
		color: #666;
		border: 1px #e5e5e5 solid;
		border-radius: 5px;
		box-sizing: border-box;
	}

	.uni-input-border {
		padding: 0 10px;
		height: 35px;
	}

	.uni-textarea-border {
		padding: 10px;
		height: 80px;
	}

	.label-box {
		margin-right: 10px;
	}
	.transform-scale {
		transform: scale(0.7);
	}

	.button {
		margin: 10px auto;
		color: #fff;
		background-color: #007aff;
	}
	.form-input {
		border: none;
	}
</style>
