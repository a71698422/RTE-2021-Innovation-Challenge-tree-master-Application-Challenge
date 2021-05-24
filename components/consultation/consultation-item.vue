<template>
	<view class="consultation-item" @click="open">
		<image :src="item.docavatar" class="list-item-avatar"></image>
		<view class="list-item-right">
			<view class="hei-48 mt-16"><text class="font-34">{{item.docname}}</text>
				<text class="font-24 ml-20">{{item.docpartment}}</text>
				<text class="list-item-tag">{{item.consultag}}</text>
			</view>
			<view class="mt-20"><text class="font-32">{{item.consultitle}}</text></view>
			<view class="list-item-docexpert mt-4">
				{{item.consultime}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {

		},
		props: {
			item: Object,
			index: Number
		},
		methods: {
			open() {

			}
		},
	}
</script>

<style>
	.consultation-item {
		display: flex;
		flex-direction: row;
		margin: 36rpx;
		padding: 4rpx;
		background-color: #FFFFFF;
		border-radius: 8rpx;
		font-family: Helvetica Neue, Helvetica, sans-serif;
	}

	.list-item-avatar {
		margin: 16rpx;
		width: 84rpx;
		height: 84rpx;
		border-radius: 42rpx;
	}

	.list-item-right {
		margin: 8rpx;
		flex-direction: column;
		text-align: left;
	}

	.list-item-tag {
		border-radius: 8rpx;
		padding: 4rpx 16rpx;
		color: #FFFFFF;
		margin-left: 20rpx;
		font-size: 20rpx;
		background-color: #25B4A5;
	}

	.list-item-docexpert {
		color: #9FA4AE;
		font-size: 24rpx;
	}
</style>
