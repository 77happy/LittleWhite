<template>
	<view class="index_all">
		<!-- 顶部导航栏 -->
		<view class="index_header flex justify-center align-center">
			<u-icon name="map" color="#ffaa00" size="50" class="icon map"></u-icon>
			<!-- 搜索框 -->
			<view class="flex index_search justify-center align-center">
				<input placeholder="搜索站台,线路,目的地" placeholder-style="color:#c0c0c0;" />
				<u-icon name="search" class=""></u-icon>
			</view>
			<view class="flex mic_msg">
				<!-- 语音输入 -->
				<u-icon name="mic" size="40" class="icon "></u-icon>
				<!-- 消息 -->
				<u-icon name="bell" size="40" class="icon "></u-icon>
			</view>

		</view>
		<!-- 轮播图 -->
		<view class="swiper">
			<view class="swiperList">
				<swiper :indicator-dots="true" circular="true" :autoplay="true" :interval="3000" :duration="1000">
					<swiper-item v-for="swiper in swiperList" :key="swiper.id">
						<image :src="swiper.img"></image>

					</swiper-item>
				</swiper>

			</view>

		</view>
		<!-- 功能列表  乘车码 站点地图 校内地图 租借小白 发车时间 -->
		<view class="category flex">
			<view class=" " v-for="(row, index) in categoryList" :key="index">
				<view class="img">
					<image :src="row.img" style="width: 70rpx;height: 70rpx;"></image>
					<view class="text">{{row.name}}</view>
				</view>

			</view>
		</view>
		<!-- 导航条 -->
	
		<!-- <scroll-view scroll-x class="bg-white nav">
			<view class="flex text-center">
				<view class="cu-item flex-sub" :class="index==TabCur?'text-orange cur':''" v-for="(item,index) in 4"
					:key="index" @tap="tabSelect" :data-id="index">
					Tab{{index}}
				</view>
			</view>
		</scroll-view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				// 轮播图
				swiperList: [{
						id: 1,
						src: 'url1',
						img: '/static/swiper/小白.jpg'
					},
					{
						id: 2,
						src: 'url2',
						img: '/static/swiper/学校北区.jpg'
					},

				],
				// 分类菜单
				categoryList: [{
						id: 1,
						name: '乘车码',
						img: '/static/category/erweima.png'
					},
					{
						id: 2,
						name: '站点地图',
						img: '/static/category/zahndianditu.png'
					},
					{
						id: 3,
						name: '校内地图',
						img: '/static/category/ditu.png'
					},
					{
						id: 4,
						name: '租借小白',
						img: '/static/category/zujie.png'
					},
					{
						id: 5,
						name: '发车时间',
						img: '/static/category/shijian.png'
					},
				],
			}
		},
		onLoad() {

		},
		methods: {
			tabSelect(e) {
				this.TabCur = e.currentTarget.dataset.id;
				this.scrollLeft = (e.currentTarget.dataset.id - 1) * 60
			}
		}
	}
</script>

<style lang="scss">
	.index_all {
		width: 100%;
		height: 100%;

		.index_header {
			margin-top: 100rpx;

			.map {
				margin: 0 5px 0 15upx;
			}

			.index_search {
				width: 92%;
				height: 60upx;
				background-color: #f5f5f5;
				border-radius: 30upx;
				margin-left: 20upx;

				input {
					margin-left: 5upx;
				}

			}

			.mic_msg {
				margin-right: -40upx;
				margin-left: 15upx;
			}
		}

		.swiper {
			width: 92%;
			margin: 30rpx auto 0;
			display: flex;
			justify-content: center;

			.swiperList {
				width: 100%;
				height: 250rpx;
				border-radius: 15upx;
				box-shadow: 0upx 8upx 25upx rgba(0, 0, 0, 0.2);
				overflow: hidden;

				image {
					width: 700rpx;
					height: 250rpx;
				}
			}


		}

		.category {
			width: 92%;
			flex-wrap: wrap;
			justify-content: space-between;
			margin: 30rpx auto 0;


			// padding: ;
			// margin-left: 10px;
			.img {
				padding: 10rpx;
				// width: 10upx;
				// height: 10upx;
			}

			.text {
				margin-top: 10rpx;
				width: 100%;
				display: flex;
				justify-content: center;
				font-size: 24upx;
				color: #3c3c3c;
			}
		}
	}
</style>
