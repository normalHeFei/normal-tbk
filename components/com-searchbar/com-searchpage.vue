<template>
	<view class="content-wrapper">
		<view class="content">
			<view class="left">
				<uni-icons type="search" size="18"></uni-icons>
				<input v-model="inputVal" @confirm="search" class="left-input" type="text" placeholder="请输入搜索内容" />
			</view>
			<view class="right" v-show="inputVal">
				<view @click="search">搜索</view>
			</view>
		</view>
		<view class="history" v-show="!inputVal">
			<view class="history-title">
				<text class="label-title">历史搜索</text>
				<uni-icons type="clear"></uni-icons>
			</view>
			<view class="labels">
				<view class="label" v-for="label in historyLabels" :key="label">
					{{label}}
				</view>
			</view>
		</view>
		<view class="recommend" v-show="!inputVal">
			<view class="recommend-title">
				<text class="label-title">猜你可能在找</text>
			</view>
			<view class="labels">
				<view class="label" v-for="label in recommendLabels "  :key="label">
					{{label}}
				</view>
			</view>
		</view>
	</view>

</template>

<script>
	export default {
		name: "com-searchpage",
		props: [
			
		],
		data() {
			return {
				inputVal: null,
				historyLabels: [],
				recommendLabels: []
			};
		},
		methods: {
			clear() {
				this.inputVal = null;
			},
			search() {
				if (!this.inputVal) {
					return;
				}
				try{
					const localhistory =  uni.getStorageSync('history');
					if(!localhistory){
						localhistory = [];
					}
					localhistory.push(this.inputVal);
					uni.setStorageSync('history', localhistory);
				}catch(e){
					console.error(e);
				}
				console.log('input val: ', this.inputVal);
				//todo:
				uni.redirectTo({
					url: '../../pages/search/search?' + this.inputVal,
				});
			}
		},
		
		//生命周期方法
		onLoad() {
			try{
				const labels = uni.getStorageSync('history');
				this.historyLabels = labels;
				
				//recommend labels 
				
			}catch(e){
				console.error(e);
			}
		}
	}
</script>

<style scoped>
	.content-wrapper {
		display: flex;
		flex-direction: column;
	}

	.content {
		margin-top: 10rpx;
		display: flex;
		flex-wrap: nowrap;
		justify-content: space-between;
	}

	.left {
		flex: 10;
		display: flex;
		justify-content: flex-start;
		align-items: center;
		border: #808080 1rpx solid;
		border-radius: 10rpx;
		height: 60rpx;
	}

	.right {
		flex: 1;
		border: #808080 1rpx solid;
		border-radius: 10rpx;
		color: #808080;
	}

	.history-title {
		display: flex;
		justify-content: space-between;
	}

	.labels {
		display: flex;
		justify-content: space-around;
	}

	.label {
		background-color: #EEEEEE;
		border-radius: 10rpx;
	}

	.recommend-title {
		display: flex;
		justify-content: flex-start
	}
	
	.label-title{
		font-size: large;
		font-weight: bold;
	}

	.history{
		margin-top: 20rpx;
	}
	.recommend{
		margin-top: 20rpx;
	}
 
</style>
