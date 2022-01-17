<template>
	<view>
		<text>我的名片</text>
		<MyTabBar :selected="selected" />
	</view>
</template>

<script>
	import MyTabBar from '@/common/tabBar/my-tabBar.vue'
	export default {
		data() {
			return {
				selected: 4
			}
		},
		methods: {
			
		},
		components: {
			MyTabBar
		}
	}
</script>

<style>

</style>
