<template>
  <view class="index_swiper">
<!-- 轮播 -->
    <view>
	<!--  -->
       <swiper class="imageContainer" circular  autoplay indicator-color="#faebd7"  indicator-dots="true" indicator-active-color="#ee7600">
           <block v-for="(item,index) in imgList" :key="index">
               <swiper-item class="swiperitem">
                   <image class="itemImg" :src="item" width="100%" height="340upx" lazy-load mode="scaleToFill"></image>
               </swiper-item>
           </block>
       </swiper>
    </view>
  </view>


</template>

<script>
export default{
data(){
return{
imgList:[
'../../static/lunbo/timg-1.jpg',
'../../static/lunbo/timg-2.jpg',
'../../static/lunbo/timg-3.jpg',
'../../static/lunbo/timg-4.jpg',
'../../static/lunbo/timg-5.jpg',
'../../static/lunbo/timg-6.jpg',
'../../static/lunbo/timg-7.jpg',
'../../static/lunbo/timg-8.jpg']
}
}
}
</script>

<style>
template{
	width: 750upx;
	background-color: #DD524D;
}

.index_swiper{
width: 750upx;
}
.imageContainer{
/* margin-top: -10upx; */
width: 100%;
height: 350upx;
}
.swiperitem{
height: 350upx;
/* padding: 0rpx 30rpx; */
width: 100%;
/* box-sizing: border-box; */
position: relative;
}

.itemImg {
position: absolute;
width: 100%;
height: 350upx;
border: #7FFFD4 3upx solid;
border-radius: 10upx;
/* border-radius: 15rpx; */
z-index: 5;
opacity: 0.8;
top: 0%;
box-shadow:0px 17upx 17upx 0px rgba(53,53,53,0.9);
}
.swiperactive {
width: 95%;
opacity: 1;
z-index: 10;
height: 287upx;
transition: all .2s ease-in 0s;
}
</style>