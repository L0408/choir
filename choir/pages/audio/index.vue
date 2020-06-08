<template>
	<view class="all">
		<view class="title">
			更多音频
		</view>
		
		<view class="" v-for="item in 20">
			<view class="audio">
				<audio :src="current.src" :poster="current.poster" :name="current.name" :author="current.author" :action="audioAction" controls></audio>
			</view>
		</view>
		<uni-load-more :status="more"></uni-load-more>
	</view>
	
</template>

<script>
	import uniLoadMore from "@/components/uni-load-more/uni-load-more.vue"

	export default {
		 components: {uniLoadMore},
	    data() {
	        return {
	            current: {
	                poster: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/audio/music.jpg',
	                name: '致爱丽丝',
	                author: '暂无',
	                src: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/audio/music.mp3',
	            },
	            audioAction: {
	                method: 'pause'
	            }
	        }
	    }
	}
</script>

<style>
	.all{
		background-color: #666666;
		width: 100%;
	}
	.title{
		
		font-size: 40rpx;
		text-align: center;
		
	}
	.audio{
		margin-top: 10rpx;
		margin-left: 30rpx;
	}
</style>
