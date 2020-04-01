<template>
	<view class="content">
		<view class="inputs">
			<view class="uni-form-item uni-column">
				<input class="uni-input" focus v-model="bank" placeholder="输入你的结算卡号" />
			</view>
			<button class="btn" type="primary" @click="bankClick()">确认绑定</button>
		</view>
	</view>
</template>

<script>
	export default {
		
		data() {
			return {
				bank:''
			}
		},
		onLoad:function(options) {
			
		},
		methods: {
			//提现点击事件
			bankClick: function(){
				uni.request({
					url: 'http://localhost:8081/updatebank?u_id='+localStorage.getItem("id")+"&bank="+this.bank,
					method: 'POST',
					success: res => {
						uni.showToast({
							title: '绑定成功',
							icon: 'none',
							duration: 1500
						});
					}
				});
				uni.request({
					url: 'http://localhost:8081/getUser?u_phone='+localStorage.getItem("phone"),
					method: 'POST',
					success: res => {
						localStorage.setItem("bank",res.data.ubank)
					}
				});
				uni.reLaunch({
					url: '/pages/my/my'
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
