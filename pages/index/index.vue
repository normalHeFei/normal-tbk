<template>
	<view class="content">
		<scroll-view @scroll="scroll" scroll-y="true" class="scroll-Y">
			<view v-for="item in configIdxs" class="scroll-view-item ">
				<view class="group">
					<view class="group-title">{{item.title}}</view>
					<image class="group-image" :src="item.imageUrl" mode="scaleToFill" lazy-load="true"></image>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				configIdxs: [{
					id: 'xxx',
					title: '标题1',
					imageUrl: 'https://tse1-mm.cn.bing.net/th/id/OET.2e14ecaf0a104203b02244ce1535876f?w=272&h=272&c=7&rs=1&o=5&pid=1.9',
					order: 1
				}, {
					id: 'xxx',
					title: '标题1',
					imageUrl: 'https://tse1-mm.cn.bing.net/th/id/OET.2e14ecaf0a104203b02244ce1535876f?w=272&h=272&c=7&rs=1&o=5&pid=1.9',
					order: 1
				}, {
					id: 'xxx',
					title: '标题1',
					imageUrl: 'https://tse1-mm.cn.bing.net/th/id/OIP.wvCjZCj5h6u5jk8-cdJyHgHaNK?pid=ImgDet&rs=1',
					order: 1
				}, {
					id: 'xxx',
					title: '标题1',
					imageUrl: 'https://tse1-mm.cn.bing.net/th/id/OET.2e14ecaf0a104203b02244ce1535876f?w=272&h=272&c=7&rs=1&o=5&pid=1.9',
					order: 1
				}]
			}
		},
		onTabItemTap(){
			console.log('tab item tap')
			
		},
		methods: {
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-around;
	}

	.group {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
</style>
