<template>
	<view class="contains">
		<!-- <view  v-if="!onlySwiper" class="contains-button">{{ buttonTitle }}</view> -->
		<swiper indicator-color="white" indicator-active-color="#FFD66C" :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item v-for="(item, idx) in picture">
				<view class="swiper-item">
					<image :src="item.src" mode="widthFix" ></image>
					<!-- <view style="color: #1D3245; width: 90%; height: 30upx; "></view> -->
				</view>
				
			</swiper-item>
		</swiper>
		<view class="contains-small" v-if="!onlySwiper" >
			<view class="contains-description" style="color: white">{{ gameName }}</view>
			<image src="../../static/index/toDetail.png" style="width: 75upx; height: 75upx;"></image>
		</view>
		<view style="color: white;">介绍: {{describle}}</view>
		<view class="line-bottom"></view>
	</view>
</template>

<script>
export default {
	props: {
		picture: {
			type: Array // {{src:ddd,id:ddd}}
		},
		buttonTitle: {
			type: String
		},
		gameName: {
			type: String
		},
		onlySwiper:{
			type:Boolean,
			default:false
		}
	},
	data() {
		return {};
	},
	mounted() {
		console.log(this.picture[0]);
	}
};
</script>

<style scoped>
.
	
	
.contains {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-content: center;
	text-align: center;
	width: 90%;
	background-color: #00191E;
}
.contains > * {
	margin-top: 30upx;
}
.contains-button {
	background-color: #031113;
	width: 30%;
	height: 40upx;
	padding: 10upx 0;
	margin-left: 40upx;
	border-radius: 30upx;
	box-shadow: 2upx -2upx 4upx 4upx #49595c;
}
.swiper-item image {
	border-radius: 20upx 20upx 0 0;
}
.contains-small {
	margin: 10upx 80upx;
	/* width: 85%; */
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	background-color: #0D2331;
	border-radius: 20upx;
}
.contains-description {
	/* background-color: #0d2330; */
	width: 35%;
	height: 50upx;
	line-height: 50upx;
	border-radius: 30upx;
}

.line-bottom {
		margin: 10upx auto;
		width: 70%;
		height: 1px;
		border-top: solid #A6C0D6 5upx;
}
</style>
