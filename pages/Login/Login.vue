<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<u-form>
			<u-form-item label="账号:">
				<u-input v-model="loginData.username"></u-input>
			</u-form-item>
			<u-form-item label="密码:">
				<u-input v-model="loginData.password"></u-input>
			</u-form-item>
		</u-form>
		<view class="btn">
			<u-button @click="jumpUrl('index')">登录</u-button>
			<u-button @click="jumpUrl('register')">注册</u-button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				loginData: {
					username: '',
					password: '',
				}
			}
		},
		methods: {
			jumpUrl(url) {
				switch (url) {
					case 'index':
						uni.redirectTo({
							url: '/pages/index/index',
						})
						break
					case 'register':
						uni.redirectTo({
							url: '/pages/Register/Register',
						})
						break
				}
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.btn {
		display: flex;
		align-items: center;
		justify-content: center;
		column-gap: 24px;
	}
</style>