<template>
	<view class="">
		<view class="title_inner">
			<uni-segmented-control :current="current" 
			:values="items" @clickItem="onClickItem" 
			style-type="text" 
			active-color="red">
			</uni-segmented-control>
		</view>
		        <view class="content">
		            <view v-show="current === 0">
						<view class="image_">
							<image src="../../static/2.jpg" mode="" class="image"></image>
						</view>
		               <uni-list>
		                   <uni-list-item title="" :show-arrow="false">Red Rocket Readers红火箭分级阅读</uni-list-item>
						   <uni-list-item title="" :show-arrow="false"><view class="space">
						   <text class="font1">¥188 | 206节</text>
						   <text class="font2">销量：99+</text>
						   </view></uni-list-item>
						  <uni-collapse accordion="true">
						      <uni-collapse-item title="课程简介">
						          <view style="padding: 30rpx;">
									  <text class="font3">
										  商品详情（图文介绍)商品详情（图文介绍)商品详情（图文介绍)商品详情（图文介绍)
									  </text>
						          </view>
						      </uni-collapse-item>
						     
						  </uni-collapse>
							   <view class="details">
							   	<text class="font4">商品详情（图文介绍)</text>
							   	<image src="../../static/1.jpg" mode="" class="details_img"></image>
							   </view>
							</uni-list-item>

		                   <!-- <uni-list-item title="标题文字"></uni-list-item> -->
		                  
		               </uni-list>
		            </view>
		            <view v-show="current === 1">
		                <view class="image_">
		                	<image src="../../static/2.jpg" mode="" class="image"></image>
		                </view>
						<uni-list>
						    <uni-list-item title="" :show-arrow="false"><text>Alphabet Explorers</text></uni-list-item>
							<uni-list-item title="" :show-arrow="false">
								<view class="cont">
									<image src="../../static/1.jpg" mode="" class="cont_img"></image>
									<text class="font5">Alphabet Explorers-A</text>
								</view>
							</uni-list-item>
							<uni-list-item title="" :show-arrow="false">
								<view class="cont">
									<image src="../../static/1.jpg" mode="" class="cont_img"></image>
									<text class="font5">Alphabet Explorers-B</text>
								</view>
							</uni-list-item>
						</uni-list>
						
		            </view>
		            <view v-show="current === 2">
		                <view class="image_">
		                	<image src="../../static/2.jpg" mode="" class="image"></image>
		                </view>
						<uni-list>
						    <uni-list-item title="" :show-arrow="false"><view class="space">
								<text>Alphabet Explorers</text>
								<text class="font6">可试听</text>
							</view></uni-list-item>
							<uni-list-item title="" :show-arrow="false">
								<view class="cont">
									<image src="../../static/1.jpg" mode="" class="cont_img"></image>
									<text class="font5">Alphabet Explorers-A</text>
								</view>
							</uni-list-item>
							<uni-list-item title="" :show-arrow="false">
								<view class="cont">
									<image src="../../static/1.jpg" mode="" class="cont_img"></image>
									<text class="font5">Alphabet Explorers-B</text>
								</view>
							</uni-list-item>
							<uni-list-item title="" :show-arrow="false">
								<view class="cont">
									<image src="../../static/1.jpg" mode="" class="cont_img"></image>
									<text class="font5">Alphabet Explorers-B</text>
								</view>
							</uni-list-item>
						</uni-list>
		            </view>
		        </view>
	<view class="add_btn">
			<uni-goods-nav :fill="true"  
			:options="options" 
			:buttonGroup="buttonGroup"  
			@click="onClick"
			 @buttonClick="buttonClick" />
	</view>
	</view>
</template>

<script>
	import uniList from "@/components/uni-list/uni-list.vue"
	import uniListItem from "@/components/uni-list-item/uni-list-item.vue"
	import uniSegmentedControl from '@/components/uni-segmented-control/uni-segmented-control.vue'
	import uniGoodsNav from '@/components/uni-goods-nav/uni-goods-nav.vue'
	import uniCollapse from '@/components/uni-collapse/uni-collapse.vue'
	import uniCollapseItem from '@/components/uni-collapse-item/uni-collapse-item.vue'
	export default {
		components: {
			uniSegmentedControl,
			uniList,
			uniListItem,
			uniGoodsNav,
			uniCollapse,
			uniCollapseItem
		},
		
		data() {
			return {
				items: ['图文详情', '目录', '试听页'],
				current: 0,
				 options: [{
				            icon: 'headphones',
				            text: '咨询'
				        },  {
				            icon: 'cart',
				            text: '收藏数',
				            info: 2
				        }],
				        buttonGroup: [{
				          text: '加入收藏',
				          backgroundColor: '#ff0000',
				          color: '#fff'
				        },
				        {
				          text: '立即购买',
				          backgroundColor: '#ffa200',
				          color: '#fff'
				        }
				        ]
			};
		},
		methods: {
			onClickItem(e) {
				if (this.current !== e.currentIndex) {
					this.current = e.currentIndex;
				}
			},
			onClick (e) {
			        uni.showToast({
			          title: `点击${e.content.text}`,
			          icon: 'none'
			        })
			      },
			      buttonClick (e) {
			        console.log(e)
			        
			      }
		}
	};
</script>

<style>
	
	.image_{
		
		text-align: center;
		
	}
	
	.image{
		margin-top: 20rpx;
		border-radius: 20rpx;
		width: 90%;
		/* height: ; */
	}
	.title_inner {
		width: 70%;
		margin: 0 auto;
		/* box-shadow: 0 0rpx 3rpx #00a0ff; */
		/* background-color: rgba(0, 0, 0, 0.01); */
		/* border-bottom: 4rpx solid rgb(255,0,0); */
		border-radius: 10rpx;
	}
	
	.font1{
		font-size: 35rpx;
		color: #FF2000;
	}
	.font2{
		font-size: 30rpx;
		color: #999999;
	}
	.font3{
		font-size: 30rpx;
		color: #999999;
	}
	.font4{
		margin-top: 20rpx;
		font-size: 40rpx;
		color: #555555;
	}
	.font5{
		margin-top: 20rpx;
		margin-left: 100rpx;
	}
	.font6{
		color: red;
	}
	.space{
		display: flex;
		justify-content: space-between;
	}
	.details{
		text-align: center;
	}
	
	.add_btn{
	    width: 100%;
	    /* display: flex; */
		position: fixed;
	    bottom: 0rpx;
		/* height: auto; */
		
	}
	.btn1{
		
	    margin-top: 30rpx;
	    width: 25%;
	    background-color: #663333;
	    color:  #FFFFFF;
	    border-radius: 50rpx;
		margin-left: 20rpx;
		
	}
	.btn2{
		
	    margin-top: 30rpx;
	    width: 30%;
	    background-color: #ff8040;
	    color:  #FFFFFF;
	    border-radius: 50rpx;
		margin-left: 80rpx;
		
		
	}
	.btn3{
		
	    margin-top: 30rpx;
	    width: 30%;
	    background-color: #ff2000;
	    color: #FFFFFF;
	    border-radius: 50rpx;
		margin-right: 20rpx;
	}
	.details_img{
		margin-top: 20rpx;
		width: 99%;
	}
	.cont{
		display: flex;
		width: 100%;
	}
	
	.cont_img{
		width: 100rpx;
		height: 100rpx;
	}


</style>