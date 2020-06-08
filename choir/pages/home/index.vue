<template>
	<view>
	<!-- 轮播图 开始 -->
	<view class="home_swiper">
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item v-for="item in banners":key='item.id'>
				<image :src="item.thumb" mode="widthFix"></image>
			</swiper-item>
			
		</swiper>
	</view>
	<!-- 轮播图 结束 -->
	
	<!-- 目录 开始 -->
	<view class="menu">
		
		<navigator url="/pages/english/index" class="menu-item" v-for="item in 4">
			<image src="../../static/logo.png" mode="widthFix" class="menu-img"></image>
			<text class="menu-name">英文</text>
		</navigator>
		<navigator url="/pages/zp/index" class="menu-item">
			<image src="../../static/logo.png" mode="widthFix" class="menu-img"></image>
			<text class="menu-name">作品</text>
		</navigator>
		<navigator url="/pages/news/index" class="menu-item">
			<image src="../../static/logo.png" mode="widthFix" class="menu-img"></image>
			<text class="menu-name">活动</text>
		</navigator>
		
	</view>
	

	<!-- 目录 结束 -->
	
	<!-- 间隔 -->
	<view class="interval">	</view>
	
	<!-- 叔叔头条(音频) 开始 -->
	<view class="music_wrap">
		<view class="music_title">
			<view class="title_info">叔叔头条(音频)</view>
			<navigator url="/pages/audio/index" class="title_more">查看更多(学堂)</navigator>
		</view>
		<view>
		     <view class="music_content">
		            <view class="into">
						
		                <audio :src="current.src" poster="../../static/1.jpg" name=" Today is Monday." author="0531 "  controls>	
						</audio>
					
					</view>
		        </view>
				<view class="music_content">
				       <view>
				           <audio  :src="current.src" :poster="current.poster" :name="current.name" :author="current.author"  controls></audio>
				       </view>
				   </view>
		    </view>
		
	</view>
	<!-- 叔叔头条(音频) 结束 -->
	
	<!-- 间隔 -->
	<view class="interval">	</view>
	
	<!-- 叔叔快手(短视频) 开始 -->
	<view class="video_warp">
		<view class="video_title">
			<view class="title_info">叔叔快手(短视频)</view>
			<navigator url="/pages/video/index" class="title_more">查看更多(学堂)</navigator>
		</view>
		<view class="video_item">
		
		<view class="video_content">
			<navigator url="">
				<image src="../../static/1.jpg"  class="video"></image>
				<!-- <image src="../../static/4.jpg" mode="" ></image> -->
				<!-- <button type="default"></button> -->
				 
				<text>视频介绍</text>
			</navigator>
		</view>
		<view class="video_content">
			<navigator url="">
				<image src="../../static/2.jpg" class="video"></image>
				<text>视频介绍</text>
			</navigator>
		</view>
		<view class="video_content">
			<navigator url="">
				<image src="../../static/3.jpg" class="video"></image>
				<text>视频介绍</text>
			</navigator>
		</view>
	</view>
	</view>
	<!-- 叔叔快手(短视频) 结束 -->
	
	<!-- 间隔 -->
	<view class="interval"></view>
	
	<!-- 热门好课(可试听) 开始-->
	<view class="course_warp">
		<view class="course_title">
			<text class="title_content">热门好课(可试听)</text>
			<view class="line"></view>
		</view>
		<view class="course_content">
			<view class="course_item">
				<navigator url="">
					<image src="../../static/1.jpg"  class="course_video"></image>
				</navigator>
			</view>
			<view class="course_item">
				<navigator url="">
					<image src="../../static/2.jpg"  class="course_video"></image>
				</navigator>
			</view>
			<view class="course_item">
				<navigator url="">
					<image src="../../static/3.jpg"  class="course_video"></image>
				</navigator>
			</view>
			<view class="course_item">
				<navigator url="">
					<image src="../../static/logo.png"  class="course_video"></image>
				</navigator>
			</view>
			<navigator url="" class="more">查看更多(学堂)</navigator>
		</view>
	</view>
	
	<!-- 热门好课(可试听) 结束-->
	
	<!-- 间隔 -->
	<view class="interval">	</view>
	
	<!-- 英文/语文/通识/音乐/作品 开始 -->
	
	<view class="course_warp">
		<view class="course_title">
			<text class="title_content">英文/语文/通识/音乐/作品</text>
			<view class="line"></view>
		</view>
		<view class="course_content">
			<view class="course_item">
				<navigator url="">
					<image src="../../static/1.jpg"  class="course_video"></image>
				</navigator>
			</view>
			<view class="course_item">
				<navigator url="">
					<image src="../../static/2.jpg"  class="course_video"></image>
				</navigator>
			</view>
			<view class="course_item">
				<navigator url="">
					<image src="../../static/3.jpg"  class="course_video"></image>
				</navigator>
			</view>
			<view class="course_item">
				<navigator url="">
					<image src="../../static/logo.png"  class="course_video"></image>
				</navigator>
			</view>
			<navigator url="" class="more">查看更多(学堂)</navigator>
			<view class="down"></view>
		</view>
	</view>
	
	<!-- 英文/语文/通识/音乐/作品 结束 -->
	</view>
</template>



<script>
export default{
// https://service.picasso.adesk.com/v1/wallpaper/album
// http://www.tp5.com/index.php/index/index/index
data(){
	return{
		banners:[],
		current: {
		                poster: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/audio/music.jpg',
		                name: '致爱丽丝',
		                author: '暂无',
		                src: 'https://img-cdn-qiniu.dcloud.net.cn/uniapp/audio/music.mp3',
		            },
		           
	}
},



  
mounted() {
	//  测试接口
	this.request({
		url:'https://service.picasso.adesk.com/v1/wallpaper/album',
		data:{
			//要获取几条数据
			limit:30,
			//关键字
			order:'hot',
			skip:0
		}
	})
	.then(result=>{
		console.log(result);
		this.banners=result.res.banner;
		
	})
	
	// 自己写的测试接口
		this.request({
			url:'http://www.tp5.com/index.php/index/index/index',
			data:{
				//要获取几条数据
				limit:30,
				//关键字
				order:'hot',
				skip:0
			}
		})
		.then(result=>{
			console.log(result);
			
			
		})
	
}


// mounted() {
// 	this.request({
// 		url:'http://www.tp5.com/index.php/index/index/index',
// 		data:{
// 			//要获取几条数据
// 			limit:30,
// 			//关键字
// 			order:'hot',
// 			skip:0
// 		}
// 	})
// 	.then(result=>{
// 		console.log(result);
// 		this.banners=result;
		
// 	})
// }

}

</script>




<style lang='scss' scoped>
		.home_swiper{
			swiper{
				/* width: 100%; */
				height:calc(750rpx/2.3);
				image{
					height:100%;
					width: 100%;
				}
			}
		}

	</style>
	
	<style>
		/* 目录 开始 */
		.menu{
				margin-top: 50rpx;
				
				display: flex;        /*弹性布局*/
				flex-wrap: wrap;     /*允许换行*/
			}
		.menu-item{
			
			text-align: center;
			display: flex;
			flex-direction: column;
			width: 25%;      /*一行排四个icon，每个icon占比25%*/
			margin-top: 20rpx;
			box-sizing: border-box;
		}
		
		.menu-name{
			margin-top: 10rpx;
			display:flex;
			justify-content: center;
			text-align: center;
		}
		
		.menu-img{
			margin-left: 28%;
			display: flex;
			justify-content: center;
			
			width: 80rpx;
			height: 80rpx;
		}
		
		/* 目录 结束 */
		
		/* 间隔 */
		.interval{
			margin-top: 50rpx;
			background-color: #F1F1F1;
			height: 20rpx;
			width: 100%;
		}
		
		/* 叔叔头条(音频) 开始 */
		.music_wrap{
			margin-top: 50rpx;
		}
		
		.music_title{
			margin-left: 40rpx;
			border-left: 10rpx solid #ff8020;
			display: flex;
			justify-content: space-between;
			
		}
		.title_info{
			margin-left: 20rpx;
			font-size: 30rpx;
		}
		
		.title_more{
			margin-right: 40rpx;
			font-size: 30rpx;
			color: #8F8F94;
		}
		
		.music_content{
			
			display: flex;
			/* border: 1rpx solid F1F1F1; */
			margin:10rpx;
			height: 100rpx;
			/* box-shadow:2px 2px 2px 2px #F1F1F1; */
			margin-top: 30rpx;
			margin-left: 80rpx;
		
		}
		.play_image{
			margin-left: 30rpx;
			width: 80rpx;
			height: 80rpx;
			margin-top: 10rpx;
		}
		
		.content_info{
			
		}
		
		.content_music{
			display: flex;
			flex-direction: column;
			justify-content: center;
			margin-left: 50rpx;
		}
		.into{
			width: 70%;
			float: right;
		}
		/* 叔叔头条(音频) 结束 */
		
		
		/*  叔叔快手(短视频) 开始 */
		.video_warp{
			
			margin-top: 50rpx;
		}
		.video_title{
			
			margin-left: 40rpx;
			border-left: 10rpx solid #ff8020;
			display: flex;
			justify-content: space-between;
			
		}
		.video_item{
			display: flex;
			width: 33%;
		}
		.video_content{
			margin-left: 30rpx;
			margin-top: 60rpx;
			border: 5rpx solid #F1F1F1;
			box-shadow: 2px 2px 2px 2px #F1F1F1;
			height: 350rpx;
		}
		
		.video{
			
			width: 200rpx;
			height: 225rpx;
			
		}
		/* 叔叔快手(短视频) 结束 */
		
		
		/* 热门好课(可试听) 开始 */
		.course_warp{
			margin-top: 50rpx;
		}
		.course_title{
			
			
			
		}
		.title_content{
			display: flex;
			font-size: 30rpx;
			text-align: center;
			justify-content: center;
			
		}
		.line{
			margin-left: 250rpx;
			border-bottom: 8rpx solid #FF8020;
			width: 250rpx;
			margin-top: 5rpx;
		}
		
		.course_content{
			margin-top: 50rpx;
			display: flex;
			flex-wrap: wrap;
		}
		.course_item{
			
			border: 10rpx solid #FFFFFF;
			
		}
		.course_video{
			width: 350rpx;
			height: 250rpx;
		}
		.more{
			color: #8F8F94;
			font-size: 30rpx;
			margin-top: 25rpx;
			display: flex;
			margin-left: 300rpx;

		}
		/* 热门好课(可试听) 结束 */
		
		/* 英文/语文/通识/音乐/作品 开始 */
		.down{
			margin-top: 10rpx;
			background-color: #FFFFFF;
			height: 20rpx;
			width: 100%;
		}
	
		
		/* 英文/语文/通识/音乐/作品 结束 */
	</style>