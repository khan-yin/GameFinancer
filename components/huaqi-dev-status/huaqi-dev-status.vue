<template>
	<view class="dev-status">
		<view class="dev-status-background">
			<view class="dev-show" v-if="!combine">
				<view class="dev">开发进程</view>
				<view class="dev">3/5</view>
				<view class="dev" style="text-decoration:underline">报告</view>
			</view>
			<view class="button-box" >
				<view class="box-1" style="background-color: #4D6067;" @click="$emit('clickedone')">自选+</view>
				<view class="box-2" style="background-color: #395966;" @click="$emit('soldout')">卖出</view>
				<view class="box-3" style="background-color: #19383D;" v-if="!combine" @click="$emit('funding')">众筹</view>
				<view class="box-4" style="background-color: #00141B;" @click="$emit('buyin')">买入</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	props:{
		combine:{
			type:Boolean,
			default:false
		}
	},
	data() {
		return {};
	},
	methods:{
		btnclick(){
			console.log(111);
			this.$emit('clickedfour')
		}
	}
};
</script>

<style scoped>
.dev-status {
	background-color: #2e3d40;
	position: fixed;
	left: 10%;
	right: 10%;
	bottom: 30upx;
	height: 158upx;
}
.dev-status-background {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
}
.dev-status-background > * {
	flex: 1;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
}
.dev-show {
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	width: 100%;
	height: 79upx;
}
.dev-show > * {
	flex: 1;
	width: 33%;
	height: 100%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
}
.button-box {
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	text-align: center;
	width: 100%;
	height: 79upx;
}
.button-box > * {
	flex: 1;
	width: 25%;
	height: 100%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	text-align: center;
	color: #fff;
}
</style>
