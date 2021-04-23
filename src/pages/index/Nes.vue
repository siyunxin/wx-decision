<template>
	<view>
		<label-cell label="新闻资讯"></label-cell>
		<news-item v-for="(i,index) in newsList" :key="index" :newsInfo="i"></news-item>
	</view>
</template>

<script>
	import LabelCell from '@/components/LabelCell.vue'
	import NewsItem from '@/components/NewsItem.vue'
	export default {
		components:{
			NewsItem,
			LabelCell
		},
		data() {
			return {
				newsList: [
					{
						src: "",
						text: "大连金普新区管理委员会关于印发2021年金普新区“惠民实事”项目的通知",
						browseCount: 11,
						source: "新闻中心",
						img:require('../../static/lb1.jpg')
					},
					{
						src: "",
						text: "国家卫健委一行调研金普新区新冠疫苗接种工作",
						browseCount: 22,
						source: "新闻中心",
						img:require('../../static/lb2.jpg')
					},
					{
						src: "",
						text: "金普新区召开会议以更高标准开展新一轮创城工作3",
						browseCount: 33,
						source: "新闻中心",
						img:require('../../static/lb3.jpg')
					},
					{
						src: "",
						text: "总投资80亿元航海时代海洋文旅城在金石滩奠基",
						browseCount: 44,
						source: "中心4",
						img:require('../../static/lb4.jpg')
					}
				]
			}
		},
		
		methods:{
			
		}
	}
</script>

<style lang="scss" scoped>
</style>
