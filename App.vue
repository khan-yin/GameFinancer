<script>
export default {
	onLaunch: function() {
		console.log('App Launch');
	},
	onShow: function() {
		console.log('App Show');
	},
	onHide: function() {
		console.log('App Hide');
	}
};
</script>

<style>
@import './normalize.css';
/* 解决头条小程序组件内引入字体不生效的问题 */
/* #ifdef MP-TOUTIAO */
@font-face {
	font-family: uniicons;
	src: url('/static/uni.ttf');
}
/* #endif */

page {
	background-color:  rgb(0, 25, 30);
	color: #8a9ca6;
	background-image: linear-gradient(to bottom, rgb(0, 25, 30) 70%, rgb(62, 64, 75));
	background-repeat: no-repeat;
	background-position: 100%;
	background-attachment: fixed;
}
</style>
