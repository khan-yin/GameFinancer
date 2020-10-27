<template>
	<view class="contains">
		<view class="userCard">
			<!-- 头像 -->
			<view><image @click="chooseImg" class="ImgClass" :src="userimgUrl" mode="widthFix"></image></view>
			<!-- 登录后显示名称，id -->
			<view v-if="isLogin" class="LoginInfo">
				<view class="user-name">
					<image class="icon" src="../../static/profile/usericon.png"></image>
					<view style="font-size: 40upx;">- {{ username }}</view>
				</view>

				<view class="idstyle">game financer ID:{{ userId }}</view>
			</view>

			<view v-else class="LoginInfo" @click="navTo('../Login/Login')">登录</view>
		</view>

		<view class="box">
			<view class="box-item">账户</view>

			<view class="box-item" style="background-color: #24393F;">我的持债</view>

			<view class="box-item" style="background-color: #192E34;">众筹订单</view>
		</view>

		<view class="box">
			<view class="box-item">道具订单</view>
			<view class="box-item" style="background-color: #24393F;">周边订单</view>
			<view class="box-item">我的游戏账号</view>
		</view>

		<view class="box">
			<view class="box-item">成为制作人</view>
			<view class="box-item" style="background-color: #24393F;">我制作的项目</view>
			<view class="box-item">设置</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			authorization: '',
			isLogin: false,
			username: '血小板',
			userId: '0121810880322',
			userimgUrl: '../../static/profile/userImg.png' //"https://khany.top/assets/xxb.jpg"//
		};
	},
	methods: {
		navTo(url) {
			console.log(url);
			if (url) {
				uni.navigateTo({
					url: url,
					animationType: 'slide-in-right',
					animationDuration: 200
				});
			}
		},
		// 头像设置
		chooseImg() {
			uni.chooseImage({
				count: 1,
				success: res => {
					console.log(res.tempFiles[0]);
					this.userimgUrl = res.tempFiles[0].path;
					uni.saveFile({
						tempFilePath: this.userimgUrl,
						success: res => {
							console.log(res.savedFilePath);
							this.userimgUrl = res.savedFilePath;
							uni.setStorageSync('userimgUrl', this.userimgUrl);
						},
						fail: err => {
							console.log(err);
						}
					});
				}
			});
		}
	},
	onShow() {
		// uni.clearStorage('authorization')
		let Authorization = uni.getStorageSync('authorization');
		console.log(Authorization);
		if (Authorization) {
			this.authorization = Authorization;
			uni.request({
				url: 'http://server.kingfish404.cn/main/getUserInfo',
				method: 'POST',
				header: {
					Authorization
				},
				success: res => {
					console.log(res);
					this.isLogin = true;
					if (res.data.code == 0) {
						this.username = res.data.username;
						this.userId = res.data.useremail;
						this.userimgUrl = uni.getStorageSync('userimgUrl');
						if (!this.userimgUrl) {
							this.userimgUrl = '../../static/profile/userImg.png';
						}
					}else{
						this.navTo('../Login/Login')
					}
				}
			});
		}
	}
};
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
	background-color: #20373b;
	color: #ffffff;
	padding: 10upx;
	border-radius: 5upx;
	font-size: 25upx;
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
	opacity: 0.7;
	box-shadow: 0 0 70upx rgb(69, 81, 91);
}

.LoginInfo {
	display: flex;
	flex-direction: column;
	justify-content: center;
	width: 430upx;
	height: 300upx;
	vertical-align: middle;
	align-items: center;
	font-size: 80upx;
}

.user-name {
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
}

.user-name > * {
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
	box-shadow: 0upx 0upx 5upx 5upx #0f272b;
}

.box-item {
	text-align: left;
	vertical-align: middle;
	height: 34%;
	width: 95%;
	padding-left: 5%;
	background-color: #152a30;
	line-height: 66upx;
}
</style>
