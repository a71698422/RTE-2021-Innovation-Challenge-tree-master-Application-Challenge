<template>
	<view>
		<uni-nav-bar :status-bar="true" backgroundColor="#F7F8FA" left-icon="back" :border="false"
			@clickLeft="goBackAction">
			<view class="uni-navbar__header-container uni-navbar__content_view">
				<view class="uni-navbar__header-container-inner uni-navbar__column_view">
					<text class="uni-nav-bar-text">选择预约时间</text>
					<text class="uni-nav-bar-note">仅可预约未来七天 医生会在预约时间联系你</text>
				</view>
			</view>
		</uni-nav-bar>
		<view class="uni-calendar__box">
			<view class="uni-calendar__title-bg">
				<text class="uni-calendar__title-line"></text>
				<text class="uni-calendar__title-text">十月</text>
				<text class="uni-calendar__title-line"></text>
			</view>
			<view class="uni-calendar__weeks">
				<view class="uni-calendar__weeks-day">
					<text class="uni-calendar__weeks-day-text">日</text>
					<text class="uni-calendar__weeks-day-text">21</text>
				</view>
				<view class="uni-calendar__weeks-day">
					<text class="uni-calendar__weeks-day-text">一</text>
					<text class="uni-calendar__weeks-day-text">22</text>
				</view>
				<view class="uni-calendar__weeks-day">
					<text class="uni-calendar__weeks-day-text">二</text>
					<text class="uni-calendar__weeks-day-text">23</text>
				</view>
				<view class="uni-calendar__weeks-day">
					<text class="uni-calendar__weeks-day-text">三</text>
					<text class="uni-calendar__weeks-day-text">24</text>
				</view>
				<view class="uni-calendar__weeks-day">
					<text class="uni-calendar__weeks-day-text">四</text>
					<text class="uni-calendar__weeks-day-text">25</text>
				</view>
				<view class="uni-calendar__weeks-day">
					<text class="uni-calendar__weeks-day-text">五</text>
					<text class="uni-calendar__weeks-day-text">26</text>
				</view>
				<view class="uni-calendar__weeks-day">
					<text class="uni-calendar__weeks-day-text">六</text>
					<text class="uni-calendar__weeks-day-text">21</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		components: {

		},
		data() {
			return {
				show: false,
				weeks: [],
				calendar: {},
				nowDate: '',
				aniMaskShow: false
			}
		},
		onLoad() {
			// 获取日历方法实例
			// this.cale = new Calendar({
			// 	// date: new Date(),
			// 	selected: this.selected,
			// 	startDate: this.startDate,
			// 	endDate: this.endDate,
			// 	range: this.range,
			// })
			// 选中某一天
			// this.cale.setDate(this.date)
			// this.init(this.date)
			// this.setDay
		},
		methods: {
			// 返回上一步
			goBackAction() {
				uni.navigateBack({
					delta: 1
				});
			},
			/**
			 * 初始化日期显示
			 * @param {Object} date
			 */
			init(date) {
				this.cale.setDate(date)
				this.weeks = this.cale.weeks
				this.nowDate = this.calendar = this.cale.getInfo(date)
			},
		}
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

	.uni-navbar__header-container {
		flex: 1;
	}

	.uni-navbar__header-container-inner {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex: 1;
		align-items: center;
		justify-content: center;
		font-size: 14px;
	}

	.uni-navbar__content_view {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		align-items: center;
		flex-direction: row;
	}

	.uni-navbar__column_view {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		align-items: center;
		flex-direction: column;
	}

	.uni-nav-bar-text {
		font-size: 28rpx;
		line-height: 30rpx;
	}

	.uni-nav-bar-note {
		color: #BFC0C8;
		font-size: 20rpx;
	}

	.uni-calendar__weeks {
		position: relative;
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		margin-top: 16rpx;
		margin-bottom: 32rpx;
	}

	.uni-calendar__weeks-item {
		flex: 1;
	}

	.uni-calendar__weeks-day {
		flex: 1;
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 45px;
	}

	.uni-calendar__weeks-day-text {
		font-size: 14px;
	}

	.uni-calendar__box {
		display: flex;
		flex-direction: column;
		position: relative;
		background-color: #FFFFFF;
	}

	.uni-calendar__title-bg {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		justify-content: center;
		align-items: center;
		margin: 48rpx 48rpx 32rpx;
	}

	.uni-calendar__title-line {
		height: 2rpx;
		flex: 1;
		background-color: #E7EAF1;
	}

	.uni-calendar__title-text {
		font-size: 32rpx;
		flex: 1;
		line-height: 1;
	}
</style>
