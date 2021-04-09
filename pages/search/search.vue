<template>
	<view class="content">
		<com-searchbar :onClickSearch="onClickSearch" :onClickMore="onClickMore"></com-searchbar>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				goods: [{
					id: 1,
					title: '示例产品',
					image: 'https://img.zcool.cn/community/0148e859198029b5b3086ed4d79814.jpg@1280w_1l_2o_100sh.jpg',
					oldPrice: 102.2,
					nowPrice: 50
				}]
			}
		},
		onLoad() {
			
		},
		methods: {
			onClickSearch(){
				uni.navigateTo({
					url: '../../components/com-searchbar/com-searchpage',
					complete(rst) {
						console.log('rst: ', rst);
					}
				})
			},
			onClickMore(){
				console.log('on click more');
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		align-items: center;
		flex-wrap: wrap;
		justify-content: center;
		width: 100%;
	}

	.goods-item {
		display: flex;
		flex-wrap: nowrap;
		justify-content: space-around;
	}
</style>
