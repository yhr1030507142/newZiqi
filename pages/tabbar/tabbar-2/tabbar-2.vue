<template>
	<view class="box">
		<prompt ref="prompt" @onConfirm="onConfirm" @onCancel="onCancel" title="请填写相册名称" :text="promptText"></prompt>
			<view class="all"><button @tap="prompt()">创建相册</button></view>
		<view>
			
			<ul class="ul">
				<li class="li" v-for="(v,i) in arr" :key="i" @tap="goToPhoto(v.id)">
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
	import prompt from '../../../component/prompt.vue';
	export default {
		data() {
			return {
				arr:[
					{id:1,name:"回忆",img:"../../../static/yhr.jpg"},
					{id:2,name:"回忆",img:"../../../static/yhr.jpg"},
					{id:3,name:"回忆",img:"../../../static/yhr.jpg"},
					{id:4,name:"回忆",img:"../../../static/yhr.jpg"},
				],
			}
		},
		components: {
			prompt,
		},
		methods: {
			goToPhoto:function(){
				uni.navigateTo({
					url:"../../../pages/photo/photo",
				})
			},
			goToMy:function(id){
				uni.navigateTo({
					url:"../pages/photoList/photoList?Id="+id,
				})
			},
			shangchuan:function(){
				uni.showModal({
					 title: '提示',
					content: '这是一个模态弹窗',
				success: function (res) {
					if (res.confirm) {
						console.log('用户点击确定');
					} else if (res.cancel) {
						console.log('用户点击取消');
					}
				}
				})
			},
			prompt:function(){
				this.$refs.prompt.show();
			},
			onConfirm:function(e){
				console.log(e);
				let _cost = e;
				if (_cost == '') {
				 console.log('你还未输入');
				 return;
				}
				else{
				  this.$refs.prompt.hide();
				  uni.showModal({
				  	title: '提示',
				  	content: '创建成功',
				  	showCancel: false,
				  	confirmText: "确定",
					success: function (res) {
						if (res.confirm) {
							// 重新加载本页面
							console.log('用户点击确定');
						} else if (res.cancel) {
							console.log('用户点击取消');
						}}
				  })
				 
				}
			},
			onCancel:function(){
				this.$refs.prompt.hide();
				this.$refs.prompt.cost = '';
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
