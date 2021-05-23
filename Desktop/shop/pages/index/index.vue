<template>
<view>
	<!-- 轮播图区域 -->
	<view class="home">
		<swiper indicator-dots circular>
			<swiper-item v-for="item in swipers" :key="item.goods_id">
				<image :src="item.image_src"></image>
			</swiper-item>
		</swiper>
	</view>
	<!-- 导航区域 -->
	<view class="nav">
		<view class="nav_item">
			<view class="iconfont icon-ziyuan"></view>
			<text>超市</text>
		</view>
		<view class="nav_item">
			<view class="iconfont icon-guanyuwomen"></view>
			<text>咨询</text>
		</view>
		<view class="nav_item">
			<view class="iconfont icon-tupian"></view>
			<text>图片</text>
		</view>
		<view class="nav_item">
			<view class="iconfont icon-shipin"></view>
			<text>视频</text>
		</view>
	</view>
	<!-- 推荐商品 -->
	<view class="shop_goods">
		<view class="tit">
			推荐商品
		</view>
	</view>
	<view class="goods_list">
		<view class="goods_item">
			<img src="../../static/d8f9d72a6059252dd42aeafa42d1143b5bb5c8ea13b0.jpg">
			<view class="price">
				<text>￥3399</text>
				<text>￥3699</text>
			</view>
			<view class="name">
				一加 OnePlus 9R 5G旗舰120Hz 柔性屏12GB+256GB 蓝屿 骁龙870 65W快充 专业游戏配置 超大广角拍照手机
			</view>
		</view>
		<view class="goods_item">
			<img src="../../static/d8f9d72a6059252dd42aeafa42d1143b5bb5c8ea13b0.jpg">
			<view class="price">
				<text>￥3399</text>
				<text>￥3699</text>
			</view>
			<view class="name">
				一加 OnePlus 9R 5G旗舰120Hz 柔性屏12GB+256GB 蓝屿 骁龙870 65W快充 专业游戏配置 超大广角拍照手机
			</view>
		</view>
		<view class="goods_item">
			<img src="../../static/d8f9d72a6059252dd42aeafa42d1143b5bb5c8ea13b0.jpg">
			<view class="price">
				<text>￥3399</text>
				<text>￥3699</text>
			</view>
			<view class="name">
				一加 OnePlus 9R 5G旗舰120Hz 柔性屏12GB+256GB 蓝屿 骁龙870 65W快充 专业游戏配置 超大广角拍照手机
			</view>
		</view>
	</view>
</view>
</template>

<script>
	export default {
		data() {
			return {
				swipers:[]
			}
		},
		onLoad() {
			this.getSwipers()
		},
		methods: {
			// 获取轮播图数据
			async getSwipers(){
				const res = await this.$myRequest({
					url:'/home/swiperdata'
				})
				this.swipers = res.data.message
			}
		}
	}
</script>

<style lang="scss">
	.home{
		swiper{
			width: 750rpx;
			height: 380rpx;
			image{
				height: 100%;
				width: 100%;
			}
		}
	}
	.nav{
		display: flex;
		.nav_item{
			width: 25%;
			text-align: center;
			view{
				width: 120rpx;
				height: 120rpx;
				background: $shop-color;
				border-radius: 60rpx;
				margin: 10px auto;
				line-height: 120rpx;
				color: #fff;
				font-size: 50rpx;
			}
		}
		text{
			font-size: 30rpx;
		}
	}
	.shop_goods{
		background: #eee;
		overflow: hidden;
		margin-top: 10px;
		.tit{
			height: 50px;
			line-height: 50px;
			color: $shop-color;
			text-align: center;
			letter-spacing: 20px;
			background-color: #fff;
			margin: 7px 0;
		}
	}
	.goods_list{
		padding: 0 15rpx;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		.goods_item{
			width: 355rpx;
			margin: 10px 0;
			padding: 15px;
			box-sizing: border-box;
			background-color: #fff;
			img{
				width: 80%;
				height: 150px;
				display: block;
				margin: 0 auto;
			}
			.price{
				color: $shop-color;
				font-size: 36rpx;
				text:nth-child(2){
					color: #ccc;
					font-size: 28rpx;
					margin-left: 17rpx;
					text-decoration: line-through;
				}
			}
			.name{
				font-size: 28rpx;
				line-height: 50rpx;
				padding-bottom: 15rpx;
				padding-top: 10rpx;
			}
		}
	}
</style>
