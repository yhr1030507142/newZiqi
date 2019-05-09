<template>
	<view class="content">
		<view class="login-bg">	
				<ul class="top_ul">
					<li class="top_li flex column">
						<view class="img-div">
							<image src="../../../static/yhr.jpg" mode="" class="img"></image>
						</view>
						<text>妈妈</text> 
					</li>
					<li class="top_li flex column">
						<view class="img-div">
							<image src="../../../static/yhr.jpg" mode="" class="img"></image>
						</view>
						<text>妈妈</text> 
					</li>
					<li class="top_li flex column">
						<view class="img-div">
							<image src="../../../static/yhr.jpg" mode="" class="img"></image>
						</view>
						<text>妈妈</text> 
					</li>
					<li class="top_li flex column">
						<view class="img-div">
							<image src="../../../static/yhr.jpg" mode="" class="img"></image>
						</view>
						<text>妈妈</text> 
					</li>
					<li class=" top_li flex column">
						<view class="img-div add">
							<i>+</i>
						</view>
						<text>添加</text> 
					</li>
					</ul>
			<view class="login-card"  v-for="(v,i) in data" :key="i" >
			<view class="list flex column">
				<view class="list_top">
						<view class="list_content flex row">
								<view class="start flex row">
									<view class="img-div1">
										<image src="../../../static/yhr.jpg" mode="" class="img img1"></image>
									</view>
									<view class="title flex column">
										<text class="title_top p_title">haha</text>
										<text class="title_bottom p">2017.2.11</text>
									</view>
								</view>	
								<view class="end">
										<text class="name p">
											<text class="p">主人公:</text>
											<text class="p blcak">bab</text>

										</text>
								</view>		
						</view>	
						
						<view class="list_middle">
							<text class="fonts">dfdsfdsfsdfdsfsdfdssfdsfsdfsdf</text>
						</view>
						<!-- <view class="list_middle_pic flex row">
							<image src="../../static/yhr.jpg" mode="" class="pic-img"></image>
						</view> -->
						</view>
						<view class="list_bottom">
							<button class="btn" @tap="goToTalk()">聊&nbsp;&nbsp;&nbsp;&nbsp;天</button>
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
				title: 'Hello',
				newList:[],
				data:[
					{name:'妈妈',content:'年后饭萨芬卡死了就疯狂拉升积分卡',toname:'爸爸'},
						{name:'妈妈',content:'年后饭萨芬卡死了就疯狂拉升积分卡',toname:'爸爸'},
							{name:'妈妈',content:'年后饭萨芬卡死了就疯狂拉升积分卡',toname:'爸爸'},
								{name:'妈妈',content:'年后饭萨芬卡死了就疯狂拉升积分卡',toname:'爸爸'},
									{name:'妈妈',content:'年后饭萨芬卡死了就疯狂拉升积分卡',toname:'爸爸'},
										{name:'妈妈',content:'年后饭萨芬卡死了就疯狂拉升积分卡',toname:'爸爸'},
											{name:'妈妈',content:'年后饭萨芬卡死了就疯狂拉升积分卡',toname:'爸爸'}
				]
			}
		},
		onLoad() {
		},
// 		onPullDownRefresh:function(){
// 			this.getNews()
// 		},
		methods: {
			go_forget(){
				uni.navigateTo({
				    url: '../../pages/forget/forget'
				})
			},
			go_register(){
				uni.navigateTo({
					url: '../../pages/register/register'
				})
			},
			getNews:function(){
				uni.showNavigationBarLoading()
				uni.request({
					url:'https://demo.hcoder.net/index.php?user=hcoder&pwd=hcoder&m=list1&page=1',
					success:function (res) {
						this.newList =JSON.parse(JSON.stringify((res.data.split('--hcSplitor--')))) 
						console.log(this.newList)
						uni.stopPullDownRefresh();
					}
				})
			}
			
		}
	}
</script>

<style>
	
	.landing{
		height: 84upx;
		line-height: 84upx;
		border-radius: 44upx;
		font-size: 32upx;
		background: linear-gradient(left,#FF978D, #FFBB69);
	}
	.login-btn{
		padding: 10upx 20upx;
		margin-top: 350upx;
	}
	.login-function{
		overflow: auto;
		padding: 20upx 20upx 30upx 20upx;
	}
	.login-forget{
		float: left;
		font-size: 26upx;
		color: #999;
	}
	.login-register{
		color: #666;
		float: right;
		font-size: 26upx;

	}
	.login-input input{
		background: #F2F5F6;
		font-size: 28upx;
		padding: 10upx 25upx;
		height: 62upx;
		line-height: 62upx;
		border-radius: 8upx;
	}
	.login-margin-b{
		margin-bottom: 25upx;
	}
	.login-input{
		padding: 10upx 20upx;
	}
	.login-head{
		font-size: 34upx;
		text-align: center;
		padding: 25upx 10upx 55upx 10upx;
	}
	.login-card{
		background: #fff;
		border-radius: 12upx;
		padding: 10upx 25upx;
		box-shadow: 0 6upx 18upx rgba(0,0,0,0.12);
		position: relative;
		/* margin-top: 100upx; */
	}
	.login-bg {
		height: 260upx;
		padding: 25upx;
		/* background: linear-gradient(#FF978D, #FFBB69); */
		background: #fc6c6c;
	}
	
	
	.list{
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		/* border: 1px solid #000; */
		width: 96%;
		border-radius: 5upx;
		margin: 0 auto;
		margin-top: 20upx;
		/* box-shadow: 0 3px 0 0 rgba(242, 156, 177, 0.3); */
		margin-top: 50upx;
		padding-bottom: 30upx;
	}
	
	.list_content{
		/* min-height: 120upx; */
		margin-top: 10upx;
		justify-content: space-between;	
		
	}
	.list_top{
		width: 96%;
		margin: 0 auto;
	}
	.img{
		/* border:1px solid #000; */
		border-radius: 50%;
		width: 90upx;
		height: 90upx;
		margin-right: 20upx;
	}
	.list_middle{
		min-height: 200upx;
		margin-top: 20upx;
	}
	.btn{
		width: 100%;
		height: 100upx;
		border-radius: 50upx;
		/* background: linear-gradient(to right,#FF978D, #FFBB69); */
		background: #fc6c6c;
		color: #fff;
		font-weight: 600;
		
	}
	.list_middle_pic{
		justify-content: flex-start;
		width: 100%;
		margin: 0 auto;
	}
	.pic-img{
		width: 100%;
		
	}
		.flex{
		display: flex;
	}
	.row{
		flex-direction: row;
	}
	.column{
		flex-direction: column;
	}
	.p_title{
		font-size: 40upx;
		font-weight: 600;
	}
	.p{
		font-size: 30upx;
		color: #ccc;
	}
	.blcak{
		color: #000;
	}
	.fonts{
		font-size: 30upx;
	}
	.top_ul{
		width: 100%;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		/* background: #fc6c6c; */
	}
	.top_li{
		width: 100upx;
		height: 160upx;
		margin-left: 40upx;
		color: #fff;
		font-size: 30upx;
		text-align: center;
		/* align-items: center; */
		/* justify-content: center; */
		
	}
	.img-div{
		width: 100upx;
		height: 100upx;
		border-radius: 50%;
	}
	.add{
		width: 90upx;
		height: 90upx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		border: 1px solid #fff;
		
	}
</style>
