<template>
	<view class="segmenter">
		<view class="title_inner">
			<uni-segmented-control :current="current" :values="items" @clickItem="onClickItem" style-type="text" active-color="orange"></uni-segmented-control>
		</view>

		<view class="content">
			<view v-show="current === 0">
				<!-- <view class="line" ></view> -->

				<view class="exhibition" v-for="item in 2">
					<navigator url=""><image class="course-image" src="../../static/2.jpg"></image></navigator>
					<!-- <view class="course-text"> -->

					<navigator url="" class="course-text">
						<text class="font1">启蒙儿歌40首</text>
						<text class="font2">简介：听歌学单词，开口即可说500词汇。</text>
					</navigator>

					<!-- <text>{{item.comment}}</text> -->
					<!-- <text wx:if='{{item.recommended}}' style="font-size: 16px; color: red;">强烈推荐</text> -->
					<!-- </view> -->
				</view>

				<!-- <view class="line" ></view> -->

				<view class="exhibition" v-for="item in 2">
					<navigator url=""><image class="course-image" src="../../static/2.jpg"></image></navigator>
					<!-- <view class="course-text"> -->

					<navigator url="" class="course-text">
						<text class="font1">启蒙儿歌40首</text>
						<text class="font2">简介：听歌学单词，开口即可说500词汇。</text>
					</navigator>

					<!-- <text>{{item.comment}}</text> -->
					<!-- <text wx:if='{{item.recommended}}' style="font-size: 16px; color: red;">强烈推荐</text> -->
					<!-- </view> -->
				</view>

				<!-- <view class="line" ></view> -->

				<view class="exhibition" v-for="item in 1">
					<navigator url=""><image class="course-image" src="../../static/2.jpg"></image></navigator>
					<!-- <view class="course-text"> -->

					<navigator url="" class="course-text">
						<text class="font1">启蒙儿歌40首</text>
						<text class="font2">简介：听歌学单词，开口即可说500词汇。</text>
					</navigator>

					<!-- <text>{{item.comment}}</text> -->
					<!-- <text wx:if='{{item.recommended}}' style="font-size: 16px; color: red;">强烈推荐</text> -->
					<!-- </view> -->
				</view>

				<!-- <view class="line" ></view> -->

				<view class="exhibition" v-for="item in 1">
					<navigator url=""><image class="course-image" src="../../static/2.jpg"></image></navigator>
					<!-- <view class="course-text"> -->

					<navigator url="" class="course-text">
						<text class="font1">启蒙儿歌40首</text>
						<text class="font2">简介：听歌学单词，开口即可说500词汇。</text>
					</navigator>

					<!-- <text>{{item.comment}}</text> -->
					<!-- <text wx:if='{{item.recommended}}' style="font-size: 16px; color: red;">强烈推荐</text> -->
					<!-- </view> -->
				</view>
			</view>

			<view v-show="current === 1">选项卡2的内容</view>
			<view v-show="current === 2">选项卡3的内容</view>
		</view>
	</view>
</template>

<script>
import uniSegmentedControl from '@/components/uni-segmented-control/uni-segmented-control.vue';
import uniList from '@/components/uni-list/uni-list.vue';
import uniListItem from '@/components/uni-list-item/uni-list-item.vue';

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
			items: ['综合排序', '活动', '新闻'],
			current: 0
		};
	},
	methods: {
		onClickItem(e) {
			if (this.current !== e.currentIndex) {
				this.current = e.currentIndex;
			}
		}
	}
};
</script>

<style>
.all {
	background-color: #ffffff;
}
.segmenter {
	margin-top: 10px;
}
.title_inner {
	width: 92%;
	margin: 0 auto;
	box-shadow: 0 4rpx 3rpx orange;
	background-color: rgba(0, 0, 0, 0.01);
	/* border-bottom: 4rpx solid rgb(255,0,0); */
	border-radius: 10rpx;
}
.content {
	margin: 25rpx;
}

.course-text {
	margin-left: 30rpx;
	display: flex;
	flex-direction: column;
	justify-content: space-around;
}

.exhibition {
	margin-top: 15rpx;
	display: flex;
	padding: 0rpx 10rpx;
}
.course-image {
	width: 200rpx;
	height: 200rpx;
	border-radius: 12rpx;
}
.font1 {
	font-size: 33rpx;
}

.font2 {
	font-size: 27rpx;
	color: rgba(0, 0, 0, 0.8);
}
</style>
