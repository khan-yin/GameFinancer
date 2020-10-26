<template>
	<view class="contains">
		<!-- 导航栏 -->

		<view class="nav-bar">
			<text class="nav-bar-item" :class="{ 'current-item': currentPlace == 0 }" @click="currentPlace = 0">咨询</text>
			<text class="nav-bar-item" :class="{ 'current-item': currentPlace == 1 }" @click="currentPlace = 1">积分</text>
		</view>

		<swiper id="swiper-total" :duration="200" @change="swiperChange" :current="currentPlace">
			<swiper-item class="swiper-item-total">
				<view class="news-list" v-for="(item,index) in newList" :key="index">
					<huaqiNewsItem :title="item.title"
					:like="item.like" 
					:comments="item.comments"
					:time="item.time" 
					:author="item.author"
					:imgUrl="item.imgUrl"
					:isTop="item.isTop"></huaqiNewsItem>
				</view>
			</swiper-item>
			
			<swiper-item class="swiper-item-total">
				<view class="search-box">
					<searchBar></searchBar>
				</view>
				<huaqiCombineSwiper :picture="swiper.picture" :onlySwiper="true" />
				<view class="class-box">
					<view class="itemline" >
						<view class="item" v-for="item in line1">
							<image class="icon" src="../../static/common-icons/wxicon.png" mode="widthFix"></image>
							<text>{{item}}</text>
						</view>
					</view>
					<view class="itemline" >
						<view class="item" v-for="item in line2">
							<image class="icon" src="../../static/common-icons/wxicon.png" mode="widthFix"></image>
							<text>{{item}}</text>
						</view>
					</view>
				</view>
				<huaqiPaymentItemList :title="listBox[0].title"   :background="listBox[0].background"  />
				<huaqiPaymentItemList :title="listBox[1].title"   :background="listBox[1].background"  />
				
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
import searchBar from '../../components/searchBar/searchBar.vue'
import huaqiCombineSwiper from '../../components/huaqiCombineSwiper/huaqiCombineSwiper.vue';
import huaqiNewsItem from '../../components/huaqiNewsItem/huaqiNewsItem.vue'
import huaqiPaymentItemList from '../../components/huaqi-payment-item-list/huaqi-payment-item-list.vue'

export default {
	components:{
		huaqiCombineSwiper,
		searchBar,
		huaqiNewsItem,
		huaqiPaymentItemList
	},
	data() {
		return {
			currentPlace: 0,
			listBox:[
				{
					title:"限定发行",
					background:'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				},
				{
					title:"每日抽奖",
					background:'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg'
				}
			],
			line1: ["RPG","ACT","AVG","SLG"],
			line2: ["RTS","FTG","STG","MORE"],
			newList:[
				{
					title:"xxxxx",
					like: 999,
					comments:999,
					time: "2020/10/20",
					author: "xxx",
					imgUrl: "https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg",
					isTop:true
				},
				{
					title:"xxxxx",
					like: 999,
					comments:999,
					time: "2020/10/20",
					author: "xxx",
					imgUrl: "https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg",
					isTop:true
				},
				{
					title:"xxxxx",
					like: 999,
					comments:999,
					time: "2020/10/20",
					author: "好好好",
					imgUrl: "https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg",
					isTop:false
				},
				{
					title:"xxxxx",
					like: 999,
					comments:999,
					time: "2020/10/20",
					author: "xxx",
					imgUrl: "https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg",
					isTop:false
					
				},
				{
					title:"xxxxx",
					like: 999,
					comments:999,
					time: "2020/10/20",
					author: "xxx",
					imgUrl: "https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg",
					isTop:false
					
				},
			],
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
		}
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
	/* align-items: center; */
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

.search-box{
	position: sticky;
	top:0upx;
	z-index: 1;
	width: 100%;
	background-color: #00191E;
	margin-bottom: 50upx;
	
}

.news-list{
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	justify-content: center;
	width: 96%;
	height: 250upx;
}

.class-box{
	display: flex;
	flex-direction: column;
	width: 90%;
	justify-content: center;
	text-align: center;
	margin-top: 20upx;
}

.itemline{
	display: flex;
	flex-direction: row;
}

.item{
	width: 25%;
}

.icon{
	width: 160upx;
}
</style>
