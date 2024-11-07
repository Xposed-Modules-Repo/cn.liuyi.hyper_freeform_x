# HyperFreeformX

## 介绍

自从Hyper发布以来，MIUI小窗X很长时间没有再继续更新，一个原因是当时毕业季来临，一堆事情需要处理；加上之前是第一次使用Kotlin开发，整个项目结构混乱，也提不起继续维护的兴趣。后面Hyper发布，又没有机型测试，于是Hyper小窗X一鸽又鸽。

不过现在虽迟但到，目前自由小窗X经过在内测群的不断更新修改，功能也比较稳定了，所以也就可以发出来了。

## 自由小窗X目前存在的功能：

- 通知与控制中心：
  - 点击小窗打开磁贴
  - 点击通知使用小窗打开
  - 移除通知下来白名单
- 轻量打开
  - 应用间跳转：当发生任务栈（可以理解为最近任务里面的一个窗口）相互调用切换时，目标应用将使用小窗打开
  - 系统分享：其他应用使用系统的分享功能后使用小窗打开
  - 传送门：使用小窗处理传送门
  - 打开链接：比如很多应用中的“在浏览器中打开”
  - 快捷搜索：酷安等一些应用在选择文字后出现搜索图标，使用小窗打开
  - 文字处理：同快捷搜索
  - 微信分享：HyperOS自带，但可能过滤掉部分情况，所以这个属于系统增强
  - QQ 分享：HyperOS自带，但可能过滤掉部分情况，所以这个属于系统增强
  - QQ 登录：HyperOS自带，但可能过滤掉部分情况，所以这个属于系统增强
- 自由小窗配置：主要是对小窗的大小和位置进行自定义
  - 禁用小窗位置偏移：让小窗永远从固定的位置出现
  - 记住小窗位置：从迷你小窗或贴边小窗进入普通小窗时会恢复之前的位置
- 背景与手势：可以在小窗后面添加模糊、阴影的背景，同时有单击、双击、长按手势对小窗进行操作

- 平行小窗：主要实现变刷pyq边回消息（目前只对微信进行适配，其他应用可通过白名单开启，出现问题不予修复）

- 其他：
  - 去除各种黑名单
  - 禁用后台贴边小窗
  - 系统桌面小窗捷径（当存在一个小窗时，可尝试多开小窗）
  - 小窗沉浸（隐藏小窗的顶部栏、底部栏）

自由小窗X的功能就是上面这些了

## 使用要求

- Android 14
- Hyper OS 1.0
- 部分功能平板和Fold2可能出现问题，请理性反馈

<!--Hyper 2.0 尚未支持-->

## 版本分发



## 支持作者

[爱发电](https://afdian.com/a/liuyia)

### 微信赞赏

![image-20240819163613185](images/image-20240819163613185.png)

### 支付宝

![image-20240819163738834](images/image-20240819163738834.png)

### QQ频道

![image-20240819163904666](images/14ed92849d807e48945643c12f890570.jpeg)

## 特别注意

本模块是修改系统框架的Xposed模块，可能会造成软重启等情况，使用前自行做好应对措施，作者不对此承担任何责任。