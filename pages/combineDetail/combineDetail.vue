<template>
	<view class="contains">
		<view class="title">组合内容</view>
		<view class="contain-game">
			<view class="game-box" style="margin: 0;" v-for="(item, idx) in pageData">
				<huaqiDetailList
					style="margin: 0;"
					:title="item.title"
					:rank="item.rank"
					:interestRate="item.interestRate"
					:background="item.background"
					:avgRate="item.avgRate"
				></huaqiDetailList>
			</view>
		</view>

		<view class="dev-status"><devStatus :combine="true"></devStatus></view>
	</view>
</template>

<script>
import huaqiDetailList from '../../components/huaqiDetailList/huaqiDetailList.vue';
import devStatus from '../../components/huaqi-dev-status/huaqi-dev-status.vue';
export default {
	components: {
		huaqiDetailList,
		devStatus
	},
	data() {
		return {
			pageData: [
				{
					title: '项目一',
					rank: '1/40',
					interestRate: '13',
					avgRate: '11',
					background: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				},
				{
					title: '项目一',
					rank: '1/40',
					interestRate: '13',
					avgRate: '11',
					background: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				},
				{
					title: '项目一',
					rank: '1/40',
					interestRate: '13',
					avgRate: '11',
					background: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				},
				{
					title: '项目一',
					rank: '1/40',
					interestRate: '13',
					avgRate: '11',
					background: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				},
				{
					title: '项目一',
					rank: '1/40',
					interestRate: '13',
					avgRate: '11',
					background: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				},
				{
					title: '项目一',
					rank: '1/40',
					interestRate: '13',
					avgRate: '11',
					background: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				},
				{
					title: '项目一',
					rank: '1/40',
					interestRate: '13',
					avgRate: '11',
					background: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				},
				{
					title: '项目一',
					rank: '1/40',
					interestRate: '13',
					avgRate: '11',
					background: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				},
				{
					title: '项目一',
					rank: '1/40',
					interestRate: '13',
					avgRate: '11',
					background: 'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				}
			]
		};
	},
	methods: {}
};
</script>

<style scoped>
.contains {
	display: flex;
	flex-direction: column;
	justify-content: center;
	text-align: center;
	align-items: center;
}
.title {
	margin: 35upx 0;
	font-size: 40upx;
	color: #ffffff;
	padding-bottom: 15upx;
	width: 50%;
	border-bottom: 4upx solid #ffffff;
}
.dev-status {
	position: fixed;
	z-index: 1;
}
	
.contain-game{
	height: 70vh;
	overflow: scroll;
}
</style>
