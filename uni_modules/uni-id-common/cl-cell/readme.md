
## cl-cell 单元格

#### 基础功能
- 该组件需要搭配cell-group使用
- 通过title设置左侧标题，value设置右侧内容
- 通过icon字段设置图标
- 
#### 体验地址
[http://qiaozhen.labizhuanzhuan.cn/cl-cell](http://qiaozhen.labizhuanzhuan.cn/cl-cell)

---

![image](https://mp-61599c79-d7ee-4a75-a24b-e5a288da6dd3.cdn.bspapp.com/mine/cl-cell-yulan.png)

#### 基础使用

```
<cl-cell-group title="基础使用">
	<cl-cell title="账号与安全" icon="person"></cl-cell>
	<cl-cell title="隐私设置" icon="locked"></cl-cell>
	<cl-cell title="主题色" icon="color"></cl-cell>
	<cl-cell title="QQ号码" icon="qq" value="1321589787" ></cl-cell>
	<cl-cell title="邮箱号码" icon="mail-open" value="1321589787@qq.com"></cl-cell>
</cl-cell-group>
```

#### 高级使用(自定义)

```
<cl-cell-group title="高级使用 (自定义)" :titleStyle="{'margin-top': '50rpx'}">

	<cl-cell title="uniapp代码提示" :isLink="false" :border="false">
		<template #icon>
			<image src="../../static/logo.png" mode="widthFix" style="width: 40rpx;height: 40rpx;"></image>
		</template>

		<template #value>
			<switch checked style="transform:scale(0.8)" />
		</template>

		<template #label>uni-app在手，做啥都不愁</template>
	</cl-cell>

	<cl-cell title="跳转到我的页面" label="默认是navigateTo方式跳转" url="/pages/mine/mine" :border="false"></cl-cell>
	
	<cl-cell title="清除缓存" label="清除缓存记得加延时函数" value="100.13kb" name="user" @onItem="onItem" :border="false"></cl-cell>
	
	<cl-cell title="设置" icon="gear-filled" right-icon="paperplane-filled" icon-color="rgb(253 109 250)" :titleStyle="{'color': 'rgb(253 109 250)'} " :border="false"></cl-cell>

</cl-cell-group>
```


#### 单独使用
> 单独使用样式是经典款

```
<cl-cell title="朴素"></cl-cell>
<cl-cell title="瀑布"></cl-cell>
```

[图标示例地址](https://uniapp.dcloud.net.cn/component/uniui/uni-icons.html#%E5%9B%BE%E6%A0%87%E7%A4%BA%E4%BE%8B)

[自定义图标](https://uniapp.dcloud.net.cn/component/uniui/uni-icons.html#%E8%87%AA%E5%AE%9A%E4%B9%89%E5%9B%BE%E6%A0%87)
> 基于阿里图标库进行扩展

1. 将 iconfont.ttf、iconfont.css 放到项目根目录 static 下。
2. 打开 iconfont.css ,修改 @font-face为`url('@/static/iconfont.ttf') format('truetype');`
3. 在项目根目录的 App.vue 中，引入上述的 iconfont.css

```
<!-- App.vue -->
<style>
@import "@/static/iconfont.css";
</style>
```
4. 在组件中使用

```
<cl-cell icon="icon-swarm" isCustomize></cl-cell>
```



### API

#### CellGroup Props

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| --- | --- | --- | --- | --- |
| title | 分组标题 | String | - | - |
| titleStyle | 分组标题样式 | Object | - | - |

#### Cell Props
| 参数 | 说明 | 类型 | 默认值 | 可选值 |
| --- | --- | --- | --- | --- |
| title | 左侧标题 | String | - | - |
| label | 标题下方的描述信息 | String | - | - |
| value | 右侧的内容 | String | - | - |
| icon | 左侧图标名称(参照uni-icons组件名称) | String | - | - |
| iconSize | 左侧图标尺寸 | Number | 23 | - |
| iconColor | 左侧图标颜色 | String | #333 | - |
| isCustomize`1.0.1` | 自定义左侧图标(开启后icon传入图标名称) | Boolean | false | true |
| border | 是否显示下边框 | Boolean | true | false |
| url | 点击后跳转的URL地址 | String | - | - |
| linkType | 链接跳转的方式 | String | navigateTo | - |
| rightIcon | 右侧图标名称 | String | forward | - |
| isLink | 是否展示右侧箭头并开启点击反馈 | Boolean | true | false |
| isVibrate | 点击是否触发震动 | Boolean | false | true |
| disabled | 是否禁用 | Boolean | false | true |
| name | 标识符，用于在click事件中进行返回 | String , Number | - | - |
| titleStyle | 标题样式 | Object | - | - |
| height | cell高度 | String | - | - |

#### Cell Slot

| 名称 | 说明 |
| --- | --- |
| icon | 自定义左侧的图标 |
| label | 自定义label内容 |
| value | 自定义value内容 |
| rightIcon | 自定义右侧的图标 |


#### Cell Event

| 事件名 | 说明 | 回调参数 |
| --- | --- | --- |
| click | 点击cell列表时触发 | name: props的name参数标识符 |


### [遇到问题或者讨论 uniapp 加入QQ群  553291781](https://jq.qq.com/?_wv=1027&k=5UkMN1QX)