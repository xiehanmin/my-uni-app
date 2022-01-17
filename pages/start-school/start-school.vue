<template>
	<view class="start-school">
		<MyHeader class="start-header" :title="title" />
		<scroll-view scroll-y="true" :style="{height:clientHeight+'px'}">
			<view>
				<!-- 顶部填写入学信息 -->
				<view class="banner-bg">
					<view class="sign-btn">
						立即填写 >
					</view>
				</view>
				<view class="school-content">
					<ManageList />
					<view class="main-title">名人堂</view>
					<scroll-view scroll-x="true" class="scroll-content">
						<view class="scroll-item">
							<CelebrityList />
						</view>
					</scroll-view>
					<view class="main-title">公告</view>
					<Notice></Notice>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	import MyHeader from '@/common/my-header/my-header.vue'
	import ManageList from '@/components/start-school/manage-list.vue'
	import CelebrityList from '@/components/start-school/celebrity-list.vue'
	import Notice from "@/components/start-school/Notice.vue"
	export default {
		components: {
			MyHeader,
			ManageList,
			CelebrityList,
			Notice
		},
		data() {
			return {
				title: '',
				clientHeight: 1000
			}

		},
		onReady() {
			uni.getSystemInfo({
				success: (res) => {
					///获取头部的高度 select 里面的参数和CSS选择器一样选择元素
					let info = uni.createSelectorQuery().in(this).select(".start-header")
					info.boundingClientRect((data) => {
						//data包含元素的高度信息
						//56是tabbar的高度
						console.log(data.height)
						this.clientHeight = res.windowHeight - data.height
					}).exec(function(res) {
						//这个方法必须执行，即使什么也不做，否则不会获取到信息
					})

				}
			})
		},
		onLoad(options) {
			const item = JSON.parse(options.item)
			this.title = item.className
			console.log(item)
		},
		methods: {

		}
	}
</script>

<style scoped>
	/* 消除滚动条 */
	scroll-view ::-webkit-scrollbar {
		display: none;
		width: 0 !important;
		height: 0 !important;
		-webkit-appearance: none;
		background: transparent;
		color: transparent;
	}

	scroll-view {
		background-color: #f3f4f6;
	}

	.start-school {
		width: 100vw;
		height: 100vh;
		box-sizing: border-box;
		background-color: #f3f4f6;
	}

	.banner-bg {
		position: relative;
		width: 750rpx;
		height: 295rpx;
		background: url('https://fawn.xuexiluxian.cn/api/profile/wechat/bgimg/banner.png') no-repeat;
		background-size: contain;
	}

	.sign-btn {
		position: absolute;
		top: 195rpx;
		left: 60rpx;
		width: 173rpx;
		height: 44rpx;
		font-size: 28rpx;
		color: #FFFFFF;
		padding: 5rpx 10rpx;
		text-align: center;
		line-height: 44rpx;
		border: 1rpx solid #FFFFFF;
		border-radius: 40rpx;
	}

	.school-content {
		padding: 40rpx 37rpx;
	}

	.scroll-content {
		width: 100%;
		height: 100%;
	}

	.main-title {
		width: 102rpx;
		height: 33rpx;
		font-size: 34rpx;
		font-weight: bold;
		color: #252525;
		margin-top: 54rpx;
		margin-bottom: 36rpx;
	}

	.scroll-content {
		width: 100%;
		height: 100%;
	}

	.scroll-item {
		display: inline-block;
	}
</style>
