<template>
	<view class="investment-container">
		<!-- 主页面 -->
		<searchBar></searchBar>
		<!-- 5个按钮 -->
		<huaqiSortButton />
		
		<!-- 项目详情列表 -->
		<view class="item-list">
			<huaqiGameList
				v-for="item in marketData"
				@clicked="navTo('../itemDetail/itemDetail?id=' + item.id)"
				:title="item.title"
				:rank="item.rank"
				:interestRate="item.interestRate"
				:background="item.background"
			/>
		</view>
	</view>
</template>

<script>
import huaqiSortButton from '../../components/huaqi-sort-button/huaqi-sort-button.vue';
import huaqiGameList from '../../components/huaqi-game-list/huaqi-game-list.vue';
import searchBar from '../../components/searchBar/searchBar.vue'
export default {
	components: {
		huaqiGameList,
		huaqiSortButton,
		searchBar
	},
	data() {
		return {
			// 标记市场还是持有 0:市场 1：持有
			currentPlace: 0,
			buttonContains: [
				{
					id: 1,
					src: '../../static/common-icons/new.png',
					title: '新发'
				},
				{
					id: 2,
					src: '../../static/common-icons/rank.png',
					title: '排行'
				},
				{
					id: 3,
					src: '../../static/common-icons/module.png',
					title: '板块',
					url: '../module/module'
				},
				{
					id: 4,
					src: '../../static/common-icons/combine.png',
					title: '组合',
					url: '../combine/combine'
				},
				{
					id: 5,
					src: '../../static/common-icons/invest.png',
					title: '定投',
					url: '../fixedInvestment/fixedInvestment'
				}
			],
			marketData: [
				{
					id: 1,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 1
				},
				{
					id: 2,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 2
				},
				{
					id: 3,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 3
				},
				{
					id: 4,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 4
				},
				{
					id: 5,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 5
				}
			]
		};
	},
	methods: {
		swiperChange(e) {
			console.log(e.detail.current);
			this.currentPlace = e.detail.current;
		},
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
	mounted() {}
};
</script>

<style>
.investment-container {
	width: 100%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
}
/* list */
.item-list {
	margin-top: 50upx;
}
</style>
