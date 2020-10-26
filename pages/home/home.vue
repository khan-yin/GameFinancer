<template>
	<view class="contains">
		<!-- 导航栏 -->

		<view class="nav-bar">
			<text class="nav-bar-item" :class="{ 'current-item': currentPlace == 0 }" @click="currentPlace = 0">端游</text>
			<text class="nav-bar-item" :class="{ 'current-item': currentPlace == 1 }" @click="currentPlace = 1">手游</text>
		</view>

		<swiper id="swiper-total" :duration="200" @change="swiperChange" :current="currentPlace">
			<swiper-item class="swiper-item-total">
				<navBarItem></navBarItem>
				<view class="box-contains">
					<view class="list-contains" v-for="(item, index) in swipers" :key="index">
						<indexItem :picture="item.picture" :describe="item.describe" :gameName="item.gameName" />
						<!-- 加判断，使得最后一个没有底栏 -->
						<view class="line-bottom" v-if="index !== swipers.length - 1"></view>
					</view>
				</view>
			</swiper-item>
			
			<swiper-item class="swiper-item-total">
				<navBarItem></navBarItem>
				<view class="box-contains">
					<view class="list-contains" v-for="(item, index) in swipers" :key="index">
						<indexItem :picture="item.picture" :describe="item.describe" :gameName="item.gameName" />
						<!-- 加判断，使得最后一个没有底栏 -->
						<view class="line-bottom" v-if="index !== swipers.length - 1"></view>
					</view>
				</view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
import indexItem from '../../components/indexItem/indexItem.vue';
import navBarItem from '../../components/navbar-game-item/navbar-game-item.vue';

export default {
	components: {
		indexItem,
		navBarItem
	},
	data() {
		return {
			currentPlace: 0,
			swipers: [
				{
					picture: [
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						}
					],
					describe:
						'位于提瓦特大陆东方的富饶港湾。傲然矗立的山麓与石林、广袤的平原与生机勃勃的河滩共同构成了璃月的丰富地貌，在四季分明的气候下焕发出多彩的风华。山石奇景间，又埋藏了多少岩之魔神的古老馈赠等待着人们发掘呢？',
					gameName: '原神'
				},
				{
					picture: [
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						}
					],
					describe: 'xxxxxx',
					gameName: '原神人'
				},
				{
					picture: [
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						}
					],
					describe: 'xxxxxx',
					gameName: '原神人'
				},
				{
					picture: [
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						},
						{
							src: 'https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302',
							id: 12
						}
					],
					describe: 'xxxxxx',
					gameName: '原神人'
				}
			]
		};
	},
	methods: {
		swiperChange(e) {
			console.log(e.detail.current);
			this.currentPlace = e.detail.current;
		}
	}
};
</script>

<style scoped>
.contains {
	width: 100%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
}
.investment-container {
	width: 100%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
}
/* swiper */
#swiper-total {
	width: 100%;
	height: 100vh;
	overflow: scroll;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	justify-content: center;
}
.swiper-item-total {
	width: 100%;
	overflow: scroll;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	justify-content: center;
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
.line-bottom {
	margin: 10upx auto;
	width: 70%;
	height: 1px;
	border-top: solid #a6c0d6 3upx;
}
.box-contains {
	overflow: scroll;
}
.game-classify {
}
</style>
