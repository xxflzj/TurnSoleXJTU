<template>
	<view>
		<view class="box">
			<image class="logoImg" :src="about.logo"></image>
			<text class="tip title">iCaring欢迎您</text>
		</view>
		<uni-card class="card">
			<text>&nbsp;&nbsp;&nbsp;&nbsp;iCaring向日葵是一款XXX软件，提供在线志愿发布与完成的应用平台。</text>
		</uni-card>
		<button class="btn-welcome" style="color: #ffffff; background-color: #4c8dae;" type="primary" @click="this.start()">开始使用</button>
		<view class="copyright">
			<text class="hint">{{about.company}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		computed: {
			uniStarterConfig() {
				return getApp().globalData.config
			},

		},
		data() {
			return {
				about: {},
				canEdit : true,
				uid:"",
				
			}
		},
		created() {
			this.about = this.uniStarterConfig.about
		},
		methods: {
			aboutus() {
				uni.navigateTo({
					url:'/pages/index/iCaring'
				})
			},
			start() {
				// uni.navigateTo({
				// 	url: '/pages/ucenter/ucenter'
				// })
				uni.switchTab({
				          url: '/pages/ucenter/ucenter'
				})
			}
		}
	}
</script>

<style>
	/* #ifndef APP-NVUE */
	view {
		display: flex;
		box-sizing: border-box;
		flex-direction: column;
	}
	
	/* #endif */
	.bind {
		width: 100%;
		flex-direction: column;
	}

	.box {
		width: 100%;
		margin-top: 100px;
		margin-bottom: 10px;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.logoImg {
		margin-bottom: 10upx;
		width: 320upx;
		height: 320upx;
		border-radius: 15px;
	}

	.tip {
		font-size: 24rpx;
		margin: 10px;
		text-align: center;
	}

	.title {
		margin-top: 10px;
		font-size: 42rpx;
		font-weight: 500;
	}

	.btn-welcome {
		width: 40%;
		margin: 20px auto;
		align-items: center;
		
	}
	.copyright {
		width: 100%;
		font-size: 32rpx;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		bottom: 20px;
		left: 0;
		position: fixed;
	}

	.hint {
		color: #999999;
		font-size: 26rpx;
	}

	.icon {
		width: 100rpx;
	}
	
	.description-text {
		font-size: 32rpx;
	}
	
	.card {
		margin: 0px;
		padding: 0px;
	}
</style>
