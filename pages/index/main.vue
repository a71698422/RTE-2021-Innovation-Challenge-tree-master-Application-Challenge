<template>
	<view class="page">
		<view class="flex align-center mt-32">
			<uni-list class="text-left" :border="false">
				<uni-list-item showArrow="true" title="电话客服" showExtraIcon="true">
					<template slot="header">
						<image class="slot-image" src="@/static/iconfont/icon_service.png"></image>
					</template>
				</uni-list-item>
			</uni-list>
		</view>
	</view>
</template>

<script>
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue';
	export default {
		components: {
			uniListItem
		},
		data() {
			return {
				titleString: "医生列表"
			}
		},
		onLoad(e) {


		},
		methods: {
			
		},
	}
</script>

<style>
	page {
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		background-color: #F2F2F2;
		min-height: 100%;
		height: auto;
	}

	.width-20 {
		width: 20%;
		max-width: 28%;
	}

	.example-body {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: column;
		flex-wrap: wrap;
		justify-content: center;
		border-radius: 8rpx;
		margin: 20rpx;
		font-size: 14px;
		background-color: #ffffff;
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

	.slot-circle-image {
		/* #ifndef APP-NVUE */
		display: block;
		background-color: #FFEFE7;
		padding: 16rpx;
		border-radius: 32rpx;
		/* #endif */
		margin: 4rpx 32rpx 4rpx 4rpx;
		width: 64rpx;
		height: 64rpx;
	}

	.border-vertical {
		border-top-width: 1rpx;
		border-top-style: solid;
		border-top-color: #FFFFFF;
		border-bottom-style: solid;
		border-bottom-color: #FFFFFF;
	}
</style>
