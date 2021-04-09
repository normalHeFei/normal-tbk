<template>
	<view class="content" :style="size">
		<text class="cont-title">{{title}}</text>
		<image :src="image"></image>
		<view class="price">
			<text class="old-price">{{orignalPrice}}</text>
			<text class="now-price">{{nowPrice}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		name: "com-goodsitem",
		props: {
			title: String,
			image: String,
			orignalPrice: [Number, String],
			nowPrice: [Number, String],
			size: {
				type: Object,
				default: function() {
					return {
						width: 350,
						height: 400
					}
				}
			}
		},
		data() {
			return {

			}
		},
		methods: {

		},
		onLoad() {

		}
	}
</script>

<style scoped>
	.content {
		display: flex;
		flex-direction: column;
	}
	.cont-title{
		font-size: medium;
	}
	.price{
		display: flex;
		justify-content: space-around;
	}
	.old-price {
		text-decoration: line-through;
		font-size: medium;
	}
	.now-price {
		font-weight: bold;
		color: #DD524D;
		font-size: larger;
	}
</style>
