<template>
	<view class="register">

		<view class="content">
			<!-- 头部logo -->
			<view class="header">
				<image src="@/static/icons/icon_showlog.png"></image>
				<text class="header_line"></text>
				<text class="header_text">医疗 Demo</text>
			</view>
			<!-- 主体表单 -->
			<view class="register_main">
				<text class="header_tips">用户名/room</text>
				<view :class="'login_user ' + nameFocus">
					<input type="text" v-model="username" placeholder="用户名" placeholder-style="color:rgb(173,185,193)"
						@focus="onFocusName" @blur="onBlurName">
				</view>
				<text class="header_tips">密码/Key</text>
				<view :class="'login_pwd ' + psdFocus">
					<input type="text" v-model="userpass" placeholder="密码" placeholder-style="color:rgb(173,185,193)" 
					 @focus="onFocusPsd" @blur="onBlurPsd">
				</view>
				<text class="header_tips">确认密码/Key</text>
				<view :class="'login_pwd ' + psdFocus">
					<input type="text" v-model="userpass" placeholder="密码" placeholder-style="color:rgb(173,185,193)" 
					 @focus="onFocusPsd" @blur="onBlurPsd">
				</view>
			</view>
			
			<view class="login_btn">
				<button hover-class="btn_hover" @tap="startReg">注册</button>
			</view>
			
			<!-- 返回登录 -->
			<view class="footer">
				<navigator url="login" open-type="navigate">返回登录</navigator>
			</view>
			
			<!-- 底部信息 -->
			<view class="register_bottom">
				<text>本产品由环信提供  当前版本：1.4.1</text>
			</view>
		</view>
	</view>
</template>

<script>
	let _this;

	export default {
		data() {
			return {
				//logo图片 base64
				logoImage: '/static/icons/icon_showlog.png',
				phoneData: '', //用户/电话
				passData: '', //密码
				isRotate: false, //是否加载旋转
				isFocus: true, // 是否聚焦
				username: "",
				userpass: "",
				psdFocus: "",
				nameFocus: "",
				showAgree: true, //协议是否选择
			}
		},
		components: {
			
		},
		mounted() {
			_this = this;
		},
		methods: {
			onFocusPsd: function() {
				this.setData({
					psdFocus: 'psdFocus'
				});
			},
			onBlurPsd: function() {
				this.setData({
					psdFocus: ''
				});
			},
			onFocusName: function() {
				this.setData({
					nameFocus: 'nameFocus'
				});
			},
			onBlurName: function() {
				this.setData({
					nameFocus: ''
				});
			},
			isShowAgree() {
				//是否选择协议
				_this.showAgree = !_this.showAgree;
			},
			getVerCode() {
				//获取验证码
				if (_this.phoneData.length != 11) {
					uni.showToast({
						icon: 'none',
						position: 'bottom',
						title: '手机号不正确'
					});
					return false;
				}
				console.log("获取验证码")
				this.$refs.runCode.$emit('runCode'); //触发倒计时（一般用于请求成功验证码后调用）
				uni.showToast({
					icon: 'none',
					position: 'bottom',
					title: '模拟倒计时触发'
				});

				setTimeout(function() {
					_this.$refs.runCode.$emit('runCode', 0); //假装模拟下需要 终止倒计时
					uni.showToast({
						icon: 'none',
						position: 'bottom',
						title: '模拟倒计时终止'
					});
				}, 3000)
			},
			startReg() {
				//注册
				if (this.isRotate) {
					//判断是否加载中，避免重复点击请求
					return false;
				}
				if (this.showAgree == false) {
					uni.showToast({
						icon: 'none',
						position: 'bottom',
						title: '请先同意《协议》'
					});
					return false;
				}
				if (this.phoneData.length != 11) {
					uni.showToast({
						icon: 'none',
						position: 'bottom',
						title: '手机号不正确'
					});
					return false;
				}
				if (this.passData.length < 6) {
					uni.showToast({
						icon: 'none',
						position: 'bottom',
						title: '密码不正确'
					});
					return false;
				}
				if (this.verCode.length != 4) {
					uni.showToast({
						icon: 'none',
						position: 'bottom',
						title: '验证码不正确'
					});
					return false;
				}
				console.log("注册成功")
				_this.isRotate = true
				setTimeout(function() {
					_this.isRotate = false
				}, 3000)
			}
		}
	}
</script>

<style>
	@import url("./css/main.css");
</style>
