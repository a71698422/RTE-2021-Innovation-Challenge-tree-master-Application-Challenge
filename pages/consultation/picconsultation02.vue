<template>
	<view>
		<view class="flex align-center">
			<uni-list class="text-left" :border="true">
				<uni-list-item leftText="病情描述">
					<view slot="body">
						<input class="uni-input" name="nickname" placeholder="请填写真实姓名" />
					</view>
				</uni-list-item>
				<uni-list-item leftText="患者身份证号">
					<view slot="body">
						<input class="uni-input" name="nickname" placeholder="请填写身份证号" />
					</view>
				</uni-list-item>
				<uni-list-item leftText="性别">
					<view slot="body">
						<view class="tag-view">
							<uni-tag class="mx-20" text="男" type="indigo" />
							<uni-tag class="piccon-tag" text="女" type="default" />
						</view>
					</view>
				</uni-list-item>
				<uni-list-item leftText="出生日期">
					<view slot="body">
						<input class="uni-input" name="nickname" placeholder="请选择出生日期" />
					</view>
				</uni-list-item>
				<uni-list-item leftText="体重">
					<view slot="body">
						<input class="uni-input" name="nickname" placeholder="请输入体重(kg)" />
					</view>
				</uni-list-item>
				<uni-list-item leftText="过敏史">
					<view slot="body">
						<view class="tag-view">
							<uni-tag class="mx-20" text="有" type="indigo" />
							<uni-tag class="piccon-tag" text="无" type="default" />
						</view>
					</view>
				</uni-list-item>
				<uni-list-item leftText="过往病史">
					<view slot="body">
						<view class="tag-view">
							<uni-tag class="mx-20" text="有" type="indigo" />
							<uni-tag class="piccon-tag" text="无" type="default" />
						</view>
					</view>
				</uni-list-item>
				<uni-list-item leftText="肝功能">
					<view slot="body">
						<view class="tag-view">
							<uni-tag class="mx-20" text="正常" type="indigo" />
							<uni-tag class="piccon-tag" text="异常" type="default" />
						</view>
					</view>
				</uni-list-item>
				<uni-list-item leftText="肾功能功能">
					<view slot="body">
						<view class="tag-view">
							<uni-tag class="mx-20" text="正常" type="indigo" />
							<uni-tag class="piccon-tag" text="异常" type="default" />
						</view>
					</view>
				</uni-list-item>
			</uni-list>
		</view>
		<view class="uni-flex mt-20">
			<button type="primary" class="piccon_button" @click="piconextAction"><text class="font-md">提交</text></button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style>
	page {
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		background-color: #FFFFFF;
		min-height: 100%;
		height: auto;
	}
	.tag-view {
		/* #ifndef APP-PLUS-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		justify-content: flex-start;
		align-items: flex-start;
	}

	.piccon-tag {
		margin-left: 20rpx;
		margin-right: 20rpx;
		background-color: #EDEEEF !important;
	}
	
	.piccon_button {
		width: 92%;
		padding: 0 72rpx;
		margin: 64rpx 32rpx;
		font-size: 48rpx;
		line-height: 1.8;
		border-radius: 8rpx;
		border-width: 0rpx;
		background-image: linear-gradient(90deg,#07C193, #3EAAB4);
	}
</style>
