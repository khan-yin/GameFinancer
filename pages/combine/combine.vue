<template>
	<view class="contains">
		 <view class="search-box">
		 	<searchBar></searchBar>
		 </view>
		 <view class="list-contains" v-for="item in swipers" @click="navTo('../combineDetail/combineDetail')">
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
			navTo(url){
				if(url){
					uni.navigateTo({
						url:url,
						animationType:'slide-in-right',
						animationDuration:500
					})
				}
			}
		}
	}
</script>

<style>
.search-box{
	position: sticky;
	top:0upx;
	z-index: 1;
	background-color: #00191E;
}
</style>
