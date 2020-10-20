<template>
	<view class="contains">
		<searchBar class="search-box" />
		<view class="list-contains">
			<view class="list-body" v-for="item in marketData">
				<view class="up-box">
					<view class="body-box">
						<view class="body-font">
							<text class="font-avg1">{{ item.classType }}</text>
							<view class="font-avg3">平均利率：<text class="text-rate">{{ item.avgRate }}%</text></view>
						</view>
						<huaqiGameList :title="item.title" :interestRate="item.interestRate" :background="item.background" />
						<view class="pic">
							<image src="../../static/common-icons/fire.png" mode="widthFix"></image>
							<text>立刻买入</text>
						</view>
					</view>
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
.body-box {
	background-color: #060a0b;
	border-radius: 30upx;
}
.up-box {
	padding: 15upx 15upx;
}
.font-avg1{
	font-size:40upx;
	color:#B2B9BC;
}
.body-font{
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items: center;
	padding-top: 20upx;
}
.body-font>*{
	flex: 1;
}
.text-rate{
	color:#B79F67;
	font-size: 40upx;
}
.pic{
	position: fixed;
	left: 0;
}
.pic image{
	width: 180upx;
}
</style>
