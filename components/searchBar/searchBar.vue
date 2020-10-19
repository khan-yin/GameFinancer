<template>
	<view class="search-bar">
		<!-- 搜索框 -->
		<uni-search-bar id="uni-search-bar" @confirm="" @input="" />
		<view class="contains-box">
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style scoped>
.search-bar{
	width: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
}
#uni-search-bar{
	width:90%;
	background-color: #001418;
	color: #fff;
}
</style>
