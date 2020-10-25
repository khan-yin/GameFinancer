<template>
	<view class="contains">
		<view class="sold-top">
				  <!-- <huaqiDetailList :title="listBox.title"  :rank="listBox.rank" :interestRate="listBox.interestRate" :background="listBox.background" :avgRate="listBox.avgRate" /> -->
				  <huaqiPaymentItemList :title="listBox.title"   :background="listBox.background"  />
		</view>
		<view class="buy-contain">
			    
				<view class="title">卖出金额</view>
			    
			    <view class="money">
			      <image src="../../static/common-icons/money.png" /></image>
			      <input class="number" v-model="inputmoney" style="color: yellow;" />
			    </view>
			    
			    <view class="way">
			      <view class="remain">剩余金额</view>
			      <!-- <view> -->
					 <input class="number" v-model="balance" style="color: yellow;"  />  			     
				  <!-- </view> -->
			      
			    </view>
			  </view>
				  <button class="btn" @click="payGame">确认</button>
	</view>
</template>

<script>
	import huaqiPaymentItemList from '../../components/huaqi-payment-item-list/huaqi-payment-item-list.vue'
	
	export default {
		components:{
			huaqiPaymentItemList,
		},
		data() {
			return {
				usertotalmoney: 1000,
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
		computed:{
			balance(){
			return (this.usertotalmoney - this.inputmoney)>=0?(this.usertotalmoney - this.inputmoney):"余额不足";
			}
		},
		methods: {
			payGame(){
				this.usertotalmoney=this.usertotalmoney - this.inputmoney;
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
	height: 110upx;
	width: 110upx;
	margin-right: 7%;
	/* height: 50%;
	width: 50%; */
}

.number{
  margin-left: 25%;
  width: 300upx;
  color: #F5DEB3;
  text-align: right;
  background-color: #2F4F4F;
  border-radius: 20upx;
  margin-top: 15upx;
  padding: 10upx 0upx;
}
.way{
  color: white;
  flex: 1;
  display: flex;
  flex-direction: row;
  margin: 20upx 20upx;
  padding-bottom: 15upx;
}
.remain{
	margin-top: 10upx;
	padding-top: 15upx;
  /* margin-left: -10upx; */
  /* margin-right: 0upx; */
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
