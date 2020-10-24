<template>
	<view class="contains-box">
		<view :class="{ 'current-item': idx===current }" @click="clickItem(idx)" v-for="(item, idx) in types" :key="idx">{{ item }}</view>
	</view>
</template>

<script>
export default {
	props: {
		types: {
			type: Array,
			default: ()=>['全部', 'RPG', 'ACT', 'AVG', 'SLG', 'RTS', 'FTG', 'ST']
		}
	},
	data() {
		return {
			current:0
		};
	},
	methods:{
		clickItem(idx){
			// 分发事件上去
			this.$emit("classify",this.types[idx]);
			// 修改当前活跃
			this.current = idx;
		}
	}
	
};
</script>

<style scoped>
.contains-box {
	height: 70upx;
	background-color: #00191e;
	width: 95%;
	margin: 3% 2%;
	flex-wrap:wrap;
	overflow-x: scroll;
	/* overflow-y: hidden; */
	/* overflow-x: auto; */
	white-space: nowrap;
}
.contains-box > * {
	/* flex: 1; */
	width:20%;
	font-size: 35upx;
	display: inline-block;
}
.current-item {
	font-size: 40upx;
	color: #FFD66C;
}
</style>
