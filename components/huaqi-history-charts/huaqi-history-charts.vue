<template>
	<view class="contains">

		<view class="title" style="font-size: 50upx; color: #FFFFFF;">
			利润走势
		</view>
		<view>
			<canvas canvas-id="canvasColumn" @touchstart="touchLineA"  id="canvasColumn" class="charts"></canvas>
		</view>
		<view class="mouth" style="font-size: 30upx; color: #FFFFFF;margin-top: 5upx;">
			月份
		</view>
	</view>
</template>

<script>
import uCharts from '../u-charts/u-charts.js';
var _self;
var canvaLineA = null;
export default {
	data() {
		return {
			cWidth: '',
			cHeight: '',
			pixelRatio: 1,
			chartData: {
				categories: ['1月', '2月', '3月', '4月', '5月', '6月'],
				series: [
					{
						name: '利率',
						data: [35, 8, 25, 37, 4, 20]
					},
				]
			}
		};
	},
	mounted() {
		_self = this;
		this.cWidth = uni.upx2px(600);
		this.cHeight = uni.upx2px(400);
		this.getServerData();
	},
	methods: {
		getServerData() {
			// uni.request({
			// 	url: 'https://www.ucharts.cn/data.json',
			// 	data: {},
			// 	success: function(res) {
			// 		console.log(res.data.data);
			// 		let LineA = { categories: [], series: [] };
			// 		//这里我后台返回的是数组，所以用等于，如果您后台返回的是单条数据，需要push进去
			// 		LineA.categories = res.data.data.LineA.categories;
			// 		LineA.series = res.data.data.LineA.series;
			// 		console.log(LineA)
			// 		_self.showLineA('canvasColumn', LineA);
			// 	},
			// 	fail: () => {
			// 		_self.tips = '网络错误，小程序端请检查合法域名';
			// 	}
			// });
			_self.showLineA('canvasColumn', this.chartData);
		},
		showLineA(canvasId, chartData) {
			canvaLineA = new uCharts({
				$this: _self,
				canvasId: canvasId,
				type: 'line',
				fontSize: 11,
				legend: { show: true },
				dataLabel: false,
				dataPointShape: true,
				background: '#FFFFFF',
				pixelRatio: _self.pixelRatio,
				categories: chartData.categories,
				series: chartData.series,
				animation: true,
				xAxis: {
					type: 'grid',
					gridColor: '#CCCCCC',
					gridType: 'dash',
					dashLength: 8
				},
				yAxis: {
					gridType: 'dash',
					gridColor: '#CCCCCC',
					dashLength: 8,
					splitNumber: 5,
					min: 0,
					max: 40,
					format: val => {
						return val.toFixed(0) + '%';
					}
				},
				width: _self.cWidth * _self.pixelRatio,
				height: _self.cHeight * _self.pixelRatio,
				extra: {
					line: {
						type: 'straight'
					}
				}
			});
		},
		touchLineA(e) {
			canvaLineA.showToolTip(e, {
				format: function(item, category) {
					return category + ' ' + item.name + ':' + item.data;
				}
			});
		}
	}
};
</script>

<style scoped>
/*样式的width和height一定要与定义的cWidth和cHeight相对应*/
.charts {
	width: 600upx;
	height: 400upx;
	background-color: #0C1E22;
}
.contains{
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	border-radius: 25upx;
}
.title{
	width: 100%;
}
</style>
