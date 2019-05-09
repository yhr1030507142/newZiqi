<template>
	<view class="box">
		  <textarea placeholder-style="color:#999999" placeholder="回忆起家人的故事了吗？快来写一写"/>
		  <view class="name">
			回忆对象:哥哥
		  </view>
		  <button type="primary" style="width:100%" @tap="fabu()">发布</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			fabu:function(){
				uni.showToast({
					title: '发布成功',
					duration: 2000,
					success:function (res) {
						uni.switchTab({
							url:"../../pages/tabbar/tabbar-1/tabbar-1"

						})
						
					}
					
				});
				
			}
		}
	}
</script>

<style>
	page{
		background: #FF978D;
	}
	.box{
		display: flex;
		flex-direction: column;
		align-items: center;
		height: 100%;
	}
	.name{
		width: 100%;
	}
textarea{
	margin-top: 200upx;
	width: 80%;
	height: 600upx;
	color: #ffffff;
	font-size: 36upx;
	/* border: 2upx solid #fff; */
}
</style>
