<template>
	
	<view class="all">
		<view class="pic">
			<image src="../../static/2.jpg" mode="">test!!</image>
		</view>
		<view class="">
			<view>
			        <uni-segmented-control :current="current" :values="items" @clickItem="onClickItem" style-type="button" active-color="#4cd964"></uni-segmented-control>
			        <view class="content">
			            <view v-show="current === 0">
			                选项卡1的内容
			            </view>
			            <view v-show="current === 1">
			                选项卡2的内容
			            </view>
			            <view v-show="current === 2">
			                选项卡3的内容
			            </view>
			        </view>
			    </view>
		</view>
		
	</view>
</template>

<script>
	import uniSegmentedControl from "@/components/uni-segmented-control/uni-segmented-control.vue"
	
	export default {
		components: {
			uniSegmentedControl
		},
		components: {
			uniList,
			uniListItem
		},
		data() {
			return {
				items: ['综合排序', '2-4', '5-7'],
				current: 0
			}
		},
		methods: {
			onClickItem(e) {
				if (this.current !== e.currentIndex) {
					this.current = e.currentIndex;
				}
			}
		}
	}
	
</script>

<style>
</style>
