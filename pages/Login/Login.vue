<template>
	<view class="index-contain">
		<view class="index-body">
			<image src="../../static/common-icons/playLogo.png" class="cell-pic" mode="widthFix"></image>
		</view>
		
		<view class="login-contain" v-if="status">
			<view class="inputitem">
			<text>邮箱：</text>
			<input class="inputstyle" type="text" value="" />
			</view>
			<view class="inputitem">
			<text>密码：</text>
			<input class="inputstyle" type="password" value="" />
			</view>
			<view class="button-contains">
				<button type="default" class="btnstyle" @click="doLogin">登录</button>
				<button type="default" class="btnstyle"  @click="change">注册</button>
			</view>
		</view>
		<view class="sign-contain"  v-else>
			<view class="inputitem">
				<text>用户名：</text>
				<input class="inputstyle" type="text" value="" />
			</view>
			
			<view class="inputitem">
			<text>名字：</text>
			<input class="inputstyle" type="text" value="" />
			</view>
			
			<view class="inputitem">
			<text>姓氏：</text>
			<input class="inputstyle" type="text" value="" />
			</view>
			
			<view class="inputitem">
			<text>电子邮箱：</text>
			<input class="inputstyle" type="text" value="" />
			</view>
			
			<view class="inputitem">
			<text>密码：</text>
			<input class="inputstyle" type="password" value="" />
			</view>
			
			<view class="inputitem">
			<text>确认密码：</text>
			<input class="inputstyle" type="password" value="" />
			</view>
			
			<view class="button-contains">
				<button class="btnstyle" @click="change">返回</button>
				<button class="btnstyle" @click="doSignup">注册</button>
			</view>
		</view>
		
		
	</view>
</template>

<script>
export default {
	data() {
		return {
			status:true,
		};
	},
	methods: {
		start() {
			uni.switchTab({
				url: '../home/home'
			});
		}
	},
	methods:{
		change(){
			this.status=!this.status;
		},
		doLogin(){
			
		},
		doSignup(){
			
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
	/* justify-content: center; */
	align-items: center;
	text-align: center;
}
.index-body {
	margin-top: 100upx;
	width: 100%;
	height: 300upx;
	margin-bottom: 10upx;
	/* background-color: #007AFF; */
}
.cell-pic {
	width: 70%;
/* 	position: relative;
	top: -400upx; */
}

.login-contain{
	align-items: center;
	justify-content: center;
	width: 90%;
	height: 300upx;
	display: flex;
	flex-direction: column;
	background-color: #6c6d60;
	border-radius: 10upx;
	opacity: 0.6;
}


.sign-contain{
	align-items: center;
	justify-content: center;
	width: 90%;
	height: 600upx;
	display: flex;
	flex-direction: column;
	background-color: #6c6d60;
	border-radius: 10upx;
	opacity: 0.6;
}

.inputitem{
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	width: 90%;
	height: 70upx;
	font-size: 15px;
	line-height: 70upx;
	vertical-align: middle;
	margin-bottom: 20upx;
	color: #000000;
}

.inputstyle{
	background-color: #EBEBEB;
	height: 70upx;
	width: 70%;
	border: solid 5upx #000000;
	border-radius: 10upx;
	direction: ltr;
	text-align: left;
}

.button-contains{
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	width: 80%;
	text-align: center;
}

.btnstyle{
	width: 200upx;
	height: 50upx;
	background-color: #ffc680;
	border-radius: 20upx;
	/* vertical-align: middle; */
	line-height: 50upx;
}
</style>
