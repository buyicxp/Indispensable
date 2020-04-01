<template class="setting">
	<view class="content">
		<view class="dimension-card">
			<view class="portrait-top">
				<view>
					<image class="yard" :src="imgurl"></image>
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgurl:'',
				userList:[]
				//u_recommend: {u_recommend}
			}
		},
		onLoad:function(options) {
			this.imgurl="../../static/generalize/"+localStorage.getItem("id")+".png"
			uni.request({
				url: 'http://localhost:8081/generalize?u_id='+localStorage.getItem("id"),
				method: 'POST',
				success: res => {
				}
			});	
			
		
		},
		methods: {
			
		}
	
	}
	
</script>

<style>
	.content{
		height:1110rpx;
		background-color: #f4f4f4;
		padding-top: 150rpx;
	}
	.dimension-card{
		background-color: #FFFFFF;
		height: 700rpx;
		width: 700rpx;
		margin:0rpx auto;
		border-radius: 10rpx;
		
	}
	.portraitimg{
		margin: 30rpx;
		height: 100rpx;
		width: 100rpx;
		float: left;
	}
	.designation{
		padding-top: 30rpx;
		padding-bottom: 10rpx;
	}
	.yard{
		height: 700rpx;
		width: 700rpx;
	}
</style>
