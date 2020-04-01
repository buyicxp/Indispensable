<template>
	<view class="content">
		<view class="text-btn" @click="creditClick()">
			<image class="img" src="../../static/card.png"></image>
			<text class="title">免费申办信用卡</text>
		</view>
		<view class="text-btn" @click="posClick()">
			<image class="img" src="../../static/pos.png"></image>
			<text class="title">免费领取POS机</text>
		</view>
		<view class="text-btn" @click="integralClick()">
			<image class="img" src="../../static/integral.png"></image>
			<text class="title">信用卡积分兑换</text>
		</view>
		<view class="text-btn" @click="diagnoseClick()">
			<image class="img" src="../../static/doctor.png"></image>
			<text class="title">信用卡提额诊断</text>
		</view>
		<view class="text-btn" @click="loansClick()">
			<image class="img" src="../../static/loans.png"></image>
			<text class="title">缺钱贷款多途径</text>
		</view>
		<view class="text-btn" @click="hiringClick()">
			<image class="img" src="../../static/invite.png"></image>
			<text class="title">招聘求职双通道</text>
		</view>
		<view class="text-btn" @click="accClick()">
			<image class="img" src="../../static/accountant.png"></image>
			<text class="title">免费会记咨询</text>
		</view>
		<view class="text-btn" @click="lawClick()">
			<image class="img" src="../../static/law.png"></image>
			<text class="title">免费法律咨询</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {
		
		},
		methods: {
			//信用卡框点击事件
			creditClick: function(){
				uni.navigateTo({
					url: '/pages/frommenu/frommenu'
				});
			},
			//POS机框点击事件
			posClick: function(){
				uni.navigateTo({
					url: '/pages/applypos/applypos'
				});
			},
			//积分信用卡兑换点击事件
			integralClick: function(){
				uni.navigateTo({
					url: '/pages/applypos/applyintegral'
				});
			},
			//信用卡提额诊断框点击事件
			diagnoseClick: function(){
				uni.navigateTo({
					url: '/pages/applypos/applydiagnose'
				});
			},
			//缺钱贷款多途径框点击事件
			loansClick: function(){
				uni.navigateTo({
					url: '/pages/applypos/applyloans'
				});
			},
			//招聘求职双通道框点击事件
			hiringClick: function(){
				uni.navigateTo({
					url: '/pages/applypos/applyhiring'
				});
			},
			//免费会记咨询框点击事件
			accClick: function(){
				uni.navigateTo({
					url: '/pages/applypos/accapply'
				});
			},
			//免费法律咨询框点击事件
			lawClick: function(){
				uni.navigateTo({
					url: '/pages/applypos/applylaw'
				});
			}
		}
	}
</script>

<style>
	.content {
		flex-direction: column;
		align-items: center;
		justify-content: center;
		background-color: #f4f4f4;
		height: 1110rpx;
	}
	//小框样式
	.text-btn {
		margin-left: 15rpx;
		margin-top: 15rpx;
		margin-right: 5px;
		height: 200rpx;
		width: 350rpx;
		background-color: #ffffff;
		display: inline-block;
		text-align: center;
		border-radius: 20rpx;
	}
	.img{
		height: 70rpx;
		width: 70rpx;
		padding-top: 40rpx;
	}
	.title {
		font-size: 24rpx;
		color: #000000;
		display: block;
	}
</style>
