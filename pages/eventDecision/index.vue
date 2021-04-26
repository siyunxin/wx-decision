<template>
	<view class="decision">
		<view class="header">
			<view class="input-view">
				<u-icon type="search" size="22" color="#666666" />
				<input confirm-type="search" class="input" type="text" placeholder="输入搜索关键词" @confirm="confirm">
			</view>
		</view>
		<view class="search-div">
			<u-form>
				<u-row gutter="12">
					<u-col span="4">
						<u-form-item label="事件类型:" label-width="130" :border-bottom="false">
							<input placeholder="事件类型" class="form-input" type="select" @focus="eventTypeFocus" v-model="eventTypeValue">
						</u-form-item>
					</u-col>
					<u-col span="4">
						<u-form-item label="事件来源:" label-width="130" :border-bottom="false">
							<input placeholder="事件来源" class="form-input">
						</u-form-item>
					</u-col>
					<u-col span="4">
						<u-form-item label="事件描述:" label-width="130" :border-bottom="false">
							<input placeholder="事件描述" class="form-input">
						</u-form-item>
					</u-col>
				</u-row>
				<u-row gutter="16">
					<u-col span="4">
						<u-form-item label="事件状态:" label-width="130" :border-bottom="false">
							<input placeholder="事件状态" class="form-input">
						</u-form-item>
					</u-col>
					<u-col span="4">
						<u-form-item label="责任单位:" label-width="130" :border-bottom="false">
							<input placeholder="责任单位" class="form-input">
						</u-form-item>
					</u-col>
					<u-col span="4">
						<u-form-item label="所属街道:" label-width="130" :border-bottom="false">
							<input placeholder="所属街道" class="form-input">
						</u-form-item>
					</u-col>
					
				</u-row>
				<u-row class="row-button">
					<u-col span="3">
						<button class="search_btn">搜索</button>
					</u-col>
				</u-row>
			</u-form>
			<u-select :list="eventType" v-model="eventTypeFlag" @confirm="eventConfirm"></u-select>
			<u-select :list="eventSource"></u-select>
			<u-select :list="eventStatus"></u-select>
			<u-select :list="dutyUnit"></u-select>
			<u-select :list="belongStreet"></u-select>
		</view>
		<uni-table border stripe emptyText="暂无更多数据" :loading="loading">
			<uni-tr>
				<uni-th align="center">序号</uni-th>
				<uni-th align="center">事件类型</uni-th>
				<uni-th align="center">事件来源</uni-th>
				<uni-th align="center">事件描述</uni-th>
				<uni-th align="center">事件状态</uni-th>
				<uni-th align="center">责任单位</uni-th>
				<uni-th align="center">所属街道</uni-th>
			</uni-tr>
			<uni-tr v-for="i in 10" :key="i" @click="trClick">
				<uni-td align="center">{{i+1}}</uni-td>
				<uni-td align="center">类型{{i+1}}</uni-td>
				<uni-td align="center">来源{{i+1}}</uni-td>
				<uni-td align="center">描述{{i+1}}</uni-td>
				<uni-td align="center">状态{{i+1}}</uni-td>
				<uni-td align="center">单位{{i+1}}</uni-td>
				<uni-td align="center">街道{{i+1}}</uni-td>
			</uni-tr>
		</uni-table>
		<!-- <view class="table-scorll">
			<table>
				<tr>
					<th>序号</th>
					<th>事件类型</th>
					<th>事件来源</th>
					<th>事件描述</th>
					<th>事件状态</th>
					<th>责任单位</th>
					<th>所属街道</th>
				</tr>
				<tr v-for="i in 10" :key="i" @click="trClick">
					<td>{{i}}</td>
					<td>类型{{i}}</td>
					<td>来源{{i}}</td>
					<td>描述{{i}}</td>
					<td>状态{{i}}</td>
					<td>单位{{i}}</td>
					<td>街道{{i}}</td>
				</tr>
			</table>


		</view> -->
	</view>
</template>

<script>
	export default {
		components: {},
		data() {
			return {
				eventType: [{
						label: '城市部件',
						value: '1'
					},
					{
						label: '城市事件',
						value: '2'
					}
				],
				eventSource: [{
						label: "来源1",
						value: 1
					},
					{
						label: "来源2",
						value: 2
					}
				],
				eventStatus: [{
						label: "状态1",
						value: 1,
					},
					{
						label: "状态2",
						value: 2
					}
				],
				dutyUnit: [{
						label: "单位1",
						value: 1
					},
					{
						label: "单位2",
						value: 2
					}
				],
				dutyUnit: [{
						label: "单位1",
						value: 1
					},
					{
						label: "单位2",
						value: 2
					}
				],

				belongStreet: [{
						label: "街道1",
						value: 1
					},
					{
						label: "街道2",
						value: 2
					}
				],
				eventTypeFlag: false,
				eventTypeValue: '',
				city: '',
				loading: true,
			}
		},
		methods: {
			trClick() {
				console.log(i)
				this.$refs.popupDialog.open();
			},
			eventTypeFocus() {
				this.eventTypeFlag = true
			},
			eventConfirm(v) {
				const [a] = [...v]
				this.eventTypeValue = a.label
			}
		},
		onShow() {
			var that = this;
			setTimeout(function() {
				that.loading = false
			}, 1000);
		},
		
		
	}
</script>

<style>
	.header {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		padding: 10px 15px;
		align-items: center;
		border-top-width: 1px;
		border-top-color: #f5f5f5;
		border-top-style: solid;
		background-color: #ffffff;
	}

	.input-view {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		align-items: center;
		flex-direction: row;
		background-color: #e7e7e7;
		height: 30px;
		border-radius: 15px;
		padding: 0 10px;
		flex: 1;
		background-color: #f5f5f5;
	}

	.search-div {
		display: flex;
		flex-wrap: wrap;
		/* width: 85%; */
		margin: 0 auto;
		align-items: center;
		/* justify-content: space-between; */
	}

	.search-div>.uni-combox {
		width: 32%;
	}

	.search_btn {
		height: 60rpx;
		width: 160rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.uni-table-mask {
		background: none !important;
	}

	.table-scorll {
		width: 100%;
		overflow-x: auto;
	}

	.form-input {
		font-size: 24rpx;
		border: 2rpx solid #303133;
	}
	
	.row-button {
		display: flex;
		height: 80rpx;
		flex-direction: row-reverse;
		align-items: center;
	}

	/* 
	table {
		min-width: 900px;
	}

	th {
		padding: 12px 10px;
		display: table-cell;
		color: #333;
		font-weight: 500;
		border: 1px #ddd solid;
		font-size: 14px;
		box-sizing: border-box;
		border-left: none;
	}

	td {
		display: table-cell;
		padding: 12px 10px;
		vertical-align: middle;
		border-bottom: 1px #ddd solid;
		color: #666;
		font-size: 14px;
		box-sizing: border-box;
		border-right: 1px #ddd solid;
		text-align: center;
	}

	tr:nth-child(2n+3) {
		background-color: #fafafa;
	} */
</style>

