---
layout: post
title: "2014 WWDC Session 笔记(1) - cocoa touch 新特性"
tags: WWDC WWDC-2014
---

这一篇视频总体概述了今年的cocoa touch产生了哪些新特性，视频全长45分钟，涉及到的内容包括：

- ViewController适配
- Presentations适配
- 增加UIVisualEffectView
- Image Assets
- Condensing Bars
- 自适应的Table Cell
- App Extensions
- 第三方输入法
- Notification更新
- DocumentPickerViewController
- SDK Modernization
- Handoff
- Notification Center
- Photos
- CloudKit
- HealthKit
- Local Authentication
- SceneKit
- Core Locations

看了以上条目是不是觉得信息量超大，是的，今年cocoa touch所有的变动全部在这里了。

![cocoa touch](/images/whats_new_in_cocoa_touch.png)

下面简单介绍下上面的这些特性，而对应的每个特性的具体说明则可在单独的WWDC视频中找到:

####1. ViewController适配
- 增加了size classes，这是苹果今年主推的概念，跟autolayout配合可以解决多屏幕适配的问题
- 增加了margins属性，如下所示，现在在xcode6中新建autolayout就可以看到constrain to margins被默认选中：
![margin](/images/margin.png)
- 增加了UISplitViewController，这个原先是iPad上的控件，现在在iPhone上也可以统一使用了，而且官方建议使用，
用于以后取代NavigationController的push，目的是将这一过程自适应化。

####2. Presentations适配
- 增加UIPopoverPresentationController，它是UIPresentationController的子类，
可以控制view到底是以modal形式还是popover出来。
- UIAlertView 和 UIActionSheet弃用，改成使用UIAlertController代替
- UISearchController取代了UISearchDisplayController

####3. 增加UIVisualEffectView(背景虚化视图)
其中包括主要的类UIBlurEffect和UIVibrancyEffect，做虚化背景又很方便了很多。

####4. Image Asset
因为屏幕尺寸不定，所以想要用一张图片适配所有的尺寸变得越来越困难，
现在可以针对不同的size设置对应的image了。

####5. Condensing Bars
可收缩的导航栏和工具栏。这个以前需要我们自己写代码实现，现在苹果已经把它官方化了，
当推动scrollView时，可以使导航栏自动收缩，用于展现更多空间。

####6. Table Cell自适应
这个是一个非常给力的更新，用户终于可以不用再去写代码计算heightForRowAtIndexPath了。
当然，前期是要配置好autolayout

####7. App Extensions
现在开发者可以定制ios的app扩展了。

####8. 第三方输入法
iOS开始支持第三方输入法

####8. Notification更新
这是一个很有意思的更新，一直以来，app第一次打开时会弹出请求通知权限，但这些都是服务端通知，
本地通知在展现时依旧不需要权限(所以很多app明明已经关了权限结果还会有各种通知过来），现在
从iOS8开始，本地通知也需要开始请求权限。另外附加的一点是app可以发送一些非UI请求的数据来用于app更新，
而这些是不需要请求用户权限的。最后就是通知弹出按钮可以自定义了

####9. DocumentPickerViewController
开始支持iCloud和第三方文档。

####10. SDK Modernization
OC的语法更新,见[ModernizationObjC](https://developer.apple.com/library/ios/releasenotes/ObjectiveC/ModernizationObjC/AdoptingModernObjective-C/AdoptingModernObjective-C.html#//apple_ref/doc/uid/TP40014150)

- NS_DESIGNATED_INITIALIZER 一个宏，用于修饰构造函数
- 使用instancetype代替id
- properties

Xcode工具 Edit -> Refactor -> Convert to Modern OC Syntax..

####11. Handoff
Handoff也是一个比较有意思的概念，可以用于各设备之间的协作

####12. Notification Center
增加自定义控件

####13. Photos权限
可以调用camera接口调教对焦、曝光等等

####14. CloudKit权限
更多的数据访问权限
甚至可以利用CloudKit构建一个不需要server端的client-server应用

####15. HealthKit权限
获取用户的健康数据

####16. Local Authentication权限
主要包含获取Touch ID的权限

####17. SceneKit
3D绘图/游戏相关

####18. Core Locations
室内定位，听说更加精准，以及更少的耗电












