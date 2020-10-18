<template>
	<view class="investment-container">
		<!-- 导航栏 -->
		<view class="nav-bar">
			<text class="nav-bar-item" :class="{'current-item':currentPlace==1}">市场</text>
			<text class="nav-bar-item" :class="{'current-item':currentPlace==2}">持有</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// 标记市场还是持有 1:市场 2：持有
				currentPlace:1
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.nav-bar{
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	width: 100vw;
	font-size: 15px;
	font-weight: 900;
	padding-top:24upx;
	height: 9vh;
	color: #fff;
	background-color: #2D2E33;
}
.nav-bar-item{
	padding:0 40upx;
}
.current-item{
	font-size: 20px;
}
</style>
