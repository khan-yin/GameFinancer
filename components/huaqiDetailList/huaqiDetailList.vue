<template>
	<view class="contains">
		<!-- 整体栏目 -->
		<view class="game-list-box" @click="$emit('clicked')">
			<image :src="background" style="display: block;position: absolute;left: 10%;"></image>
			<view class="game-detail">
				<text style="color: #FFFFFF; font-size: 40upx;">{{ title }}</text>
				<view class="rate">
					<view class="rate-box" style="color: #fff;">利率</view>
					<view class="rate-detail" style="color: #FFD17C;font-size: 30upx;">{{ interestRate }}%</view>
				</view>
				<view class="rank">
					<view class="rank-box" style="color: #fff;">同类利率均值</view>
					<view class="rank-detail" style="color: #FFD17C;font-size: 30upx;font-weight: 900;">{{ avgRate }}%</view>
				</view>
				<view class="rank">
					<view class="rank-box" style="color: #fff;">排名</view>
					<view class="rank-detail" style="color: #FFD17C;font-size: 30upx;font-weight: 900;">{{ rank }}</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	props: {
		title: {
			default: '',
			type: String
		},
		rank: {
			type: String
		},
		interestRate: {
			type: String
		},
		background: {
			type: String
		},
		avgRate: {
			type: String
		}
	},
	data() {
		return {};
	},
	mounted() {
		console.log(this.avgRate)
	}
};
</script>

<style scoped>
.contains {
	display: flex;
	flex-direction: row;
	width: 89%;
	height: 150upx;
	padding: 30upx 40upx;
	border-radius: 40upx;
}
.game-list-box {
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	/* 	background-color: #FFFFFF; */
}
.game-list-box image {
	width: 300upx;
	height: 150upx;
	border-radius: 100upx 0 0 100upx;
	box-shadow: 10px 0px 10px 0px rgba(17, 38, 40, 0.9);
}
.game-detail {
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	/* background-color: rgba(25,55,69,1); */
	background-image: linear-gradient(to right, rgba(17, 38, 40, 0.1), rgba(25, 55, 69, 1));
	height: 150upx;
	width:90%;
	/* position: relative; */
	/* left: -10%; */
	z-index: 1;
	border-radius: 100upx;
	/* box-shadow: -20px 0px 10px  rgba(25,55,69,1); */
}
.game-detail text {
	font-size: 18px;
	color: #83959e;
	padding-right: 40upx;
}
.game-detail > * {
	padding-right: 20upx;
}
/* #FFD17C */
</style>
