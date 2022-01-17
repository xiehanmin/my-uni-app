<template>
	<view>
		<text>面试流程</text>
		<MyTabBar :selected="selected" />
	</view>
</template>

<script>
	import MyTabBar from '@/common/tabBar/my-tabBar.vue'
	export default {
		data() {
			return {
				selected: 2
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
