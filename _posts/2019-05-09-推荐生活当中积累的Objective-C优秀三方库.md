---
layout:     post
title:      推荐生活当中积累的Objective-C优秀三方库
subtitle:   推荐生活当中积累的Objective-C优秀三方库
date:       2019-05-09
author:     邹壮壮
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - iOS
    - iOS开发基础
    - 开源框架
---

# 推荐生活当中积累的Objective-C优秀三方库

### 基于OC进行的相关推荐,常用程度：1-5星 每天会不定时更新，推荐好玩有趣的第三方优秀框架。

<br>

# Objective-C 

1. [Objective-C 框架搭建](#1)
2. [Objective-C 网络请求检测](#2) 
3. [Objective-C 数据解析存储](#3) 
4. [Objective-C 数据刷新加载](#4)
5. [Objective-C UI模块](#5) 
6. [Objective-C UI动画](#6) 
7. [Objective-C 图像](#7) 
8. [Objective-C 音视频处理](#8) 
9. [Objective-C 大型框架](#9) 
10. [Objective-C 大汇总](#10) 

<span id="1"></span>

# [Objective-C 框架搭建](#back)

| 推荐框架 | 推荐理由 | Github地址 |
| --- | --- | --- |
| CYLTabBarController | 【中国特色 TabBar】最低只需传两个数组即可完成主流App框架搭建。 | [点击前往](https://github.com/ChenYilong/CYLTabBarController) |
| DZNEmptyDataSet |是一个嵌入 UITableView/UICollectionView 超类的范畴(category),当视图没有要显示的内容时,它用于显示空数据集界面。|[点击前往](https://github.com/dzenbot/DZNEmptyDataSet)|
| XHLaunchAd |开屏广告、启动广告解决方案-支持静态/动态图片广告,mp4视频广告,全屏/半屏广告、兼容iPhone/iPad.|[点击前往](https://github.com/CoderZhuXH/XHLaunchAd)|
| CYLTableViewPlaceHolder |一行代码完成“空TableView占位视图”管理|[点击前往](https://github.com/ChenYilong/CYLTableViewPlaceHolder)|
|PYSearch| 一个非常优雅的搜索控制器iOS框架|[点击前往](https://github.com/ko1o/PYSearch)|
|JJException| 保护App,一般常见的问题不会导致闪退，增强App的健壮性，同时会将错误抛出来，根据每个App自身的日志渠道记录，下次迭代或者热修复以下问题 |[点击前往](https://github.com/jezzmemo/JJException)|

<br>

<span id="2"></span>

# [Objective-C 网络请求检测](#back)

| 推荐框架 | 推荐理由 | Github地址 | 推荐星级 |
| --- | --- | --- | --- |
| AFNetworking | 一款轻量级网络请求开源框架，基于iOS和mac os 网络进行扩展的高性能框架，大大降低了iOS开发工程师处理网络请求的难度，让iOS开发变成一件愉快的事情。|  [点击前往](https://github.com/AFNetworking/AFNetworking)   |  🌟🌟🌟🌟🌟   |
| CocoaAsyncSocket | 是谷歌的开发者，基于BSD-Socket写的一个IM框架，它给Mac和iOS提供了易于使用的、强大的异步套接字库，向上封装出简单易用OC接口。省去了我们面向Socket以及数据流Stream等繁琐复杂的编程。 | [点击前往](https://github.com/robbiehanson/CocoaAsyncSocket) | 🌟🌟🌟🌟🌟 |
|YTKNetwork|是猿题库 iOS 研发团队基于 AFNetworking 封装的 iOS 网络库，提供了更高层次的网络访问抽象。|[点击前往](https://github.com/yuantiku/YTKNetwork)|🌟🌟🌟🌟|
|Reachability|苹果提供过一个Reachability类，用于检测网络状态。但是该类由于年代久远，并不支持ARC。该项目旨在提供一个苹果的Reachability类的替代品，支持ARC和block的使用方式|[点击前往](https://github.com/tonymillion/Reachability)|🌟🌟🌟🌟|

<br>

<span id="3"></span>

# [Objective-C 数据解析存储](#back)

| 推荐框架 | 推荐理由 | Github地址 | 推荐星级 |
| --- | --- | --- | --- |
|YYModel| 数据解析Json框架，支持自动的 JSON/Model 转换，支持定义映射过程。 |[点击前往](https://github.com/ibireme/YYModel)|🌟🌟🌟🌟|
|JSONModel| 基于 JSON 的数据模型化框架。Model 需要继承自 JSONModel。| [点击前往](https://github.com/jsonmodel/jsonmodel) | 🌟🌟🌟🌟 |
|MJExtension|是一套字典和模型之间互相转换的超轻量级框架,使用简单无侵入。|[点击前往](https://github.com/CoderMJLee/MJExtension)|🌟🌟🌟|
|FMDB|是针对libsqlite3框架进行封装的三方，它以OC的方式封装了SQLite的C语言的API，使用步骤与SQLite相似。|[点击前往](https://github.com/ccgus/fmdb)|🌟🌟🌟🌟🌟|
|Realm|是由Y Combinator孵化的创业团队开源出来的一款可以用于iOS(同样适用于Swift&Objective-C)和Android的跨平台移动数据库。|[点击前往](https://github.com/realm/realm-cocoa)|🌟🌟🌟🌟|

<br>

<span id="4"></span>

# [Objective-C 数据刷新](#back)

| 推荐框架 | 推荐理由 | Github地址 | 推荐星级 |
| --- | --- | --- | --- |
|MJRefresh|可高度自定义的刷新第三方框架。|[点击前往](https://github.com/CoderMJLee/MJRefresh)|🌟🌟🌟🌟🌟|
|Toast|是一个Objective-C类，它向UIView对象类添加Toast通知|[点击前往](https://github.com/scalessec/Toast)|🌟🌟🌟🌟|
|SVProgressHUD|方法都是类方法，并且对象是通过单例创建|[点击前往](https://github.com/SVProgressHUD/SVProgressHUD)|🌟🌟🌟|
|MBProgressHUD|用法简单|[点击前往](https://github.com/jdg/MBProgressHUD)|🌟🌟🌟|

<br>

<span id="5"></span>

# [Objective-C UI模块](#back)

| 推荐框架 | 推荐理由 | Github地址 | 推荐星级 |
| --- | --- | --- | --- |
|Masonry|是一个轻量级的布局框架,拥有自己的描述语法,采用更优雅的链式语法封装自动布局,简洁明了并具有高可读性,而且同时支持 iOS 和 Max OS X。|[点击前往](https://github.com/SnapKit/Masonry)|🌟🌟🌟🌟🌟|
|IMYAOPTableView|无业务入侵，无逻辑入侵，外部察觉不到的 UITableView/UICollectionView AOP 框架|[点击前往](https://github.com/MeetYouDevs/IMYAOPTableView)|🌟🌟🌟|
|IGListKit|一个数据驱动的UICollectionView框架，用于构建快速和灵活的列表|[点击前往](https://github.com/Instagram/IGListKit)|🌟🌟🌟🌟|
|Charts|以一款用于绘制图表的框架，可以绘制柱状图、折线图、K线图、饼状图等|[点击前往](https://github.com/danielgindi/Charts)|🌟🌟🌟🌟|
|XLForm|灵活和强大的iOS库来创建动态的表观形态|[点击前往](https://github.com/xmartlabs/XLForm)|🌟🌟🌟🌟|
|JSDropDownMenu|类似美团的下拉菜单|[点击前往](https://github.com/jsfu/JSDropDownMenu)|🌟🌟🌟🌟|
|YYKit|是一组庞大、功能丰富的 iOS 组件|[点击前往](https://github.com/ibireme/YYKit)|🌟🌟🌟🌟|
|FSCalendar|是一款开源iOS日历控件|[点击前往](https://github.com/WenchaoD/FSCalendar)|🌟🌟🌟🌟|
|PYSearch|一个非常优雅的搜索控制器iOS框架|[点击前往](https://github.com/ko1o/PYSearch)|🌟🌟🌟🌟|
|SDCycleScrollView|无限循环自动图片轮播器|[点击前往](https://github.com/gsdios/SDCycleScrollView)|🌟🌟🌟🌟|
|ViewDeck|是一个有黑色透明遮罩层轻量级的侧边栏抽屉控件,其支持左侧抽屉和右侧抽屉。|[点击前往](https://github.com/ViewDeck/ViewDeck)|🌟🌟🌟🌟|
|TYPagerController|页面滚动视图和控制器，简单，自定义高，并有许多选项卡样式|[点击前往](https://github.com/12207480/TYPagerController)|🌟🌟🌟🌟|
|SCLAlertView|自定义的UIAlertView，更漂亮哦|[点击前往](https://github.com/dogo/SCLAlertView)|🌟🌟🌟|

<br>

<span id="6"></span>

# [Objective-C UI动画](#back)

| 推荐框架 | 推荐理由 | Github地址 | 推荐星级 |
| --- | --- | --- | --- |
|Pop|Facebook发布的动画引擎，用以扩展iOS、OSX的动画类型。相较于iOS、OSX中的基本动画效果，Pop扩展后支持弹簧动画效果与衰减动画效果，你可以用Pop动画引擎来构建出真实的物理交互效果。|[点击前往](https://github.com/facebook/pop)|🌟🌟🌟🌟|
|TABAnimated|原生骨架屏，网络加载过渡动画|[点击前往](https://github.com/tigerAndBull/TABAnimated)|🌟🌟🌟🌟|

<br>

<span id="7"></span>

# [Objective-C 图像](#back)

| 推荐框架 | 推荐理由 | Github地址 | 推荐星级 |
| --- | --- | --- | --- |
|SDWebImage|一个可管理远程图片异步加载并缓存的类库。这个类库提供一个UIImageView类别以支持加载来自网络的远程图片。具有缓存管理、异步下载、同一个URL下载次数控制和优化等特征。|[点击前往](https://github.com/rs/SDWebImage)|🌟🌟🌟🌟🌟|
|TZImagePickerController|一个支持多选、选原图和视频的图片选择器，同时有预览、裁剪功能，支持iOS6+。|[点击前往](https://github.com/banchichen/TZImagePickerController)|🌟🌟🌟🌟|
|LBXScan|iOS 二维码、条形码|[点击前往](https://github.com/MxABC/LBXScan)|🌟🌟🌟🌟|
|MWPhotoBrowser|是一个强大且古老的图片浏览库，在GitHub上有英文版的详细使用说明。它同时依赖DACircularProgress ，MBProgressHUD ，SDWebImage。|[点击前往](https://github.com/mwaterfall/MWPhotoBrowser)|🌟🌟🌟|
|NYXImagesKit|可对图像/图片进行多个处理，比如筛选、模糊、优化、蒙版、调整大小、旋转以及保存等等|[点击前往](https://github.com/Nyx0uf/NYXImagesKit)|🌟🌟🌟|

<br>

<span id="8"></span>

# [Objective-C 音视频处理](#back)

| 推荐框架 | 推荐理由 | Github地址 | 推荐星级 |
| --- | --- | --- | --- |
|ZFPlayer|是一款基于AVPlayer,支持横屏、竖屏(全屏播放还可锁定屏幕方向),上下滑动调节音量、屏幕亮度,左右滑动调节播放进度的视频播放器软件。|[点击前往](https://github.com/renzifeng/ZFPlayer)|🌟🌟🌟🌟|
|ICGVideoTrimmer|提供提供视频剪切的视图|[点击前往](https://github.com/itsmeichigo/ICGVideoTrimmer)|🌟🌟🌟🌟|

<br>

<span id="8"></span>

# [Objective-C 音视频处理](#back)

| 推荐框架 | 推荐理由 | Github地址 | 推荐星级 |
| --- | --- | --- | --- |
|IQKeyboardManager|可以防止键盘滑动问题和覆盖UITextField / UITextView无需你输入任何代码,不需要额外的设置要求。|[点击前往](https://github.com/hackiftekhar/IQKeyboardManager)|🌟🌟🌟🌟|
|objection|自定义的UIAlertView，更漂亮哦|[点击前往](https://github.com/dogo/SCLAlertView)|🌟🌟🌟|
|SCLAlertView|自定义的UIAlertView，更漂亮哦|[点击前往](https://github.com/dogo/SCLAlertView)|🌟🌟🌟|
|SCLAlertView|自定义的UIAlertView，更漂亮哦|[点击前往](https://github.com/dogo/SCLAlertView)|🌟🌟🌟|
|SCLAlertView|自定义的UIAlertView，更漂亮哦|[点击前往](https://github.com/dogo/SCLAlertView)|🌟🌟🌟|
|SCLAlertView|自定义的UIAlertView，更漂亮哦|[点击前往](https://github.com/dogo/SCLAlertView)|🌟🌟🌟|

<br>
<br>
<br>
<br>
<br>