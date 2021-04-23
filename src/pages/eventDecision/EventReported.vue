//事件上报
<template>
	<view class="container">
		<radio-group @change="radioChange">
			<label class="uni-list-cell uni-list-cell-pd" v-for="(item, index) in items" :key="item.value">
				<view>
					<radio :value="item.value" :checked="index === current" />
				</view>
				<view>{{item.name}}</view>
			</label>
		</radio-group>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				items: [{
						value: 1,
						name: '城市部件',
						checked: 'true'
					},
					{
						value: 2,
						name: '城市事件',
						
					},
					
				],
				current: 0
			}
		},
		methods: {
			radioChange: function(evt) {
			            for (let i = 0; i < this.items.length; i++) {
			                if (this.items[i].value === evt.target.value) {
			                    this.current = i;
			                    break;
			                }
			            }
			        }
		}
	}
</script>

<style lang="scss" scoped>
	.container {}
</style>
