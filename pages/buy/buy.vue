<template>
  <view class="contains">
	  <!-- 项目概述 -->
	  <view class="buy-top">
		  <!-- <huaqiDetailList :title="listBox.title"  :rank="listBox.rank" :interestRate="listBox.interestRate" :background="listBox.background" :avgRate="listBox.avgRate" /> -->
		  <huaqiPaymentItemList :title="listBox.title"   :background="listBox.background"  />
	  </view>
	  
	  <view class="buy-contain">
	    
		<view class="title" >买入金额</view>
	    
	    <view class="money">
	      <image src="../../static/common-icons/money.png" /></image>
	      <input class="number" v-model="inputmoney" style="color: yellow;"  />
	    </view>
	    
	    <view class="way">
	      <view class="fkfs">付款方式</view>
	      <view class="imgs">
	        <image class="icon" src="../../static/common-icons/balance.png"  /></image>
	  		<image class="icon" src="../../static/common-icons/wxicon.png"  /></image>
	  		<image class="icon" src="../../static/common-icons/alipayicon.png"  /></image>
	  		<image class="icon" src="../../static/common-icons/UnionPay.png" /></image>
	      </view>
	      <view>···其他方式</view>
	    </view>
	  </view>
		  <button type="primary" class="btn" @click="payGame">确认</button>
		
  </view>
</template>

<script>
	import huaqiPaymentItemList from '../../components/huaqi-payment-item-list/huaqi-payment-item-list.vue'
	export default {
		components:{
			huaqiPaymentItemList
		},
		data() {
			return {
				inputmoney: "",
				listBox:{
					title:"项目一",
					rank:"1/40",
					interestRate:"13",
					avgRate:"11",
					background:'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg',
				}
			}
		},
		methods: {
			//监听button，执行买入操作
			payGame(){
				console.log(this.inputmoney);
				this.inputmoney="";
			}
		}
	}
</script>


<style>
.contains{
	flex:1;
	display: flex;
	flex-direction: column;
	justify-content: center;
	text-align: center;
}	

.buy-top{
	margin-top: 30upx;
}

.buy-contain{
	/* margin-top: 100upx; */
   /* margin-top: 100upx; */
   flex: 1;
  width: 90%;
  height: 40vh;
  background-color: #212F3A;
  display: flex;
  flex-direction: column;
  
  /* justify-content: center; */
  margin: 100upx auto;
  /* padding: 10upx; */
  border-radius: 5%;
}

.title{
  flex: 1;
  color: white;
  margin-top: 30upx;
  margin-left: -500upx;
  /* margin-bottom: 60upx; */
}

.money{
	flex: 1;
  display: flex;
  flex-direction: row;
  margin: 20upx 20upx;
  padding-bottom: 15upx;
  border-bottom: 2upx solid #3F5763;
}
.money image{
	height: 100upx;
	width: 100upx;
	/* height: 50%;
	width: 50%; */
}

.number{
  margin-left: 30%;
  width: 300upx;
  color: #F5DEB3;
  text-align: right;
  background-color: #2F4F4F;
  border-radius: 20upx;
  margin-top: 15upx;
  padding: 10upx 10upx;
}
.way{
	flex: 1;
  color: white;
  margin: 10upx 20upx;
  display: flex;
  flex-direction: row;
}
.fkfs{
  margin-right: 30upx;
}
.imgs{
  margin-right: 10upx;
  
}
.icon {
	width: 65upx;
	height: 55upx;
}
.btn{
	background-color: #878E7A;
	margin: 0 auto;
	width: 500upx;
	height: 80upx;
	line-height: 82upx;
	vertical-align: middle;
	text-align: center;
	border: 1px solid rgba(0,0,0,.2);
	box-sizing: border-box;
	border-radius: 10px;
}
/* .way image{
	/* width: 30%;
	height: 30%; */
  /* width: 40upx;
  height: 100upx; */
  /* margin: 0 2upx; */
/*} */
</style>

<!-- <template>
	<view class="contains">
	<huaqiDetailList :title="listBox.title"  :rank="listBox.rank" :interestRate="listBox.interestRate" :background="listBox.background" :avgRate="listBox.avgRate" />
	<view class="buydetail-contains">
		<image class="icon" src="../../static/common-icons/wxicon.png" mode="widthFix">
		</image>
		<image class="icon" src="../../static/common-icons/alipayicon.png" mode="widthFix">
		</image>
		<image class="icon" src="../../static/common-icons/UnionPay.png" mode="widthFix">
		</image>
	</view>
	
	</view>
	
	
	
</template>

<script>
	import huaqiDetailList from '../../components/huaqiDetailList/huaqiDetailList.vue'
	export default {
		components:{
			huaqiDetailList
		},
		data() {
			return {
				listBox:{
					title:"项目一",
					rank:"1/40",
					interestRate:"13",
					avgRate:"11",
					background:'https://xgpax.top/wp-content/uploads/2020/08/撑伞女孩-日本和服美女4k动漫壁纸.jpg',
				}
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
}

.game-detail{
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	/* background-color: rgba(25,55,69,1); */
	background-image: linear-gradient(to right,rgba(17,38,40,0.9),rgba(25,55,69,1));
	height: 150uupx;
	width: 380uupx;
	position: relative;
	/* left: -60uupx; */
	border-radius:0 100uupx 100uupx 0;
	/* box-shadow: -20upx 0upx 10upx  rgba(25,55,69,1); */
}

.buydetail-contains{
	height: 150uupx;
	width: 300uuupx;
	background-image: ;
	border-radius: 20%;
	border-color: #ffffff;
	border-style: solid;
}

.icon {
	/* bottom: 10vh; */
	width: 15%;
	height: 100%;
}
</style>
 -->