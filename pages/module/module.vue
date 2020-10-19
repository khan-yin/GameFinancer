<template>
	<view class="contains">
		<searchBar class="search-box" />
		<view class="list-contains">
			<view class="list-contains-item">
				<view class="list-item-body" v-for="item in marketData" >
					<view class="up-box">
						<text>{{item.classType}}</text>
						<text>{{item.avgRate}}</text>
					</view>
					<huaqiGameList :title="item.title" :interestRate="item.interestRate" :background="item.background" />
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import huaqiGameList from '../../components/huaqi-game-list/huaqi-game-list.vue';
import searchBar from '../../components/searchBar/searchBar.vue';
export default {
	components: {
		huaqiGameList,
		searchBar
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
					classType:'RPG',
					avgRate:21
				},
				{
					id: 2,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 2,
					classType:'RPG',
					avgRate:21
				},
				{
					id: 3,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 3,
					classType:'RPG',
					avgRate:21
				},
				{
					id: 4,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 4,
					classType:'RPG',
					avgRate:21
				},
				{
					id: 5,
					title: '项目一',
					interestRate: 16,
					background: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
					rank: 5,
					classType:'RPG',
					avgRate:21
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
	width: 100%;
}
.search-box {
	margin-top: 40upx;
	margin-bottom: 20upx;
}
</style>
