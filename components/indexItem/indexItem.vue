<template>
	<view class="indexItem-contains" @mouseenter.native="changebtn" @mouseleave.native="changebtn">
		<view style="background-color: #001418; margin: 0 auto; width: 90%;">
			<huaqiCombineSwiper onlySwiper="true" :picture="picture" />
			<view class="contains-small">
				<view class="contains-Namebutton" :class="{ active: hover }">
					<view style="margin-left: 100upx; padding-top: 0; color: white; font-family: STYuanti;">{{ gameName }}</view>
					<image :src="btnUrl" style="margin-top: -10upx; width: 75upx; height: 75upx; "></image>
				</view>
				<view style="color: white; font-size: small; font-family: STYuanti;">介绍: {{ describe }}</view>
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
.indexItem-contains {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-content: center;
	text-align: center;
	width: 100%;
	background-color: #00191e;
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
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
	background-color: #001418;
	border-radius: 20upx;
}

.contains-Namebutton {
	/* padding-bottom: 0; */
	display: flex;
	flex-direction: row;
	justify-content: space-evenly;
	text-align: center;
	background-color: #0d2331;
	width: 70%;
	height: 60upx;
	line-height: 50upx;
	border-radius: 30upx;
	margin: 10upx;
}

.active {
	background-color: #444d4a;
}
</style>
