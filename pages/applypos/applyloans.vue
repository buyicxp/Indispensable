<template>
    <view class="backdrop">
        <view class="uni-common-mt">
			<view class="title">缺钱贷款多途径</view>
			<text class="basics">基本信息:</text>
            <view class="uni-form-item uni-column">
                <view class="bankName">
					<view class="nameText"> 姓名 </view>
					<input class="uni-input" v-model="u_name" focus placeholder="本人姓名" />
					</view>
				</view>
				<view class="bankName">
					<view class="nameText" > 手机号 </view>
						<input class="uni-input" v-model="u_phone" focus placeholder="本人常用的手机号码" />
				</view>
				<view class="bankName">
					<view class="nameText"> 验证码 </view>
						<input class="note-verification" focus placeholder="短信验证码" />
						<text class="verification">
							获取验证码
						</text>
				</view>
				<button class="btn" type="primary" @click="affirmClick()">确认申请</button>
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
				index: 0,
				u_phone: '',
				u_name: '',
				array: ['个人POS机', '商用POS机'],
				userList:[]
	        }
	    },
	    methods: {
			//确定申请点击事件
			affirmClick: function(){
				if (this.u_name == '') {
					uni.showToast({
						title: '请填写你的姓名',
						icon: 'none',
						duration: 1500
					});
					return false;
				}
				if (this.u_phone == '') {
					uni.showToast({
						title: '手机号不能为空',
						icon: 'none',
						duration: 1500
					});
					return false;
				}
			
				//根据电话号码查询用户信息
				uni.request({
					url: 'http://localhost:8081/getUser?u_phone='+this.u_phone,
					method: 'POST',
					success: res => {
						//console.log(res.data);
						this.userList = res.data;
						uni.request({
							url: 'http://localhost:8081/orderInsert?u_id='+this.userList.uId+"&t_id=5",
							method: 'POST',
							success: res => {
								console.log(res.data);
								this.userList = res.data;
							}
						});
					}
				});
				uni.reLaunch({
					url: '/pages/correct/correct'
				});
				
			}
	    }
	}
</script>

<style>
	.btn{
		margin-top: 50rpx;
	}
	.backdrop{
		background-color: #f4f4f4;
		height: 1150rpx;
		padding-top: 50rpx;
	}
	.uni-input{
		margin-right: 230rpx;
		float:right;
		display: inline-block;
		height: 60rpx;
	}
	.verification{
		width: 180rpx;
		float: right;
		font-size: 26rpx;
		color: #999999;
		text-align:center;
		border-left:2px solid #f4f4f4;
	}
	.note-verification{
		margin-left: 55rpx;
		display: inline-block;
		height: 60rpx;
	}
	.nameText{
		margin-left: 20rpx;
		float: left;
		display: inline-block;
	}
	.bankName{
		line-height: 60rpx;
		height: 60rpx;
		background-color: #ffffff;
		border-bottom:2px solid #f4f4f4;
	}
	.title{
		text-align:center;
		color: #007AFF;
		font-size: 56rpx;
	}
	.basics{
		margin-left: 10rpx;
		font-size: 24rpx;
		color: #999999;
	}
</style>

