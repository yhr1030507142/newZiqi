<template>
	<view class="box">
		<text>请选择相册或选择跳过</text>
		<view>跳过</view>
		<view>
			<ul class="ul">
				<li class="li" v-for="(v,i) in arr" :key="i" @tap="goStory(v.id)">
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
					{id:1,name:"回忆",img:"../../static/yhr.jpg"},
					{id:2,name:"回忆",img:"../../static/yhr.jpg"},
					{id:3,name:"回忆",img:"../../static/yhr.jpg"},
					{id:4,name:"回忆",img:"../../static/yhr.jpg"},
				],
			}
		},
		
		methods: {
			goToPhoto:function(){
				uni.navigateTo({
					url:"../pages/photo/photo",
				})
			},
			goStory:function(id){
				uni.navigateTo({
					url:"../../pages/story/story",
				})
			},
			shangchuan:function(){
				var _self =this
				uni.chooseImage({
					count: 6, //默认9
					sizeType: 'compressed', //可以指定是原图还是压缩图，默认二者都有
					// sourceType: ['album'], //从相册选择
					success: function (res) {
					console.log(JSON.stringify(res.tempFilePaths))
					_self.arr.push({id:5,name:"新增",img:res.tempFilePaths})
				},
				})
				},
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
		margin-top: 150upx;
		flex-wrap: wrap;
	}
	.li{
		width: 48%;
		height: 250upx;
		display: flex;
		flex-direction: column;
		margin-bottom: 150upx;
		/* border: 1px solid #000; */	
	}
	.img{
		width: 100%;
		height: 100%;
	}
	.img-pic{
		width: 100%;
		height: 100%;
	}
	.text{
		height: 70upx;
		line-height: 70upx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		font-size: 36upx;
	}
</style>
