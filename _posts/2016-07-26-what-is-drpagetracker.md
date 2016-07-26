---
layout: post
title: "开源一个iOS里追踪当前所在页面(ViewController)的小工具"
tags: 开源 iOS PageTracker
---

很多时候，当你入职一家新公司或者接触一个新项目的时候，往往不知道当前 App 的展示页面到底对应哪一段代码，经常需要通过查看工程结构或者搜索具体关键字来确定到底是哪一个 ViewController

所以当有时候需要临时找一些东西的话，定位效率还是比较低的，此时我就想是不是有一种更方便的方式来直接定位到当前页面所在的具体ViewController，这也是 DRPageTracker 开发的初衷：


#### 项目地址
DRPageTracker [https://github.com/Shevckcccc/DRPageTracker](https://github.com/Shevckcccc/DRPageTracker)


#### 项目介绍

其实这是一个非常简单的小项目，只有一个 Category ，原理也非常简单，就是通过 Objective-C 的运行时特性，给 UIViewController 的 viewDidAppear 方法里面加上一段代码，先执行原有的代码，再打印当前所在的 Class 名，由于是放在 Category 中，所以不需要主动 import 进来，只要能通过 pod install 安装进来就行了，非常轻量

```
pod 'DRPageTracker'
```

然后 install 一下就行了，不需要本地添加任何代码，就可以在控制台看到所有的 ViewController 展现顺序

比较适合新人熟悉旧代码时使用
