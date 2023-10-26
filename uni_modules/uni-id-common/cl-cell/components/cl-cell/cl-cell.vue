<template>
	<view @tap="onCell" class="cl-cell" :class="{'disabled': disabled, 'active': isLink}" :style="{'height': height}">

		<view v-if="$slots.icon || icon" class="cl-cell__icon">
			<slot name="icon">
				<uni-icons :custom-prefix="isCustomize ? 'iconfont' : ''" :type="icon" :size="iconSize" :color="iconColor"></uni-icons>
			</slot>
		</view>

		<view :style="border ? '' : 'border: 0'" class="cl-cell__body">

			<view class="body__left">
				<view :style="[titleStyle]" class="title">{{title}}</view>
				<view v-if="$slots.label || label" class="label">
					<slot name="label">{{label}}</slot>
				</view>
			</view>

			<view class="body__right">

				<view class="right-value">
					<slot name="value">{{value}}</slot>
				</view>

				<view v-if="$slots.rightIcon || isLink" class="right-icon">
					<slot name="rightIcon">
						<uni-icons :type="rightIcon" :size="16" color="#999"></uni-icons>
					</slot>
				</view>
			</view>

		</view>

	</view>
</template>

<script>
	export default {
		name: 'cl-cell',
		props: {
			// 左侧标题
			title: {
				type: String,
				default: ''
			},
			// 标题下方的描述信息
			label: {
				type: String,
				default: ''
			},
			// 右侧的内容
			value: {
				type: String,
				default: ''
			},
			// 左侧图标名称
			icon: {
				type: String,
				default: ''
			},
			// 左侧图标是否自定义
			isCustomize: {
				type: Boolean,
				default: false
			},
			// 左侧图标尺寸
			iconSize: {
				type: Number,
				default: 23
			},
			// 左侧图标颜色
			iconColor: {
				type: String,
				default: '#333'
			},
			// 是否显示下边框
			border: {
				type: Boolean,
				default: true
			},
			// 点击后跳转的URL地址
			url: {
				type: String,
				default: ''
			},
			// 链接跳转的方式
			linkType: {
				type: String,
				default: 'navigateTo'
			},
			// 右侧图标名称
			rightIcon: {
				type: String,
				default: 'right'
			},
			// 是否展示右侧箭头并开启点击反馈
			isLink: {
				type: Boolean,
				default: true
			},
			// 点击是否触发震动
			isVibrate: {
				type: Boolean,
				default: false
			},
			// 是否禁用
			disabled: {
				type: Boolean,
				default: false
			},
			// 标识符，用于在click事件中进行返回
			name: {
				type: String | Number,
				default: ''
			},
			// 标题样式
			titleStyle: {
				type: Object,
				default: () => {}
			},
			// cell高度
			height: {
				type: String,
				default: ''
			}
		},
		data() {
			return {};
		},
		methods: {
			onCell() {
				if (this.disabled) {
					return false;
				}

				if (this.isVibrate) {
					uni.vibrate();
				}

				if (this.url) {
					uni[this.linkType]({
						url: this.url
					})
				}

				this.$emit('click', this.name) 
			},
		}
	};
</script>

<style lang="scss" scoped>
	view {
		box-sizing: border-box;
	}
	
	.disabled {
		background-color: rgba(255, 255, 255, 0.5) !important;

		.title,
		.uni-icons,
		.label {
			color: #ccc !important;
		}
	}

	.active {
		&:active {
			background-color: #f5f5f5;
		}
	}

	.cl-cell {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		background: #fff;
		padding-left: 30rpx;
		box-sizing: border-box;

		.cl-cell__icon {
			margin-right: 30rpx;
			line-height: 1;
		}

		.cl-cell__body {
			position: relative;
			height: 100%;
			flex: 1;
			display: flex;
			justify-content: space-between;
			align-items: center;
			border-bottom: 1px solid #f7f7f7;
			padding: 25rpx 0;

			.body__left {
				max-width: 70%;

				.title {
					font-size: 28rpx;
					color: #333;
				}

				.label {
					font-size: 24rpx;
					color: #a1a2a6;
					white-space: nowrap;
					text-overflow: ellipsis;
					overflow: hidden;
				}
			}

			.body__right {
				flex: 1;
				padding-right: 30rpx;
				display: flex;
				align-items: center;
				justify-content: flex-end;
				box-sizing: border-box;

				.right-value {
					font-size: 28rpx;
					color: #666;
				}


				.right-icon {
					color: #808083;
					margin-left: 20rpx;
				}
			}
		}
	}
</style>