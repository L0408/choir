<template>
	<view>
	        
	        <button class="" @click="appLogin">APP微信授权登录</button>
	       
	    </view>
</template>

<script>
 export default {
        data() {
            return {

            }
        },
        onLoad(options) {
            console.log(options);
        },
        methods: {
            appLogin: function() {
                uni.getProvider({
                    service: 'oauth',
                    success: function(res) {
                        console.log(res.provider);
                        //支持微信、qq和微博等
                        if (~res.provider.indexOf('weixin')) {
                            uni.login({
                                provider: 'weixin',
                                success: function(loginRes) {
                                    console.log('-------获取openid(unionid)-----');
                                    console.log(JSON.stringify(loginRes));
                                    // 获取用户信息
                                    uni.getUserInfo({
                                        provider: 'weixin',
                                        success: function(infoRes) {
                                            console.log('-------获取微信用户所有-----');
                                            console.log(JSON.stringify(infoRes.userInfo));
                                        }
                                    });
                                }
                            });
                        }
                    }
                });
            },
        }
    }
	
</script>

<style>
</style>
