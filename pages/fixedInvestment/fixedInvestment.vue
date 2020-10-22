<template>
	<view class="contains">
		 <view class="search-box">
		 	<searchBar></searchBar>
		 </view>
		 <view class="buttons">
		 	<view class="button">
		 		定投排行
		 	</view>
			<view class="button">
				我的定投
			</view>
		 </view>
		 <view class="list-contains" v-for="item in swipers">
		 	<huaqiCombineSwiper :picture="item.picture" :buttonTitle="item.buttonTitle" :combineName="item.combineName" />
		 </view>
	</view>
</template>

<script>
	import searchBar from '../../components/searchBar/searchBar.vue';
	import huaqiCombineSwiper from "../../components/huaqiCombineSwiper/huaqiCombineSwiper.vue"
	export default {
		components:{
			searchBar,
			huaqiCombineSwiper
		},
		data() {
			return {
				swipers:[
					{
						picture:[
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						}
						],
						buttonTitle:"推荐组合",
						combineName:"组合名称",
					},
					{
						picture:[
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						}
						],
						buttonTitle:"推荐组合",
						combineName:"组合名称",
					},
					{
						picture:[
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						}
						],
						buttonTitle:"推荐组合",
						combineName:"组合名称",
					},
					{
						picture:[
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						}
						],
						buttonTitle:"推荐组合",
						combineName:"组合名称",
					},
					{
						picture:[
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						},
						{
							src:"https://img.xjh.me/random_img.php?type=bg&ctype=nature&return=302",
							id:12
						}
						],
						buttonTitle:"推荐组合",
						combineName:"组合名称",
					}
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
.search-box{
	position: sticky;
	top:0upx;
	z-index: 1;
	background-color: #00191E;
}
.buttons{
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
}
.buttons>*{
	flex: 1;
}
.button{
	height: 50upx;
	margin:40upx;
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	background-color: #0C2026;
	border: 2px solid #414F47;
}
</style>
