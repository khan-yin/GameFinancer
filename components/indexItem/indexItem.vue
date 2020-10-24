<template>
	<view class="index-item-contains" @mouseenter.native="changebtn" @mouseleave.native="changebtn">
		<view class="contains-index">
			<huaqiCombineSwiper :onlySwiper="true" :picture="picture" />
			<view class="contains-small">
				<view class="contains-name-button" :class="{ active: hover }">
					<view class="game-name">{{ gameName }}</view>
					<image :src="btnUrl" mode="widthFix"></image>
				</view>
				<view class="descrition" style="color: white;padding: 5%;">介绍: {{ describe }}</view>
			</view>
		</view>
	</view>
</template>

<script>
import huaqiCombineSwiper from '../huaqiCombineSwiper/huaqiCombineSwiper.vue';
export default {
	components: {
		huaqiCombineSwiper
	},
	props: {
		picture: {
			type: Array // {{src:ddd,id:ddd}}
		},
		describe: {
			type: String,
			default: ''
		},
		gameName: {
			type: String
		}
	},
	data() {
		return {
			btnUrl: '../../static/index/toDetail.png',
			hover: false
		};
	},
	mounted() {},
	methods: {
		changebtn() {
			this.hover = !this.hover;
			this.btnUrl = this.hover === true ? '../../static/index/toDetailClicked.png' : '../../static/index/toDetail.png';
		}
	}
};
</script>

<style scoped>
.index-item-contains {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-content: center;
	text-align: center;
	width: 100vw;
	background-color: #00191e;
}
.contains-index{
	width: 100%;
}
.contains-small{
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
	width: 100%;
}
.contains-name-button{
	width: 50%;
	display: flex;
	flex-direction:row;
	justify-content: center;
	align-items: center;
	text-align: center;
	background-color: #0D2331;
}
	
.contains-name-button image{
	width: 80upx;
	
}
.descrition{
	width: 90%;
}
</style>
