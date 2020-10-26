<template>
	<view class="news-contains">
		<view class="content">
			<view>
				
				<image v-if="isTop" class="icon" src="../../static/common-icons/toTop.png" mode="widthFix"></image>
				{{title}}
			</view>
			<view style="font-size: 15px;">
				{{author}}
			</view>
			<view style="font-size: 11px; color: #726A4E;">
				{{comments}}评论{{like}}点赞{{time}}
			</view>
		</view>
		<image class="img" :src="imgUrl" mode="widthFix"></image>
		
	</view>
</template>

<script>
	export default {
		props:{
			title:{
				default:"",
				type:String
			},
			like:{
				default: 0,
				type: Number,
			},
			comments:{
				default: 0,
				type: Number
			},
			time:{
				default: "",
				type: String
			},
			author:{
				default: "",
				type: String
			},
			imgUrl:{
				default: "",
				type: String
			},
			isTop:{
				default:false,
				type: Boolean
			}
		},
		data() {
			return {
				
			};
		},
		methods:{
			
		}
	}
</script>

<style scoped>
.news-contains{
	display: flex;
	flex-direction: row;
	align-items: center;
	justify-content: space-between;
	text-align: center;
	width: 100%;
	border-radius: 10upx;
	box-shadow:0upx 0upx  15upx #ccc;
	/* box-shadow: 0 0 20upx rgb(69, 81, 91); */
}

.content{
	display: flex;
	flex-direction: column;
	padding: 20upx;
	justify-content: space-between;
	text-align: left;
	width: 80%;
}

.img{
	width: 45%;
}

.icon{
	width: 80upx;
	height: 80upx;
	margin-right: 5upx;
}

</style>
