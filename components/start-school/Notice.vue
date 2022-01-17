<template>
	<view class="notice">
		<view class="notice-item">
			<view class="notice-text notice-warning">
				<image class="notice-img" src="../../static/imgs/upgrade.png" mode=""></image>
				<text>我是第一条公告内容！</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		}
	}
</script>

<style scoped>
	.notice-item {
		width: 674rpx;
		height: 60rpx;
		padding-bottom: 20rpx;
	}

	.notice-img {
		width: 29rpx;
		height: 29rpx;
	}

	.notice-text {
		width: 100%;
		height: 60rpx;
		border-radius: 12rpx;
		display: flex;
		align-items: center;
		background: rgba(53, 140, 248, .12);
		border: 2rpx solid #358cf8;
		color: #358cf8;
		font-size: 30rpx;
		padding: 0 20rpx;
		box-sizing: border-box;
	}

	.notice-warning {
		background: rgba(222, 160, 0, .12);
		border: 2rpx solid #f88c35;
		color: #f88c35;
	}
</style>
