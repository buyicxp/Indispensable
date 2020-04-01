<template>
	<view class="backdrop">
			<view class="moneyimg">
				<image class="img" src="../../static/moneyimg.png"></image>
			</view>
			<view class="mymoney">我的佣金</view>
			<view class="money">1200.00</view>
			<button class="btn" type="primary" @click="withdrawClick()">提现</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad:function(options) {
			
		},
		methods: {
			//提现点击事件
			withdrawClick: function(){
				uni.reLaunch({
					url: '/pages/withdraw/inputmoney'
				});
			},
		}
	
	}
</script>

<style>
	.backdrop{
		height: 1010rpx;
		padding-top: 200rpx;
		text-align:center;
		background-color: #f4f4f4;
	}
	.moneyimg{
		padding-bottom: 50rpx;
	}
	.mymoney{
		padding-bottom: 10rpx;
		font-size: 54rpx;
	}
	.money{
		padding-bottom: 30rpx;
		font-size: 78rpx;
	}
	
	.img{
		width: 100rpx;
		height: 100rpx;
	}
	.btn{
		width: 280rpx;
		height: 93rpx;
	}
</style>
