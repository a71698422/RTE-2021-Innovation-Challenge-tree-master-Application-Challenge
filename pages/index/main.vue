<template>
	<view class="page">
		<view class="uni-list">
			<block v-for="(value, index) in lawyerlist" :key="index">
				<main-item :item="value" :index="index"></main-item>
			</block>
		</view>
		<uni-load-more :status="status" :icon-size="16" :content-text="contentText" />
	</view>
</template>

<script>
	// 测试数据
	const lawyerdemo = [{
			docname: "王娟",
			docavatar: "/static/icons/icon-avatarimg.png",
			doclevel: "主治医师",
			dochospital: "上海市第一人民医院",
			docpartment: "耳鼻喉科",
			doctag: "三甲",
			docexpert: "擅长：过敏性鼻炎；慢性炎鼻窦炎；鼻息肉；鼻息肉；",
			docconsultation: 945,
			docresponse:45,
			docfootprice: 35
		},
		{
			docname: "王娟",
			docavatar: "/static/icons/icon-doctarimg.png",
			doclevel: "主治医师",
			dochospital: "上海市第一人民医院",
			docpartment: "耳鼻喉科",
			doctag: "三甲",
			docexpert: "擅长：过敏性鼻炎；慢性炎鼻窦炎；鼻息肉；鼻息肉；",
			docconsultation: 945,
			docresponse:45,
			docfootprice: 35
		},
		{
			docname: "王娟",
			docavatar: "/static/icons/icon_marshalling.png",
			doclevel: "主治医师",
			dochospital: "上海市第一人民医院",
			docpartment: "耳鼻喉科",
			doctag: "三甲",
			docexpert: "擅长：过敏性鼻炎；慢性炎鼻窦炎；鼻息肉；鼻息肉；",
			docconsultation: 945,
			docresponse:45,
			docfootprice: 35
		}
	];
	import mainItem from '@/components/news/main-item.vue';
	export default {
		components: {
			mainItem
		},
		data() {
			return {
				titleString: "医生列表",
				lawyerlist: [],
				status: 'more',
				contentText: {
					contentdown: '上拉加载更多',
					contentrefresh: '加载中',
					contentnomore: '没有更多'
				}
			}
		},
		onLoad(e) {
			this.lawyerlist = [...lawyerdemo,...lawyerdemo];
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
		background-color: #F7F8FA;
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
		/* #endif */
		background-color: #FFEFE7;
		padding: 16rpx;
		border-radius: 32rpx;
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
