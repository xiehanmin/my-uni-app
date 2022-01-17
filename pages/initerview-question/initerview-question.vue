<template>
	<view>
		<text>刷面试题</text>
		<MyTabBar :selected="selected" />
	</view>
</template>

<script>
	import MyTabBar from '@/common/tabBar/my-tabBar.vue'
	export default {
		data() {
			return {
				selected: 1
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
