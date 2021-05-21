<template>
	<view>
		<view class="flex align-center bg-white" @click="openMineData()">
			<image src="@/static/icons/icon_gongyingshang.png" style="width: 128rpx;height: 128rpx;"
				class="rounded16 m-24"></image>
			<view class="flex flex-column flex-1 px-2 align-start">
				<text class="font-md font-weight-bold text-dark">戴春花</text>
				<text class="font-28 text-main border-main">体验版VIP</text>
				<text class="font-24 text-main">有效期至2021-05-21</text>
			</view>
		</view>

		<view class="flex align-center mt-32">
			<uni-list class="text-left" :border="false">
				<uni-list-item showArrow="true" title="设置" showExtraIcon="true" to="../wallet-main/wallet-main">
					<template slot="header">
						<image class="slot-image" src="@/static/iconfont/icon_setting.png"></image>
					</template>
				</uni-list-item>
			</uni-list>
		</view>
		
		<view class="flex align-center mt-32">
			<uni-list class="text-left" :border="false">
				<uni-list-item showArrow="true" title="电话客服" showExtraIcon="true">
					<template slot="header">
						<image class="slot-image" src="@/static/iconfont/icon_service.png"></image>
					</template>
				</uni-list-item>
				<uni-list-item showArrow="true" title="帮助中心" showExtraIcon="true">
					<template slot="header">
						<image class="slot-image" src="@/static/iconfont/icon_helpless.png"></image>
					</template>
				</uni-list-item>
				<uni-list-item showArrow="true" title="更新公告" showExtraIcon="true">
					<template slot="header">
						<image class="slot-image" src="@/static/iconfont/icon_announcement.png"></image>
					</template>
				</uni-list-item>
			</uni-list>
		</view>
		
		<view class="flex align-center mt-32">
			<uni-list class="text-left" :border="false">
				<uni-list-item showArrow="true" title="关于我们" showExtraIcon="true">
					<template slot="header">
						<image class="slot-image" src="@/static/iconfont/icon_aboutus.png"></image>
					</template>
				</uni-list-item>
			</uni-list>
		</view>
	</view>
</template>

<script>
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue';
	import store from '@/store/index.js';
	export default {
		components: {
			uniListItem
		},
		data() {
			return {

			}
		},
		onReady() {

		},
		onShow: function() {
			if (!store.state.hasLogin) {
				uni.showToast({
					title: '请先登录',
					icon: 'none'
				});
				// return uni.navigateTo({
				// 	url: '../login/login'
				// });
			}
		},
		methods: {
			// 点击右上角设置
			openMineSetting() {
				uni.navigateTo({
					url: '../usersetings/usersetings'
				});
			},
			openMineData() {
				uni.navigateTo({
					url: '../personal-data/personal-data'
				});
			}
		}
	}
</script>

<style>
	.border-main {
		padding:0rpx 16rpx;
		border-radius: 16rpx;
		border-color: #FF9051;
		border-width: 2rpx;
		border-style: solid;
	}

	.slot-image {
		/* #ifndef APP-NVUE */
		display: block;
		/* #endif */
		margin-right: 32rpx;
		margin-top: 8rpx;
		width: 40rpx;
		height: 40rpx;
	}
</style>
