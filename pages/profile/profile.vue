<template>
	<view class="contains">
		<view class="userCard">
			<!-- 头像 -->
			<view>
				<image  class="ImgClass" src="../../static/profile/userImg.png" mode="widthFix"></image>
			</view>
			<!-- 登录后显示名称，id -->
			<view v-if="isLogin" class="LoginInfo">
				<view class="user-name">
					<image class="icon" src="../../static/profile/usericon.png"></image>
					<view>
						{{username}}
					</view>
				</view>

				<view class="idstyle">
					game financer ID:{{userId}}
				</view>
			</view>

			<view v-else class="LoginInfo">
				登录
			</view>

		</view>

		<view class="box">
			<view class="box-item">
				账户
			</view>

			<view class="box-item">
				我的持债
			</view>

			<view class="box-item">
				众筹订单
			</view>

		</view>



		<view class="box">
			<view class="box-item">
				道具订单
			</view>
			<view class="box-item">
				周边订单
			</view>
			<view class="box-item">
				我的游戏账号
			</view>
		</view>

		<view class="box">
			<view class="box-item">成为制作人</view>
			<view class="box-item">我制作的项目</view>
			<view class="box-item">设置</view>
		</view>



	</view>
</template>

<script>
	export default {
		data() {
			return {
				isLogin: true,
				username: "xxx",
				userId: "xxxxx",
				userimgUrl: "",
			}
		},
		methods: {

		}
	}
</script>

<style>
	.contains {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		text-align: center;

	}

	.idstyle {
		margin-top: 40upx;
		background-color: #20373B;
		color: #FFFFFF;
		padding: 10upx;
		border-radius: 5upx;
		font-size: 20upx;
	}

	.icon {
		width: 50upx;
		height: 50upx;
	}

	.userCard {
		display: flex;
		flex-direction: row;
		text-align: center;
	}

	.ImgClass {
		position: relative;
		top: 30upx;
		height: 250upx;
		width: 250upx;
		border-radius: 50%;
	}

	.LoginInfo {
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 430upx;
		height: 300upx;
		vertical-align: middle;
		align-items: center;
	}

	.user-name {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		text-align: center;
	}

	.user-name>* {
		padding: 6upx;
	}

	.box {
		border-radius: 10upx;
		margin: 10upx;
		display: flex;
		flex-direction: column;
		align-items: center;
		height: 200upx;
		width: 600upx;
		/* background-color: #007AFF; */
		/* border: solid 1upx #007AFF; */
		box-shadow: 0upx 0upx 5upx 5upx #0F272B;
	}


	.box-item {
		text-align: left;
		vertical-align: middle;
		height: 34%;
		width: 95%;
		padding-left: 5%;

		background-image: linear-gradient(to right, #152A30, #0F2226);
		line-height: 66upx;
	}
</style>
