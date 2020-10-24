<template>
	<view class="investment-container">
		<!-- 导航栏 -->
		<view class="nav-bar">
			<text class="nav-bar-item" :class="{ 'current-item': currentPlace == 0 }" @click="currentPlace = 0">市场</text>
			<text class="nav-bar-item" :class="{ 'current-item': currentPlace == 1 }" @click="currentPlace = 1">持有</text>
		</view>
		<!-- 主页面 -->
		<swiper class="swiper" :duration="200" @change="swiperChange" :current="currentPlace">
			<swiper-item class="swiper-item">
				<!-- 5个按钮 -->
				<view class="button-contain">
					<view class="button-contain-item" v-for="item in buttonContains" @click="navTo(item.url)" :key="item.id">
						<image :src="item.src" mode="widthFix"></image>
						<view>
							<text>{{ item.title }}</text>
						</view>
					</view>
				</view>
				<!-- 项目详情列表 -->
				<view class="item-list">
					<huaqiGameList
						v-for="item in marketData"
						@clicked="navTo('../itemDetail/itemDetail?id='+item.id)"
						:title="item.title"
						:rank="item.rank"
						:interestRate="item.interestRate"
						:background="item.background"
					/>
				</view>
			</swiper-item>
			<swiper-item class="swiper-item"></swiper-item>
		</swiper>
	</view>
</template>

<script>
import huaqiGameList from '../../components/huaqi-game-list/huaqi-game-list.vue';
export default {
	components: {
		huaqiGameList
	},
	data() {
		return {
			// 标记市场还是持有 0:市场 1：持有
			currentPlace: 0,
			buttonContains: [
				{
					id: 1,
					src: '../../static/common-icons/new.png',
					title: '新发',
					url: '../newPub/newPub'
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
/* swiper */
swiper {
	width: 100%;
	height: 100vh;
	overflow: scroll;
}
.swiper-item {
	width: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	overflow: scroll;
}
/* 导航栏 */
.nav-bar {
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	width: 100vw;
	font-size: 15px;
	font-weight: 900;
	padding-top: 24upx;
	height: 9vh;
	color: #fff;
	background-color: #112628;
	position: sticky;
	top: 0;
	z-index: 1;
}
.nav-bar-item {
	padding: 0 40upx;
}
.current-item {
	font-size: 20px;
}
/* button部分css */
.button-contain {
	display: flex;
	flex-direction: row;
	width: 90%;
	justify-content: center;
	align-items: center;
	text-align: center;
	box-shadow: 10px 10px 10px #000;
	border-radius: 40upx;
	background-color: #193745;
	padding: 10upx;
	margin-top: 80upx;
}
.button-contain-item {
	flex: 1;
}
.button-contain-item image {
	width: 60%;
}
/* list */
.item-list {
	margin-top: 50upx;
}
</style>
