<template>
	<view class="index-item-contains">
		<view class="contains-index">
			<huaqiCombineSwiper :onlySwiper="true" :picture="picture" />
			<view class="contains-small">
				<view class="contains-name-button">
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
		};
	},
	mounted() {},
	methods: {
		
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
	border-radius: 10upx;
}
	
.contains-name-button image{
	width: 80upx;
	border-radius: 10upx;
}
.descrition{
	width: 90%;
}

.index-item-contains:hover  .contains-name-button{
	background-color: #444D4A;
}

.index-item-contains:hover  .contains-name-button image{
	content: url(../../static/index/toDetailClicked.png);
}
</style>
