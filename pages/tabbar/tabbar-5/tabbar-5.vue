<template>
	<view class="content">
		<image class="profile-image" src="https://fel.forxhr.top:2022/view.php/52c2767426e4658698d754f890f359d8.bmp" alt="认真猫应用" />
		<cl-cell-group title="基础设置">
		    <cl-cell title="账号与安全" icon="person"></cl-cell>
		    <cl-cell title="隐私设置" icon="locked"></cl-cell>
		    <cl-cell title="主题色" icon="color"></cl-cell>
		    <cl-cell title="QQ群号" icon="qq" value="883422705" ></cl-cell>
		    <cl-cell title="官方邮箱" icon="mail-open" value="1450788363@qq.com"></cl-cell>
			<cl-cell title="版本号" icon="calendar" value="Bata1.0"></cl-cell>
            <template>
  <view>
    <view class="developer-profile">
      <image class="profile-image" src="https://fel.forxhr.top:2022/view.php/52c2767426e4658698d754f890f359d8.bmp" alt="认真猫的头像" />
      <view class="contact-info">
        <text class="name">认真猫 (OwO)</text>
        <text class="description">网站开发者</text>
        <text class="contact">联系方法：B站搜索认真猫，
		QQ群：883422705</text>
      </view>
    </view>

    <view class="developer-profile">
      <image class="profile-image" src="https://fel.forxhr.top:2022/view.php/05ea6a6a5a543dc1b2df8ae28808bdfe.bmp" alt="ZH_MC的头像" />
      <view class="contact-info">
        <text class="name">ZH_MC</text>
        <text class="description">APP开发者</text>
        <text class="contact">联系方法：
		QQ：3023555095</text>
      </view>
    </view>

    <view class="developer-profile">
      <image class="profile-image" src="https://fel.forxhr.top:2022/view.php/b316daa185f102f73f7bc2d2f4299aff.jpg" alt="奕奕的头像" />
      <view class="contact-info">
        <text class="name">奕奕</text>
        <text class="description">APP开发者</text>
        <text class="contact">联系方法：
		B站e装机，
		微信：ezjyys</text>
      </view>
    </view>
  </view>
</template>

		</cl-cell-group>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		text-align: center;
		height: 400upx;
		margin-top: 200upx;
	}
	.developer-profile {
  display: flex;
  align-items: center;
}

.profile-image {
  width: 80upx;
  height: 80upx;
  border-radius: 50%;
  margin-right: 10upx;
}

.contact-info {
  font-size: 14upx;
}

.phone-icon::before {
  content: "\ue63d";
  font-family: "uni-icons";
  margin-right: 5upx;
}

.email-icon::before {
  content: "\ue615";
  font-family: "uni-icons";
  margin-right: 5upx;
  
}

</style>
