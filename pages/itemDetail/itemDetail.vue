<template>
	<view class="contains-2">
		<!-- <image src="https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg" mode=""></image> -->
		<!-- 项目轮播图 -->
		<huaqiCombineSwiper :picture="swiper.picture" :onlySwiper="true" />
		<!-- 项目概述 -->
		<huaqiDetailList :title="listBox.title"  :rank="listBox.rank" :interestRate="listBox.interestRate" :background="listBox.background" :avgRate="listBox.avgRate" />
		<!-- 表单 -->
		<huaqiHistoryCharts />
		<!-- 开发进程 -->
		<devStatus @buyin="navTo('../buy/buy')" 
		@funding="navTo('../funding/funding')"
		@soldout="navTo('../sold/sold')"/>
		
	</view>
</template>

<script>
import huaqiCombineSwiper from '../../components/huaqiCombineSwiper/huaqiCombineSwiper.vue';
import huaqiDetailList from '../../components/huaqiDetailList/huaqiDetailList.vue'
import huaqiHistoryCharts from '../../components/huaqi-history-charts/huaqi-history-charts.vue'
import devStatus from '../../components/huaqi-dev-status/huaqi-dev-status.vue'
export default {
	components: {
		huaqiCombineSwiper,
		huaqiDetailList,
		huaqiHistoryCharts,
		devStatus
	},
	data() {
		return {
			swiper: {
				picture: [
					{
						src: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg',
						id: 12
					},
					{
						src: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg',
						id: 12
					},
					{
						src: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg',
						id: 12
					},
					{
						src: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg',
						id: 12
					}
				],
			},
			listBox:{
				title:"项目一",
				rank:"1/40",
				interestRate:"13",
				avgRate:"11",
				background:'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg',
			}
		};
	},
	methods: {
		navTo(url) {
			console.log(url);
			if (url) {
				uni.navigateTo({
					url: url,
					animationType: 'slide-in-right',
					animationDuration: 200
				});
			}
		}
	},
	onLoad(option) {
		console.log(option);
	}
};
</script>

<style>
.contains-2 {
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
}

</style>
