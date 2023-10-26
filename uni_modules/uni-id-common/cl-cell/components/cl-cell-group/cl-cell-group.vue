<template>
	<view class="cl-cell-group">
		
		<div v-if="title" class="cl-cell-group_header">
			<div :style="[titleStyle]" class="title">{{title}}</div>
			<div class="label">
				<slot name="label">{{label}}</slot>
			</div>
		</div>
		
		<div class="cl-cell-group_body">
			<slot></slot>
		</div>
		
	</view>
</template>

<script>
	export default {
		name: 'cl-cell',
		props: {
			title: {
				type: String,
				default: ''
			},
			label: {
				type: String,
				default: ''
			},
			titleStyle: {
				type: Object,
				default: ()=> {}
			}
		},
		data() {
			return {};
		},
	};
</script>

<style lang="scss" scoped>
	.cl-cell-group {
		padding: 0 25rpx;
		
		.cl-cell-group_header {
			padding-left: 30rpx;
			padding-right: 10rpx;
			margin-bottom: 10rpx;
			display: flex;
			align-items: center;
			justify-content: space-between;
			
			.title {
				font-size: 28rpx;
				color: #8b8b8b;
			}
			
			.label {
				font-size: 24rpx;
				color: #8b8b8b;
			}
		}
		
		.cl-cell-group_body {
			background-color: #f3f3f3;
			border-radius: 25rpx;
			overflow: hidden;
		}
		
	}
</style>