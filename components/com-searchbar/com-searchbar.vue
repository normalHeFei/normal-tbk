<template>
	<view class="com-sear-container">
		<view class="com-sear-ipt" v-on:click.stop="onClickSearch">
			<uni-icons type="search" size="18"></uni-icons>
			<text class="com-sear-ipt-txt">请输入搜索内容</text>
		</view>
		<view class="com-sear-more" v-on:click.stop="onClickMore">
			<uni-icons type="bars" size="30"></uni-icons>
		</view>
	</view>
</template>

<script>
	export default {
		name: "com-searchbar",
		props: {
			onClickSearch: Function,
			onClickMore: Function
		},
		data() {
			return {

			};
		},
		methods: {
			 

		}
	}
</script>

<style scoped>
	.com-sear-container {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-left: 10rpx;
		margin-top: 10rpx;
		width: 100%;
	}

	.com-sear-ipt {
		display: flex;
		justify-content: flex-start;
		align-items: center;
		flex: 10;
		border-radius: 10rpx;
		border-style: solid;
		border-color: #808080;
		border-width: 1rpx;
		height: 60rpx;
	}
	.com-sear-ipt-txt{
		size: 18;
	}
	.com-sear-more {
		flex: 1;
	}

	text {
		color: #808080;
	}
</style>
