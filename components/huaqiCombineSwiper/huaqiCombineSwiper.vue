<template>
	<view class="contains">
		<view class="contains-button">{{ buttonTitle }}</view>
		<swiper indicator-color="white" indicator-active-color="#FFD66C" :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item v-for="(item, idx) in picture">
				<view class="swiper-item"><image :src="item.src" mode="widthFix"></image></view>
			</swiper-item>
		</swiper>
		<view class="contains-small">
			<view class="contains-description">{{ combineName }}</view>
		</view>
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
		combineName: {
			type: String
		}
	},
	data() {
		return {};
	}
};
</script>

<style scoped>
.contains {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-content: center;
	text-align: center;
	width: 100%;
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
.contains-small{
	width: 100%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
}
.contains-description {
	background-color: #0d2330;
	width: 35%;
	height: 50upx;
	line-height: 50upx;
	border-radius: 30upx;
}
</style>
