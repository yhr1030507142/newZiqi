<template>
	<view class="box">
		<text>请选择家人</text>
		<view>
			
			<ul class="ul">
				<li class="li" v-for="(v,i) in arr" :key="i" @tap="goToMy(v.id)">
					<view class="img">
						<image :src="v.img" mode="" class="img-pic"></image>
					</view>
					<view class="text">
						<text>{{v.name}}</text>
					</view>
				</li>
				
				
			</ul>
		</view>
		
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				arr:[
					{id:1,name:"妈妈",img:"../../../static/yhr.jpg"},
					{id:2,name:"爸爸",img:"../../../static/yhr.jpg"},
					{id:3,name:"爷爷",img:"../../../static/yhr.jpg"},
					{id:4,name:"奶奶",img:"../../../static/yhr.jpg"},
				],
			}
		},
		methods: {
			goToPhoto:function(){
				uni.navigateTo({
					url:"../pages/photo/photo",
				})
			},
			goToMy:function(id){
				uni.navigateTo({
					url:"../../../pages/photoList/photoList"
				})
			},
			shangchuan:function(){
				uni.request({
					url:"",
					success:function(res){
						
					}
				})
			}
		}
	}
</script>

<style>
	.box{
		width: 85%;
		margin: 0 auto;
		/* border: 1px solid black; */
	}
	.all{
		display: flex;
		flex-direction: row;
		justify-content: center;
		margin-top: 50upx;
	}
	.ul{
		padding: 0;
		margin: 0;
		list-style: none;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		margin-top: 50upx;
		flex-wrap: wrap;
	}
	.li{
		width: 48%;
		height: 250upx;
		display: flex;
		flex-direction: column;
		margin-top: 130upx;
		/* border: 1px solid #000; */
		
		
	}
	.img{
		width: 100%;
		height: 250upx;
	}
	.img-pic{
		width: 100%;
		height: 100%;
	}
	.text{
		display: flex;
		flex-direction: row;
		justify-content: center;
		font-size: 36upx;
	}
</style>
