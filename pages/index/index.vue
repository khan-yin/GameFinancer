<template>
	<view class="index-contain">
		<view class="index-body"><image src="../../static/common-icons/playLogo.png" class="cell-pic" mode="widthFix"></image></view>
		<image @click="start" class="icon" src="../../static/common-icons/click.png" mode="widthFix"></image>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	methods: {
		start() {
			uni.switchTab({
				url: '../home/home'
			});
		}
	}
};
</script>

<style scoped>

.index-contain {
	background-image: url(../../static/background/index.png);
	background-size: 100%;
	background-repeat: no-repeat;
	background-color: #0b1e24;
	width: 100vw;
	height: 100vh;
	color: #fff;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
}
.index-body {
	width: 100%;
}
.cell-pic {
	width: 70%;
	position: relative;
	top: -50upx;
}

.icon {
	position: fixed;
	bottom: 10vh;
	width: 15%;
}
</style>
