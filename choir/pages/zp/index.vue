<template>


	<view class="segmenter">

		<view class="title_inner">
			<uni-segmented-control :current="current" :values="items" @clickItem="onClickItem" style-type="text" active-color="red">
			</uni-segmented-control>
		</view>

		<view class="content">
			<view v-show="current === 0">
				<!-- <view class="line" ></view> -->

				<view class="exhibition" v-for="item in 2">
					<navigator url="">
						<image class="course-image" src="../../static/2.jpg"></image>
					</navigator>
					<!-- <view class="course-text"> -->

					<navigator url="" class="course-text">
						<text class="font1">课程名字：启蒙儿歌40首</text>
						<text class="font2"> 简介：听歌学单词，开口即可说500词汇。</text>
					</navigator>


					<!-- <text>{{item.comment}}</text> -->
					<!-- <text wx:if='{{item.recommended}}' style="font-size: 16px; color: red;">强烈推荐</text> -->
					<!-- </view> -->
				</view>

				<!-- <view class="line" ></view> -->

				<view class="exhibition" v-for="item in 2">
					<navigator url="">
						<image class="course-image" src="../../static/2.jpg"></image>
					</navigator>
					<!-- <view class="course-text"> -->

					<navigator url="" class="course-text">
						<text class="font1">课程名字：启蒙儿歌40首</text>
						<text class="font2"> 简介：听歌学单词，开口即可说500词汇。</text>
					</navigator>

					<!-- <text>{{item.comment}}</text> -->
					<!-- <text wx:if='{{item.recommended}}' style="font-size: 16px; color: red;">强烈推荐</text> -->
					<!-- </view> -->
				</view>

				<!-- <view class="line" ></view> -->

				<view class="exhibition" v-for="item in 1">
					<navigator url="">
						<image class="course-image" src="../../static/2.jpg"></image>
					</navigator>
					<!-- <view class="course-text"> -->

					<navigator url="" class="course-text">
						<text class="font1">课程名字：启蒙儿歌40首</text>
						<text class="font2"> 简介：听歌学单词，开口即可说500词汇。</text>
					</navigator>

					<!-- <text>{{item.comment}}</text> -->
					<!-- <text wx:if='{{item.recommended}}' style="font-size: 16px; color: red;">强烈推荐</text> -->
					<!-- </view> -->
				</view>

				<!-- <view class="line" ></view> -->
				
				<view class="exhibition" v-for="item in 1">
					<navigator url="">
						<image class="course-image" src="../../static/2.jpg"></image>
					</navigator>
					<!-- <view class="course-text"> -->
				
					<navigator url="" class="course-text">
						<text class="font1">课程名字：启蒙儿歌40首</text>
						<text class="font2"> 简介：听歌学单词，开口即可说500词汇。</text>
					</navigator>
				
					<!-- <text>{{item.comment}}</text> -->
					<!-- <text wx:if='{{item.recommended}}' style="font-size: 16px; color: red;">强烈推荐</text> -->
					<!-- </view> -->
				</view>

			</view>






			<view v-show="current === 1">
				选项卡2的内容
			</view>
			<view v-show="current === 2">
				选项卡3的内容
			</view>
		</view>
	</view>

</template>

<script>
	import uniSegmentedControl from "@/components/uni-segmented-control/uni-segmented-control.vue"
	import uniList from "@/components/uni-list/uni-list.vue"
	import uniListItem from "@/components/uni-list-item/uni-list-item.vue"

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
				items: ['小样', '涛叔', '新耳朵乐队'],
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
	.all {
		background-color: #FFFFFF;
	}

	.title {
		font-size: 35rpx;
		text-align: center;
	}

	.title_inner {
		width: 80%;
		margin: 0 auto;
		box-shadow: 0 3px 3px rgba(0, 0, 0, 0.7);
	}

	.line {
		width: 90%;
		height: 5rpx;
		margin: auto;
		background-color: rgba(0, 0, 0, 0.4);
		margin-top: 10rpx;
	}

	.segmenter {
		margin-top: 10px;

	}

	.title_text {
		font-size: 35rpx;
		font-style: normal;
		margin-top: 15rpx;
		margin-left: 20rpx;
	}

	.font1 {
		font-weight: 400;
		font-size: 35rpx;
		color: rbg(255, 255, 255);
		/* display: block; */
		background-color: #007AFF;
		border: 2rpx dashed;
	}

	.font2 {
		font-weight: 400;
		font-size: 25rpx;
		color: rgba(0, 0, 0, 0.8);
/* 		display: block;
		display: flex;
		align-items: flex-end; */
		background-color: #007AFF;
		border: 2rpx dashed;
	}

	.font3 {
		font-weight: 400;
		font-size: 30rpx;
		color: rgba(255, 0, 0, 1);
		/* margin-top: 50rpx; */
		display: block;
/* 		display: flex;
		align-items:baseline; */
		background-color: #007AFF;
		border: 2rpx dashed;
	}

	.exhibition {
		margin-top: 15rpx;
		display: flex;
		padding: 0rpx 10rpx;
	}

	.course-text {
		margin-left: 30rpx;
		display: flex;
		flex-direction: column;
		/* align-items; */

	}

	.course-image {

		width: 200rpx;
		height: 200rpx;
		border-radius: 15rpx;
	}
</style>
