<template>
	<view class="set-button">
		<view class="box" v-for="item in titles">
			<view class="button-box">
				{{item}}
			</view>
			<image src="../mapList/static/open_active.png" mode="widthFix"></image>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			titles:{
				type:Array,
				default:()=>["阶段","利率"]
			}
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style scoped>
.set-button{
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items: center;
	text-align: center;	
	background-color:#10272B;
	width: 90%;
	height: 80upx;
	border-radius: 40upx;
	margin-top: 40upx ;
	box-shadow: 0px 0px 0 10px #071F24;
	color: #FFFFFF;
}
.box{
	flex: 1;
	display: flex;
	flex-direction: row;
	align-items: center;
	text-align: center;
	justify-content: center;	
}
.box image{
	width: 50upx;
}
</style>
