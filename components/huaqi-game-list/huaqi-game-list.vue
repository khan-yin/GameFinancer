<template>
	<view class="contains">
		<!-- 皇冠 -->
		<view class="title-show" v-if="rank<=3">
			<image v-if="rank==1" src="./static/1.png" mode="widthFix"></image>
			<image v-if="rank==2" src="./static/2.png" mode="widthFix"></image>
			<image v-if="rank==3" src="./static/3.png" mode="widthFix"></image>
		</view>
		<!-- 整体栏目 -->
		<view class="game-list-box" @click="$emit('clicked')">
			<image :src="background" ></image>
			<view class="game-detail">
				<text>{{title}}</text>
				<view class="rate">
					<view class="rate-box" style="color: #fff;">
						利率
					</view>
					<view class="rate-detail" style="color: #FFD17C;font-size: 13px;">
						{{interestRate}}%
					</view>
				</view>
					<view class="rank">
						<view class="rank-box" style="color: #fff;">
							排名
						</view>
						<view class="rank-detail"  style="color: #FFD17C;font-size: 25px;font-weight: 900;">
							{{rank}}
						</view>
					</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
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
			return {
			};
		}
	}
</script>

<style scoped>
.contains{
	display: flex;
	flex-direction: row;
	width: 100%;
	height: 150upx;
	padding: 30upx 40upx;
	border-radius: 40upx;
}
.game-list-box{
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
/* 	background-color: #FFFFFF; */
}
.game-list-box image{
	width: 300upx;
	height: 150upx;
	border-radius: 100upx 0 0 100upx;
	box-shadow: 10px 0px 10px 0px rgba(17,38,40,0.9);
}
.game-detail{
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	/* background-color: rgba(25,55,69,1); */
	background-image: linear-gradient(to right,rgba(17,38,40,0.9),rgba(25,55,69,1));
	height: 150upx;
	width: 380upx;
	position: relative;
	left: -60upx;
	border-radius:0 100upx 100upx 0;
	/* box-shadow: -20px 0px 10px  rgba(25,55,69,1); */
}

.game-detail text{
	font-size: 18px;
	color: #83959E;
	padding-right: 40upx;
}
.game-detail>*{
	padding-right: 20upx;
}

.title-show{
	/* position:fixed; */
	display: block;
	position:absolute;
	left: 20px;
	z-index: 1;
}
.title-show image{
	width: 70upx;
}
/* #FFD17C */
</style>
