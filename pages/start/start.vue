<template>
	<view class="demo">
		<image src="../../static/1777096-20191008113330218-1417377290.gif"></image>
	</view>
</template>

<script>
	export default {
		data(){
			return{
			}
		},
	onShow : function(){
		setInterval(() => {
			uni.navigateTo({
			         url: '../login/login'
			});
			}
			),5000}
	}
</script>

<style>
	.demo{
		width: 750rpx;
		height: 100%;
		justify-content:center;
	}
	.demo image{
		position: absolute;
		margin-top: 550upx;
		margin-left: 270upx;
		width: 255upx;
		height: 255upx;
	}
</style>
