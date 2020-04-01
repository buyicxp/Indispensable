<template>
	<view class="content">
		<view class="one">
			<view class="text-card">
				
				<view class="card-top">
					<image class="img" src="../../static/safety.png"></image><text>本月收益(金额)</text>
					<view  class="money">￥1200.00</view>
				</view>
			
				<view class="card-centre">
					<view class="direct">
						<view class="littletext">直营交易<view class="moneylittle">￥400.00</view></view>
					</view>
					<view class="direct">
						<view class="littletext">下级交易<view class="moneylittle">￥400.00</view></view>
					</view>
				</view>
				
				<view class="card-below">
					查看更多
				</view>
			</view>
			
			<view class="text-card">
				
				<view class="card-top">
					<image class="img" src="../../static/warning.png"></image><text>本月新增(客户)</text>
					<view  class="money">78</view>
				</view>
			
				<view class="card-centre">
					<view class="direct">
						<view class="littletext">直营客户<view class="moneylittle">26</view></view>
					</view>
					<view class="direct">
						<view class="littletext">下级客户<view class="moneylittle">48</view></view>
					</view>
				</view>
				
				<view class="card-below">
					查看更多
				</view>
			</view>
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
		align:center;
		color: #9e9e9e;
		size: 24rpx;
	}
	.one{
		align:center;
		padding-top: 30rpx;
	}
	.text-card{
		margin:10rpx auto;
		background-color: #FFFFFF;
		border-radius: 10rpx;
		height: 330rpx;
		width: 720rpx;
		box-shadow:3px 3px 10px #737373;
	}
	.card-top{
		padding: 10rpx 10rpx 0rpx 10rpx;
		border-bottom:1px solid #eaeaea;
		height: 90rpx;
		line-height: 45px;
	}
	.card-centre{
		border-bottom:1px solid #adadad;
		padding: 20rpx 10rpx 0rpx 10rpx;
	}
	.card-below{
		height: 60rpx;
		line-height: 30px;
		font-size: 28rpx;
		text-align:center;
	}
	.img{
		height: 29rpx;
		width: 31rpx;
		margin-left: 10rpx;
	}
	.money{
		font-size: 36rpx;
		font-weight: bold;
		float: right;
		color: #000000;
	}
	.direct{
		height: 70rpx;
	}
	.moneylittle{
		float: right;
	}
</style>
