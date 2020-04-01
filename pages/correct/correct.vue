<template>
	<view class="backdrop">
			<view class="moneyimg">
				<image class="img" src="../../static/correct.png"></image>
			</view>
			<view class="money">申请成功</view>
			<view class="mymoney">客服将稍后联系</view>
			<button class="btn" type="primary" @click="confirm">确定</button>
	</view>
</template>

<script>
	export default {
		
		data() {
			return {
				minusBrokerage:''
			}
		},
		onLoad:function(options) {
			
		},
		methods: {
			//提现点击事件
			confirm: function(){
				uni.reLaunch({
					url: '/pages/index/index'
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
		font-size: 60rpx;
	}
	.withdraw{
		
	}
	.img{
		width: 200rpx;
		height: 200rpx;
	}
	.btn{
		width: 280rpx;
		height: 93rpx;
	}
</style>
