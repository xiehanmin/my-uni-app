<template>
	<view class="home">
		<view class="home-container">
			<view class="home-header">
				<view class="home-title">
					我的课程
				</view>
				<view class="home-school">
					入学信息入口
				</view>
				<view class="home-show" @tap="goShowContract">
					<view class="home-class">
						<text class="show-text">查看班级权益</text>
					</view>
					<image class="home-img" src="../../static/imgs/shape.png" mode=""></image>
				</view>
			</view>
			<scroll-view scroll-y="true">
				<view class="home-content" :style="{height:clientHeight+'px'}">
					<HomeCommodity></HomeCommodity>
				</view>
			</scroll-view>
		</view>
		<MyTabBar :selected="selected" />
	</view>
</template>

<script>
	import MyTabBar from '@/common/tabBar/my-tabBar.vue'
	import HomeCommodity from '@/components/index/ComecoMmodity.vue'
	export default {
		data() {
			return {
				selected: 0,
				clientHeight: null
			}
		},
		onLoad() {

		},
		onReady() {
			uni.getSystemInfo({
				success: (res) => {
					///获取头部的高度 select 里面的参数和CSS选择器一样选择元素
					let info = uni.createSelectorQuery().in(this).select(".home-header")
					info.boundingClientRect((data) => {
						//data包含元素的高度信息
						//56是tabbar的高度
						console.log(data.height)
						this.clientHeight = res.windowHeight - data.height - 56
					}).exec(function(res) {
						//这个方法必须执行，即使什么也不做，否则不会获取到信息
					})

				}
			})
		},
		methods: {
			goShowContract(){
				uni.navigateTo({
					url:'../show-contract/show-contract'
				})
			}

		},
		components: {
			MyTabBar,
			HomeCommodity
		}
	}
</script>

<style>
	scroll-view ::-webkit-scrollbar {
		display: none;
		width: 0 !important;
		height: 0 !important;
		-webkit-appearance: none;
		background: transparent;
		color: transparent;
	}

	.home {
		width: 100vw;
		height: 100%;
		margin-right: -7rpx;
		background: url('https://fawn.xuexiluxian.cn/api/profile/wechat/bgimg/bg.png') no-repeat;
		background-size: cover;
		margin-bottom: 120rpx;
		box-sizing: border-box;
	}

	.home-header {
		padding: 131rpx 37rpx 0 37rpx;
	}

	.home-title {
		width: 420rpx;
		height: 59rpx;
		font-size: 60rpx;
		font-family: Microsoft Yahei;
		font-weight: 400;
		color: #000cff;
		line-height: 80rpx;
	}

	.home-school {
		width: 236rpx;
		height: 40rpx;
		font-size: 38rpx;
		font-family: Microsoft Yahei;
		font-weight: 400;
		color: #344356;
		line-height: 56rpx;
		opacity: 0.8;
		padding: 30rpx 0;
	}

	.home-show {
		width: 290rpx;
		height: 59rpx;
		display: flex;
		align-items: center;
		background-color: #5468ff;
		border-radius: 10rpx;
		padding: 0 20rpx;
		box-sizing: border-box;
	}

	.home-class {
		width: 200rpx;
		height: 27rpx;
		line-height: 27rpx;
		font-size: 28rpx;
		font-family: Microsoft Yahei;
		font-weight: 400;
		color: #FFFFFF;
	}

	.home-class::after {
		content: '';
		width: 1rpx;
		height: 31rpx;
		margin: 0 20rpx;
		border-left: 4rpx solid #FFFFFF;

	}

	.home-img {
		width: 38rpx;
		height: 38rpx;
	}
</style>
