<template>
	<view class="content">
		<view class="one">
			<view class="text-card" v-show="conceal">
				
				<view class="card-top">
					
				</view>
			
				<view class="card-centre">
					<view class="small"></view>
					<view class="circle"></view>
				</view>
				
				<view class="card-below">
					 <view class="trail">**** **** **** <text> {{number}}</text></view>
				</view>
			</view>
		</view>
		<view class="insert" @click="insertbankclick">
			<image class="img" src="../../static/plus.png"></image>
			绑定结算卡
		</view>
	</view>
</template>


<script>
	export default {
			data() {
				return {
					conceal:false,
					number:''
				}
			},
			onLoad() {
				if(localStorage.getItem("bank")!=null){
					this.number = localStorage.getItem("bank").substring(15)
					alert(localStorage.getItem("bank"))
					this.conceal = true;
				}else{
					this.conceal = false;
				}
			},
			methods: {
				insertbankclick: function(){
					uni.reLaunch({
						url: '/pages/withdraw/inputbank'
					});
				},
			}
		}
</script>

<style>
	.content {
		flex-direction: column;
		align-items: center;
		justify-content: center;
		background-color: #f4f4f4;
		height: 1210rpx;
		align:center;
		color: #9e9e9e;
		size: 24rpx;
	}
	.one{
		align:center;
		padding-top: 30rpx;
	}
	.text-card{
		margin:20rpx auto;
		background-color: #53a9ff;
		border-radius: 20rpx;
		height: 330rpx;
		width: 720rpx;
		box-shadow:3px 3px 10px #737373;
	}
	.card-top{
		border-bottom:20rpx solid #535353;
		height: 70rpx;
		line-height: 45px;
	}
	.card-centre{
		border-bottom:1px solid #adadad;
		padding: 30rpx;
	}
	.card-below{
		height: 60rpx;
		line-height: 30px;
		font-size: 54rpx;
		color: #FFFFFF;
		text-align:center;
		padding-top: 10rpx;
	}
	.trail{
		height: 60rpx;
		padding-right: 150rpx;
		float: right;
		font-size: 46rpx;
	}
	.small{
		display: inline-block;
		background-color: #61cdff;
		height: 100rpx;
		width: 300rpx;
	}
	.circle{
		margin-top: 10rpx;
		display: inline-block;
		float: right;
		background-color: #f4f400;
		height: 70rpx;
		width: 100rpx;
		border-radius: 30rpx;
	}
	.insert{
		margin:20rpx auto;
		background-color: #ffffff;
		border-radius: 10rpx;
		height: 100rpx;
		width: 720rpx;
		vertical-align:middle;
		line-height: 90rpx;
	}
	.img{
		margin-left: 20rpx;
		margin-right: 20rpx;
		vertical-align:middle;
		height: 40rpx;
		width: 40rpx;
	}
</style>
