<template>
	<view class="content">
		<you-scroll ref="scroll" @onPullDown="onPullDown" @onScroll="onScroll" @onLoadMore="onLoadMore">
			<view>
				<!-- 可替换下拉内容 -->
				<!-- <div class="pullDown" slot="pullDown">
					<div id="preloader_1">
						<span></span>
						<span></span>
						<span></span>
						<span></span>
						<span></span>
					</div>
				</div> -->
				<!--轮播-->
				<indexSwiper></indexSwiper>
				<!-- 分类列表 -->
				<view class="category-list">
					<view class="category"
						v-for="(row, index) in categoryList"
						:key="index"
						@tap="toCategory(row)">
						<view class="img"><image :src="row.img"></image></view>
						<view class="text">{{ row.name }}</view>
					</view>
				</view>
				<!-- 资料列表 -->
				<div class="block" v-for="(listt, item) in list" :key="item" @click="scrollTo">
					<view class="div-img"><image :src="listt.img"></image></view>
					<view class="div-text">{{ listt.title }}</view>
				</div>
				<div id="preloader_1">
					<span></span>
					<span></span>
					<span></span>
					<span></span>
					<span></span>
				</div>
				<!-- <div class="loadingText">正在努力加载...</div> -->
			</view>
		</you-scroll>
	</view>
</template>

<script>
	import indexSwiper from '../../components/lunbo/lunbo.vue'
	import youScroll from '@/components/you-scroll'
	export default {
		components: {
			youScroll,
			indexSwiper
		},
		data() {
			return {
				list: [
					{ id: 1,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
				    { id: 2,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
				    { id: 3,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
					{ id: 4,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
					{ id: 5,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
					{ id: 6,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
					{ id: 7,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
					{ id: 8,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
					{ id: 9,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
					{ id: 10,img: '../../static/category/1.png',title:'川师大数学系研究生资料' },
					],
				// 分类菜单
				categoryList: [
					{ id: 1, name: '数学', img: '../../static/category/1.png' },
					{ id: 2, name: '英语', img: '../../static/category/2.png' },
					{ id: 3, name: '政治', img: '../../static/category/3.png' },
					{ id: 4, name: '生物', img: '../../static/category/4.png' },
					{ id: 5, name: '地理', img: '../../static/category/5.png' },
					{ id: 6, name: '化学', img: '../../static/category/6.png' },
					{ id: 7, name: '物理', img: '../../static/category/7.png' },
					{ id: 8, name: '更多', img: '../../static/category/8.png' }
				]
			};
		},
		onReady() {
			// console.log(this.$refs.scroll)
		},
		methods: {
			onPullDown(done) { // 下拉刷新
				setTimeout(() => {
					this.list = [1,2,3,4,5,6,7,8,9,10];
					done(); // 完成刷新
				},1000*1)
			},
			onScroll(e) { // 监听滚动
				console.log(e.detail.scrollTop)
			},
			onLoadMore(e) { // 加载更多
				setTimeout(() => {
					let len = this.list.length;
					for (let i = 1; i <= 10; i++) {
						this.list.push(len + i);
					}
				},1000*1)
			},
			scrollTo() {
				this.$refs.scroll.goTop();
			},
			//分类跳转
			toCategory(e) {
				//uni.showToast({title: e.name,icon:"none"});
				uni.setStorageSync('catName',e.name);
				uni.navigateTo({
					url: '../../goods/goods-list/goods-list?cid='+e.id+'&name='+e.name
				});
			}
		}
	};
</script>

<style>
	page {
		height: 100%;
		overflow: hidden;
	}

	.content {
		text-align: center;
		height: 100%;
	}
	/* 资料列表详情 */
	.content .block {
		height: 200px;
		line-height: 200px;
		text-align: center;
		margin: 10px;
		background-color: #F1F1F1;
		display: flex;
		flex-wrap: wrap;
	}
	.block .div-img image {
				width: 19vw;
				height: 19vw;
			}
	
	
	.content .loadingText {
		line-height: 30px;
		text-align: center;
		font-size: 12px;
		color: #999;
	}

	#preloader_1{
		height: 40px;
		line-height: 40px;
		position:relative;
		text-align: center;
	}
	#preloader_1 span{
		width: 5px;
		height: 5px;
		margin: 0 1px;
		display: inline-block;
		vertical-align: middle;
		background: #9b59b6;
		animation: preloader_1 1.5s  infinite ease-in-out;
	}  
	#preloader_1 span:nth-child(2){
		animation-delay: .2s;  
	}
	#preloader_1 span:nth-child(3){
		animation-delay: .4s;
	}
	#preloader_1 span:nth-child(4){
		animation-delay: .6s;
	}
	#preloader_1 span:nth-child(5){
		animation-delay: .8s;
	}
	@keyframes preloader_1 {
		0% {height:5px;background:#9b59b6;}
		25% {height:30px;background:#3498db;}
		50% {height:5px;background:#9b59b6;}
		100% {height:5px;background:#9b59b6;}
	}
	.category-list {
		width: 92%;
		margin: 0 4%;
		padding: 0 0 30upx 0;
		border-bottom: solid 2upx #f6f6f6;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		}
		.category-list .category {
			width: 25%;
			margin-top: 50upx;
			display: flex;
			flex-wrap: wrap;
			}
		.category-list .category .img {
				width: 100%;
				display: flex;
				justify-content: center;
				}
		.category-list .category .img image {
					width: 9vw;
					height: 9vw;
				}
		.category-list .category .text {
				margin-top: 16upx;
				width: 100%;
				display: flex;
				justify-content: center;
				font-size: 24upx;
				color: #3c3c3c;
			}
		
</style>
