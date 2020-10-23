<template>
	<view class="contains">
		<!-- 名片 -->
		<view class="wide-card">

			<view class="Gamecard" :fundingItem="FundingItem">
				<!-- 左半部分 -->
				<view class="cardleft">
					<view style="color: white; font-size: larger; font-family: Microsoft YaHei;">{{FundingItem.title}}</view>
					<image class="cardImg" :src="FundingItem.Imgsrc"></image>
				</view>
				<!-- 中间过渡的线 -->
				<view class="line-right"></view>
				<!-- 右半部分 -->
				<view class="cardright">
					<view style="font-size: medium; color: white; margin: auto auto;">发放时间：
						<text style="color: #DECD48; font-style: italic; ">{{FundingItem.time}}</text>
					</view>
					<view class="fundinginput">
						<image class="icon" src="../../static/common-icons/money.png"></image>
						<input class="number" v-model="inputmoney" style="color: white;" />
					</view>

					<view style="font-size: 14upx; color: #FBE399; margin: auto auto;">【回报描述】<text style="color: white;">{{FundingItem.describe}}</text>
					</view>

				</view>
			</view>

		</view>

		<!-- 选择回报 -->
		<view class="FundingChoice">
			<view style="color: #8DADB0; font-size: larger; font-family: Microsoft YaHei;">选择回报</view>
			<!-- 分界线 -->
			<view class="line-bottom"></view>
			
			<!-- 不知道怎么把文字搞上去，换了好几种图片背景button还是没搞出来 qwq-->
			<view style="display:flex; flex-direction: column; justify-content: center;">
				<view style="display: flex; flex-direction: row; justify-content: center;">
					<view style="padding: 10upx;" @click="chooseItem(0)">
					<image class="choiceImg" style=" transform: rotateX(180deg)" src="../../static/funding/choicebtn.png" mode="widthFix"></image>
					</view>
					<view style="padding: 10upx;"  @click="chooseItem(1)">
						<image class="choiceImg" style="transform: rotate(180deg)"  src="../../static/funding/choicebtn.png" mode="widthFix"></image>
					<!-- <span style="position: absolute; bottom: 0; left: 0;">添加文</span>	
					 --></view>
				</view>
				
				<view style="display: flex; flex-direction: row; justify-content: center;">
					<view style="padding: 10upx;" @click="chooseItem(2)" >
						<image class="choiceImg" src="../../static/funding/choicebtn.png" mode="widthFix"></image>
					</view>
					<view style="padding: 10upx;" @click="chooseItem(3)" >
					<image class="choiceImg" style="transform: rotateY(180deg);" src="../../static/funding/choicebtn.png" mode="widthFix"></image>
					</view>
				</view>
			</view>
			
			<!-- 数量监听 点击动作效果失效-->
			<view style=" width: 80%; display: flex; flex-direction: row; justify-content: space-between; ">
				<view style=" margin-left: 80upx; color: white; margin-top: 22upx; font-size: large;">数量</view>

				<view style="margin-right: -100upx; margin-top: 5upx;">
					<image class="icon" :src="addbtnUrl" @click="clickAdd"></image>
				<text style="color: #F8D45B; font-style: italic; margin-bottom: 5upx; font-size: x-large; margin-right: 40upx;">{{count}}</text>
				<image class="icon" :src="delbtnUrl" @click="clickDel" ></image>
				</view>
				
			</view>
			<!-- 分界线 -->
			<view class="line-bottom"></view>
			<!-- button -->
			<button type="primary" style="color: #96A9AE; font-size: large; font-family: Microsoft YaHei;" class="btn" @click="btnClick">立即支持</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				inputmoney: "",
				count: 0,
				addbtnUrl: "../../static/funding/addbtn.png",
				delbtnUrl: "../../static/funding/delbtn.png",
				FundingItem: {
						title: "回报名称1",
						time: "2020/11/01",
						Imgsrc: "https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
						"describe": "在遥远的过去，人们藉由对神灵的信仰，获赐了驱动元素的力量，得以在荒野中筑起家园。五百年前，古国的覆灭却使得天地变异…如今，席卷大陆的灾难已经停息，和平却仍未如期光临。"
				},
				FundingList: [{
						title: "回报名称1",
						time: "2020/11/01",
						Imgsrc: "https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
						"describe": "在遥远的过去，人们藉由对神灵的信仰，获赐了驱动元素的力量，得以在荒野中筑起家园。五百年前，古国的覆灭却使得天地变异…如今，席卷大陆的灾难已经停息，和平却仍未如期光临。"
					},
					{
						title: "回报名称2",
						time: "2020/11/01",
						Imgsrc: "https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
						"describe": "谢谢大家的关注的支持"
					},
					{
						title: "回报名称3",
						time: "2020/11/01",
						Imgsrc: "https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
						"describe": "谢谢大家的关注的支持"
					},
					{
						title: "回报名称4",
						time: "2020/11/01",
						Imgsrc: "https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
						"describe": "谢谢大家的关注的支持"
					},
				],
			}
		},
		methods: {
			//数量监听
			clickAdd(){
				this.addbtnUrl="../../static/funding/addbtnclick.png";
				this.count++;
				this.addbtnUrl="../../static/funding/addbtn.png";
			},
			clickDel(){
				this.delbtnUrl="../../static/funding/delbtnclick.png";
				this.count--;
				this.delbtnUrl="../../static/funding/delbtn.png";
			},
			//切换回报
			chooseItem(index){
				this.FundingItem=this.FundingList[index];
			},
			//button点击事件
			btnClick(){
				console.log(this.inputmoney)
				console.log(this.count)
				this.inputmoney=""
			}
		}
	}
</script>

<style>
	.contains {
		display: flex;
		flex-direction: column;
		justify-content: center;
		text-align: center;
	}

	.wide-card {
		width: 100%;
		margin: 100upx 0upx auto;
		padding: 20upx 5upx;
		/* height: 400upx; */
		background-color: #121929;
		border-radius: 20upx;
		border: solid #333D40 2upx;
	}

	.Gamecard {
		margin: 0 auto;
		padding: 20upx;
		width: 90%;
		height: 400upx;
		background-color: #212F3B;
		display: flex;
		flex-direction: row;
		justify-content: center;
		text-align: center;

	}

	.cardleft {
		margin: ;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}

	.cardright {
		display: flex;
		flex-direction: column;
		flex-wrap: wrap;
		justify-content: center;
		text-align: center;
	}

	.line-right {
		margin-top: 50upx;
		width: 50upx;
		height: 300upx;
		border-right: solid #ACC0D8 4upx;
	}

	.line-bottom {
		margin: 10upx auto;
		width: 90%;
		height: 1px;
		border-top: solid #51707C 5upx;
	}
	
	.cardImg {
		margin-top: 30upx;
		width: 250upx;
		height: 250upx;
		border-radius: 50%;
		border: solid;
		border-color: #23465C;
		box-shadow: 0 5px 20px rgb(69, 81, 91);
	}

	.icon {
		margin-top: 15upx;
		margin-right: 40upx;
		height: 50upx;
		width: 50upx;
	}

	.choiceImg {
		height: 150upx;
		width: 300upx;
	}

	.fundinginput {
		display: flex;
		flex-direction: row;
		justify-content: center;
	}

	.btn {
		background-color: #55636A;
		margin: 0 auto;
		width: 500upx;
		height: 80upx;
		line-height: 80upx;
		vertical-align: middle;
		text-align: center;
		border: 1px solid rgba(0, 0, 0, .2);
		box-sizing: border-box;
		border-radius: 10px;
	}

	.number {
		margin-left: 10upx;
		width: 200upx;
		color: #F5DEB3;
		text-align: center;
		background-color: #0D2331;
		border-radius: 20upx;
		margin-top: 15upx;
		padding: 0upx 10upx;
	}

	.FundingChoice {
		margin-top: 30upx auto;
		display: flex;
		flex-direction: column;
		justify-content: center;
		text-align: center;
		background-color: linear-gradient(to bottom, #051316,#292F35);
	}
</style>
