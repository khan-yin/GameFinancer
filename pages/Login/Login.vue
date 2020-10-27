<template>
	<view class="index-contain">
		<view class="index-body"><image src="../../static/common-icons/playLogo.png" class="cell-pic" mode="widthFix"></image></view>
		<view class="login-contain" v-if="status">
			<view class="inputitem">
				<text>邮箱：</text>
				<input class="inputstyle" type="text" v-model="email" />
			</view>
			<view class="inputitem">
				<text>密码：</text>
				<input class="inputstyle" type="password" v-model="password" />
			</view>
			<view class="button-contains">
				<button type="default" class="btnstyle" @click="doLogin">登录</button>
				<button type="default" class="btnstyle" @click="change">注册</button>
			</view>
		</view>
		<view class="sign-contain" v-else>
			<view class="inputitem">
				<text>用户名：</text>
				<input v-model="username" class="inputstyle" type="text" />
			</view>

			<view class="inputitem">
				<text>名字：</text>
				<input v-model="name" class="inputstyle" type="text" value="" />
			</view>

			<view class="inputitem">
				<text>姓氏：</text>
				<input v-model="lastName" class="inputstyle" type="text" value="" />
			</view>

			<view class="inputitem">
				<text>电子邮箱：</text>
				<input v-model="email" class="inputstyle" type="text" value="" />
			</view>

			<view class="inputitem">
				<text>密码：</text>
				<input v-model="password" class="inputstyle" type="password" value="" />
			</view>

			<view class="inputitem">
				<text>确认密码：</text>
				<input v-model="confirmPassword" class="inputstyle" type="password" value="" />
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
			status: true,
			username: 'root',
			password: '123456',
			name: 'x',
			lastName: 'a',
			email: 'codingax@foxmail.com',
			confirmPassword: '123456'
		};
	},
	methods: {
		start() {
			uni.switchTab({
				url: '../home/home'
			});
		}
	},
	methods: {
		change() {
			this.status = !this.status;
			uni.setNavigationBarTitle({
				title: this.status ? '登录' : '注册'
			});
			console.log(this.status);
		},
		async doLogin() {
			console.log(this.email, this.password);
			// 验证输入
			if (this.email && this.password) {
				uni.showLoading({
					title: '登录中',
					content: '请耐心等待',
					mask: true
				});
				// 发起请求
				let res = uni.request({
					url: 'http://server.kingfish404.cn/main/signIn',
					method: 'POST',
					timeout: 3000,
					header: {
						'Content-Type': 'application/x-www-form-urlencoded;charset=utf-8;'
					},
					data: {
						email: this.email,
						password: this.password,
						remember_me: 'on'
					},
					success(res) {
						uni.hideLoading();
						console.log(res)
						// 打印一下然后准备存起来 jwt
						if (res.data.code == 0) {
							console.log(res)
							console.log(res.header.Authorization);
							uni.setStorageSync('authorization', res.header.Authorization);
							uni.showToast({
								title: '登录成功',
								duration: 1000
							});
							setTimeout(() => {
								uni.switchTab({
									url: '../profile/profile?login=true'
								});
							}, 1000);
						} else {
							uni.showModal({
								title: '提示',
								content: '密码或账号错误！',
								showCancel: false
							});
						}
					},
					fail() {
						uni.hideLoading();
						uni.showModal({
							title: '提示',
							content: '网络出了点小差！',
							showCancel: false
						});
					}
				});
			} else {
				uni.showModal({
					title: '提示',
					content: '请输入完整的账号和密码！',
					showCancel: false
				});
			}
		},
		doSignup() {
			console.log(this.email, this.password);
			if (this.email && this.password && this.lastName && this.name && this.confirmPassword && this.username) {
				if (this.password != this.confirmPassword) {
					uni.showToast({
						duration: 1000,
						title: '两次密码输入不一致',
						icon: 'none'
					});
					return;
				}
				uni.showLoading({
					title: '注册中',
					content: '请耐心等待',
					mask: true
				});
				let data = {
					email: this.email,
					password1: this.password,
					first_name: this.lastName,
					last_name: this.name,
					password2: this.confirmPassword,
					username: this.username
				};
				console.log(data);
				let res = uni.request({
					url: 'http://server.kingfish404.cn/main/signUp',
					method: 'POST',
					timeout: 3000,
					header: {
						'Content-Type': 'application/x-www-form-urlencoded;charset=utf-8;'
					},
					data,
					success:(res)=> {
						uni.hideLoading();
						if(res.data.code==0){
							uni.showToast({
								title:"注册成功",
								duration:1000
							})
							setTimeout(()=>{
								this.change();
							},1000)
						}else{
							uni.hideLoading();
							uni.showModal({
								title: '提示',
								content: '当前邮箱已存在',
								showCancel: false
							});
						}
					},
					fail:()=> {
						uni.hideLoading();
						uni.showModal({
							title: '提示',
							content: '网络出了点小差！',
							showCancel: false
						});
					}
				});
			} else {
				uni.showModal({
					title: '提示',
					content: '请输入完整的账号和密码！',
					showCancel: false
				});
			}
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

.login-contain {
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

.sign-contain {
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

.inputitem {
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

.inputstyle {
	background-color: #ebebeb;
	height: 70upx;
	width: 70%;
	border: solid 5upx #000000;
	border-radius: 10upx;
	direction: ltr;
	text-align: left;
}

.button-contains {
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	width: 80%;
	text-align: center;
}

.btnstyle {
	width: 200upx;
	height: 50upx;
	background-color: #ffc680;
	border-radius: 20upx;
	/* vertical-align: middle; */
	line-height: 50upx;
}
</style>
