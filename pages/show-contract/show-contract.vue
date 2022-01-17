<template>
	<view class="show-contract">
		<view class="contract-header">
			<image src="https://fawn.xuexiluxian.cn/api/profile/wechat/bgimg/title.png" mode=""></image>
		</view>
		<scroll-view scroll-y="true" :style="{height:clientHeight+'px'}">
			<view class="contract">
				<view class="show-contract-content">
					<view class="sign-item">
						<view class="sign-bg-title">
							<view class="item-title">
								实训室
							</view>
						</view>
						<view class="item-content">
							<view class="item-text">
								<rich-text>学习周期1个月</rich-text>
								<rich-text>学习周期12个月</rich-text>
								<rich-text>学习周期14个月</rich-text>
							</view>
						</view>
						<view class="sign-bg-footer">
							<view class="">
								sdfsdf
							</view>
						</view>
					</view>
					<view class="sign-item">
						<view class="sign-bg-title">
							<view class="item-title">
								实训室
							</view>
						</view>
						<view class="item-content">
							<view class="item-text">
								<rich-text>学习周期1个月</rich-text>
								<rich-text>学习周期12个月</rich-text>
								<rich-text>学习周期14个月</rich-text>
							</view>
						</view>
						<view class="sign-bg-footer">
							<view class="">
							</view>
						</view>
					</view>
					<view class="sign-item">
						<view class="sign-bg-title">
							<view class="item-title">
								实训室
							</view>
						</view>
						<view class="item-content">
							<view class="item-text">
								<rich-text>学习周期1个月</rich-text>
								<rich-text>学习周期12个月</rich-text>
								<rich-text>学习周期14个月</rich-text>
							</view>
						</view>
						<view class="sign-bg-footer">
							<view class="">
								sdfsdf
							</view>
						</view>
					</view>
					<view class="sign-item">
						<view class="sign-bg-title">
							<view class="item-title">
								实训室
							</view>
						</view>
						<view class="item-content">
							<view class="item-text">
								<rich-text>学习周期1个月</rich-text>
								<rich-text>学习周期12个月</rich-text>
								<rich-text>学习周期14个月</rich-text>
							</view>
						</view>
						<view class="sign-bg-footer">
							<view class="">
								sdfsdf
							</view>
						</view>
					</view>
					<view class="sign-item">
						<view class="sign-bg-title">
							<view class="item-title">
								实训室
							</view>
						</view>
						<view class="item-content">
							<view class="item-text">
								<rich-text>学习周期1个月</rich-text>
								<rich-text>学习周期12个月</rich-text>
								<rich-text>学习周期14个月</rich-text>
							</view>
						</view>
						<view class="sign-bg-footer">
							<view class="">
								sdfsdf
							</view>
						</view>
					</view>
				</view>
			</view>
		</scroll-view>
		<view class="know">
			<view class="contract-know" @tap="goBack">
				我知道了
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				clientHeight: null
			}
		},
		onReady() {
			uni.getSystemInfo({
				success: (res) => {
					///获取头部的高度 select 里面的参数和CSS选择器一样选择元素
					let info = uni.createSelectorQuery().in(this).select(".contract-header")
					info.boundingClientRect((data) => {
						this.clientHeight = res.windowHeight - data.height
					}).exec(function(res) {
						//这个方法必须执行，即使什么也不做，否则不会获取到信息
					})
					let konwInfo = uni.createSelectorQuery().in(this).select(".know")
					konwInfo.boundingClientRect((data) => {
						this.clientHeight = this.clientHeight - data.height
					}).exec(function(res) {
						//这个方法必须执行，即使什么也不做，否则不会获取到信息
					})

				}
			})
		},
		methods: {
			goBack() {
				uni.navigateBack({
					delta: 1
				})
			}

		}
	}
</script>

<style scoped>
	scroll-view ::-webkit-scrollbar {
		display: none;
		width: 0 !important;
		height: 0 !important;
		-webkit-appearance: none;
		background: transparent;
		color: transparent;
	}

	.show-contract {
		width: 750rpx;
		height: 100vh;
		padding-bottom: 200rpx;
		box-sizing: border-box;
		background: url('https://fawn.xuexiluxian.cn/api/profile/wechat/bgimg/sign-bg.png') no-repeat;
	}

	.contract-header {
		width: 100vw;
		height: 300rpx;
		position: relative;

	}

	.contract-header image {
		width: 622rpx;
		height: 93rpx;
		position: absolute;
		left: 50%;
		top: 150rpx;
		transform: translateX(-50%);
	}

	.contract {
		width: 703rpx;
		padding: 0 24rpx;
		padding-bottom: 60rpx;
	}

	.sign-item {
		width: 702rpx;
		margin-bottom: 60rpx;

	}

	.sign-bg-title {
		width: 702rpx;
		height: 100rpx;
		background: url('https://fawn.xuexiluxian.cn/api/profile/wechat/bgimg/sign-bg-title.png') no-repeat;
		background-size: 100% 100%;
		position: relative;
	}

	.item-title {
		position: absolute;
		left: 50%;
		top: 10rpx;
		transform: translateX(-50%);
		font-size: 48rpx;
		font-weight: normal;
		color: #5d6fe5;
		line-height: 60rpx;
	}

	.item-content {
		width: 702rpx;
		background: url('https://fawn.xuexiluxian.cn/api/profile/wechat/bgimg/item-bg.png') no-repeat;
		background-size: 100% 100%;
		position: relative;
	}

	.sign-bg-footer {
		width: 702rpx;
		height: 100rpx;
		background: url('https://fawn.xuexiluxian.cn/api/profile/wechat/bgimg/sign-bg-footer.png') no-repeat;
		background-size: 100% 100%;
		position: relative;
	}

	.item-text {
		padding: 20rpx 40rpx;
		font-size: 30rpx;
		font-family: Microsoft Yahei;
		color: #7a8bff;
	}

	.know {
		width: 100vw;
		height: 200rpx;
		position: relative;
	}

	.contract-know {
		width: 520rpx;
		height: 80rpx;
		font-size: 30rpx;
		font-family: Microsoft Yahei;
		font-weight: normal;
		color: #5D6FE5;
		text-align: center;
		line-height: 80rpx;
		background-color: #FFFFFF;
		position: absolute;
		left: 50%;
		top: 50%;
		transform: translate(-50%, -50%);
		border-radius: 20rpx;
	}
</style>
