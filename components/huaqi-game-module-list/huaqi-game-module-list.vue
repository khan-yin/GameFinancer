<template>
	<view class="up-box">
		<view class="body-box">
			<view class="body-font">
				<text class="font-avg1">{{ classType }}</text>
				<view class="font-avg3">平均利率：<text class="text-rate">{{ avgRate }}%</text></view>
			</view>
			<huaqiGameList :title="title" :interestRate="interestRate" :background="background" />
		</view>
		<view class="pic">
			<text>立刻买入</text>
		</view>
	</view>
</template>

<script>
import huaqiGameList from '../huaqi-game-list/huaqi-game-list.vue';
export default {
	props:{
		classType:{
			type:String
		},
		avgRate:{
			type:Number
		},
		title:{
			default:"",
			type:String
		},
		rank:{
			type:Number
		},
		interestRate:{
			type:Number
		},
		background:{
			type:String
		},
		
	},
	data() {
		return {};
	},
	components: {
		huaqiGameList
	}
};
</script>

<style scoped>

.body-box {
	background-color: #060a0b;
	border-radius: 30upx;
	margin-top:10upx ;
}
.up-box {
	padding: 15upx 15upx;
	position: relative;
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
	display: block;
	position: absolute;
	z-index: 1;
	top: 100upx;
	left: 76%;
	background-image: url("../../static/common-icons/fire.png");
	width: 150upx;
	height: 150upx;
	color: #FFFFFF;	
	background-size: 100%;
	display: flex;
	font-size: 34upx;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
	/* background-color: #007AFF; */
}
.pic text{
	margin-top: 35upx;
	width: 90upx;
}
</style>
