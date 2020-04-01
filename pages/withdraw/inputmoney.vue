<template>
	<view class="content">
		<view class="inputs">
			<view class="uni-form-item uni-column">
				<input class="uni-input" focus v-model="minusBrokerage" placeholder="输入提现金额" />
			</view>
			<button class="btn" type="primary" @click="withdrawClick()">确认提现</button>
		</view>
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
			withdrawClick: function(){
				uni.request({
					url: 'http://localhost:8081/deposit?u_id='+localStorage.getItem("id")+"&minusBrokerage="+this.minusBrokerage,
					method: 'POST',
					success: res => {
					}
				});
				uni.reLaunch({
					url: '/pages/correct/withdrawcorrect'
				});
			},
		}
	
	}
</script>

<style>
	.content{
		height:1110rpx;
		background-color: #f4f4f4;
	}
	.inputs{
		
		margin:10rpx auto;
		background-color: #FFFFFF;
		border-radius: 10rpx;
		height: 330rpx;
		width: 720rpx;
		box-shadow:0px 0px 10px #737373;
	}
	.uni-input{
		padding:70rpx 0rpx 60rpx 50rpx ;
		font-size: 50rpx;
		height: 50rpx;
	}
	.btn{
		width: 280rpx;
		height: 93rpx;
	}
</style>
