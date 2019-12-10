<template>
	<view class="up-banner-1">
		
		<view class="contaction-1">
			<navigator @click="lianxiPerson()">
				<image src="../../static/news/xitongxiaoxi.png" mode=""></image>
				<test class="mytest">系统消息</test>
				<test class="dates">11月1日</test>
				<em class="mynews">联系人</em>
			</navigator>
		</view>
		
		<view class="text-admire">
			<image src="../../static/news/dianzan.png" mode=""></image>
			<test class="mytest">文章点赞</test>
			<test class="dates">11月1日</test>
			<em class="mynews">暂无消息</em>
		</view>
		
		<view class="text-collect">
			<image src="../../static/news/shoucang.png" mode=""></image>
			<test class="mytest">文章收藏</test>
			<test class="dates">11月1日</test>
			<em class="mynews">暂无消息</em>
		</view>
		
		<view class="text-comment">
			<image src="../../static/news/pinglun.png" mode=""></image>
			<test class="mytest">文章评论</test>
			<test class="dates">11月1日</test>
			<em class="mynews">暂无消息</em>
		</view>
		<view class="subscriber">
			<image src="../../static/news/dingyue.png" mode=""></image>
			<test class="mytest">订阅</test>
			<test class="dates">11月1日</test>
			<em class="mynews">暂无消息</em>
		</view>
		
		<view class="text-assess">
			<image src="../../static/news/kecheng.png" mode=""></image>
			<test class="mytest">课程评价</test>
			<test class="dates">11月1日</test>
			<em class="mynews">暂无消息</em>
		</view>
		
		<view class="material-assess">
			<image src="../../static/news/ziliao.png" mode=""></image>
			<test class="mytest">资料评价</test>
			<test class="dates">11月1日</test>
			<em class="mynews">暂无消息</em>
		</view>
		
		<view class="pleasing">
			<image src="../../static/news/manyidu.png" mode=""></image>
			<test class="mytest">满意度</test>
			<test class="dates">11月1日</test>
			<em class="mynews">暂无消息</em>
		</view>
	</view>
</template>

<script>
	export default{
		data() {
		        return {
		                
		            }
		        },
		methods:{  
			     lianxiPerson(){
					uni.navigateTo({
						url: 'contacts'
                });
				 }
                 
            }
		}
	
</script>

<style>
	.up-banner-1{
		background-color: #6575d282;
	}
	.contaction-1{
		width:100%;
		height:150rpx;
		position: relative;
		padding-top: 50rpx;
		margin-bottom: 2rpx;
		background: #FFFFFF; 
	}
	.text-admire{
		width:100%;
		height:150rpx ;
		position: relative;
		padding-top: 50rpx;
		margin-bottom: 2rpx;
		background: #FFFFFF; 
	}
	.text-collect{
		width:100%;
		height:150rpx ;
		position: relative;
		padding-top: 50rpx;
		margin-bottom: 2rpx;
		background: #FFFFFF;  
	}
	.text-comment{
		width:100%;
		height:150rpx ;
		position: relative;
		padding-top: 50rpx;
		margin-bottom: 2rpx;
		background: #FFFFFF; 
	}
	.subscriber{
		width:100%;
		height:150rpx ;
		position: relative;
		padding-top: 50rpx;
		margin-bottom: 2rpx;
		background: #FFFFFF; 
	}
	.text-assess{
		width:100%;
		height:150rpx ;
		position: relative;
		padding-top: 50rpx;
		margin-bottom: 2rpx;
		background: #FFFFFF;  
	}
	.material-assess{
		width:100%;
		height:150rpx ;
		position: relative;
		padding-top: 50rpx;
		margin-bottom: 2rpx;
		background: #FFFFFF;  
	}
	.pleasing{
		width:100%;
		height:150rpx ;
		position: relative;
		padding-top: 50rpx;
		background: #FFFFFF; 
	}
	image{
		width: 100rpx;
		height: 100rpx;
		clear: both;
		display: inline-block;
		vertical-align:top;//文字与图片顶部对齐
		padding-left: 25rpx;
	}
	.mytest{
		font-size: 16px;
		display: inline-block;//文字与图片同行
		positon:relative;
		vertical-align:top;
		margin-left: 30rpx;
	}
	.mynews{
		font-size: 14px;
		display: block;//文字在图片下方显示
		positon:relative;
		margin-left: 150rpx;
	}
	.dates{
		font-size: 16px;
		display: inherit;
		vertical-align:top;
		positon:relative;
		float: right; 
		margin-right: 40rpx;
	}
</style>
