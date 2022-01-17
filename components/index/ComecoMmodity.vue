<template>
	<view class="home-main">
		<block v-for="(item, index) in homeData" :key="index">
			<HomeItem :item="item"></HomeItem>
		</block>
	</view>
</template>

<script>
	import HomeItem from '@/components/index/HomeItem.vue'
	export default {
		data() {
			return {
				homeData: [{
					classImgLink: 'https://test.cloudapprod.com/api/profile/wechat/bgimg/p4.png',
					className: '音乐室'
				}, {
					classImgLink: 'https://test.cloudapprod.com/api/profile/wechat/bgimg/p4.png',
					className: '舞蹈室'
				}, {
					classImgLink: 'https://test.cloudapprod.com/api/profile/wechat/bgimg/p4.png',
					className: '棋室'
				}, {
					classImgLink: 'https://test.cloudapprod.com/api/profile/wechat/bgimg/p4.png',
					className: '画室'
				}, {
					classImgLink: 'https://test.cloudapprod.com/api/profile/wechat/bgimg/p4.png',
					className: '其他兴趣班'
				}]
			}
		},
		components: {
			HomeItem
		}
	}
</script>

<style scoped>
	.home-main{
		width: 676rpx;
		margin: 20rpx 0 0 36rpx;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		align-items: center;
	}
</style>
