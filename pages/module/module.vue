<template>
	<view class="contains">
		<searchBar class="search-box" style="color: #FFFFFF;" />
		<view class="list-contains">
			<view class="list-body" v-for="item in marketData">
				<huaqiGameModuleList :avgRate="item.avgRate" :classType="item.classType" :title="item.title" :interestRate="item.interestRate" :background="item.background" />
			</view>
		</view>
	</view>
</template>

<script>
import huaqiGameList from '../../components/huaqi-game-list/huaqi-game-list.vue';
import searchBar from '../../components/searchBar/searchBar.vue';
import huaqiGameModuleList from '../../components/huaqi-game-module-list/huaqi-game-module-list.vue';
export default {
	components: {
		huaqiGameList,
		searchBar,
		huaqiGameModuleList
	},
	data() {
		return {
			marketData: [
				{
					id: 1,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 1,
					classType: '游戏类别',
					avgRate: 21
				},
				{
					id: 2,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 2,
					classType: '游戏类别',
					avgRate: 21
				},
				{
					id: 3,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 3,
					classType: '游戏类别',
					avgRate: 21
				},
				{
					id: 4,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 4,
					classType: '游戏类别',
					avgRate: 21
				},
				{
					id: 5,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 5,
					classType: '游戏类别',
					avgRate: 21
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
	align-items: center;
	text-align: center;
	width: 95%;
}
.search-box {
	margin-top: 40upx;
	margin-bottom: 20upx;
	color: #FFFFFF;
}
.list-contains {
	display: flex;
	flex-direction: column;
	align-items: center;
}
.list-body {
	width: 80%;
	border-radius: 30upx;
	margin-top: 10upx;
	background-color: #142a2e;
}
</style>
