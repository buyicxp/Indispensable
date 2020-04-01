<template>
	<view class="content">
		<view class="dimension-card">
			<view class="portrait-top">
				<view class="portrait">
					<image class="portraitimg" src="../../static/buyi.png"></image>
					<view class="designation">
						{{nickName}}
					</view>
					<view class="site">
						湖南 长沙
					</view>
				</view>
				<view>
					<view @click="withdrawClick()" class="choice">
						 <image class="img" src="../../static/withdraw.png"></image> 
						提现
					</view>
				</view>
				<view>
					<view>
						<view class="choice" @click="cardClick()">
							<image class="img" src="../../static/binding.png"></image> 
							绑定结算卡
						</view>
					</view>
				</view>	
				<view>
					<view @click="towClick()" class="choice">
						<image class="img" src="../../static/navigation/qrclick.png"></image>
						推广二维码
					</view>
				</view>	
				<view>
					<view class="choice">
						<image class="img" src="../../static/password.png"></image>
						修改密码
					</view>
				</view>
				<view>
					<view class="choice">
						<image class="img" src="../../static/service.png"></image>
						客服
					</view>
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				nickName: '',
				phone:''
				//u_recommend: {u_recommend}
			}
		},
		
		onLoad:function(options) {
			this.nickName=localStorage.getItem("name");
			this.phone = localStorage.getItem("phone");
			let that = this;
			// uni.login({
			// 	provider: 'weixin',
			// 	success: function(loginRes) {
			// 		// 获取用户信息				
			// 		uni.getUserInfo({
			// 			provider: 'weixin',
			// 			success: function(infoRes) {
			// 				that.account = infoRes.userInfo;
			// 				//console.log(that.account);
			// 			}
			// 		});
			// 	}
			// })
			uni.request({
				url: 'http://localhost:8081/getUser?u_phone='+localStorage.getItem("phone"),
				method: 'POST',
				success: res => {
				
					localStorage.setItem("id",res.data.uId)
				}
			});
			//判断用户是否存在
			uni.request({
				url: 'http://localhost:8081/userRepetition?u_phone='+localStorage.getItem("phone"),
				method: 'POST',
				success: res => {
					if(res.data==0){
						 //成为新用户 
						uni.request({
							url: 'http://localhost:8081/userInsert?u_name='+localStorage.getItem("name")+'&u_phone='+localStorage.getItem("phone")+'&urecommend='+localStorage.getItem("urecommend"),
							method: 'POST',
							success: res => {
								console.log(res.data);
							}
						});
					}
					
				}
			});
			
		},
		methods: {
			//提现点击事件
			withdrawClick: function(){
				uni.navigateTo({
					url: '/pages/withdraw/withdraw'
				});
			},
			//推广二维码点击事件
			towClick: function(){
				uni.navigateTo({
					url: '/pages/dimension/dimension'
				});
			},
			//绑定结算卡点击事件
			cardClick: function(){
				uni.navigateTo({
					url: '/pages/bank/bank'
				});
			}
		}
	}
</script>

<style>
	.img{
		height: 50rpx;
		width: 50rpx;
		vertical-align:middle;
		margin-right: 10rpx;
	}
	.content{
		height:1110rpx;
		background-color: #f4f4f4;
		
	}
	.dimension-card{
		background-color: #FFFFFF;
		height: 560rpx;
		width: 750rpx;
		margin:0rpx auto;
	}
	.portrait{
		border-bottom:10px solid #f4f4f4;
		height: 160rpx;
	}
	.portraitimg{
		margin: 30rpx;
		height: 100rpx;
		width: 100rpx;
		float: left;
		border-radius: 100rpx;
	}
	.designation{
		padding-top: 30rpx;
		padding-bottom: 10rpx;
		font-weight: bold;
		font-size: 36rpx;
	}
	.yard{
		height: 700rpx;
		width: 700rpx;
	}
	.choice{
		display:inline-block;
		height:100%;
		vertical-align:middle;
		width: 100%;
		border-bottom:3px solid #f4f4f4;
		font-size: 26rpx;
		padding-left: 30rpx;
		line-height: 70rpx;
	}
</style>
