<template>
	<view class="contains">
		<view></view>
		<view class="list-contains" v-for="item in swipers" :key="gameItem">
			<indexItem :picture="item.picture" :describe="item.describe" :gameName="item.gameName" />
		</view>
	</view>
	
</template>

<script>
	import indexItem from '../../components/indexItem/indexItem.vue'
	// import huaqiCombineSwiper from '../../components/huaqiCombineSwiper/huaqiCombineSwiper.vue'
	
	export default {
		components:{
			indexItem,
			// huaqiCombineSwiper,
		},
		data() {
			return {
				gameItem:"gameItem",
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
						describe:"xxxxxxxxxx",
						gameName:"组合名称",
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
						describe:"xxxxxxxxxx",
						gameName:"组合名称",
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
						describe:"xxxxxxxxxx",
						gameName:"组合名称",
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
						describe:"xxxxxxxxxx",
						gameName:"组合名称",
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
						describe:"xxxxxxxxxx",
						gameName:"组合名称",
					}
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.contains{
	display: flex;
	flex-direction: column;
	text-align: center;
	justify-content: center;
}
</style>
