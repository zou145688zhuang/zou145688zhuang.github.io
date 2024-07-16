2024-04-10-iOS 开发们，是时候干掉Charles了.md

---
layout:     post
title:      开发们，是时候干掉Charles了
subtitle:   开发工具
date:       2024-01-17
author:     邹壮壮
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:

    - iOS
    - iOS开发工具

---

**这里每天分享一个 iOS 的新知识，快来关注我吧**

### 前言

一说到 mac 上的抓包工具，大家自然而然的会想到 Charles，作为老牌抓包工具，它功能很全面，也很强大。但是随着系统的不断更新迭代，Charles 的一些缺点也慢慢表露出来，比如：

1.  卡顿，特别在一些低端 Mac 机型上比较卡，体验就很差
    
2.  吃内存，时间久了总是得重启一下，不然内存吃的太多
    
3.  页面老旧，感觉像是旧时代的产品
    

今天来介绍一个我觉得比较好用的抓包工具，Proxyman

### Proxyman 配置

安装就不说了，大家可以自行去官网下载安装。

Proxyman 提供了一个免费版本，其中包含所有基本功能，平时使用应该是够了，如果重度使用，也可以考虑购买高级版本。

这是他的主页面，看起来是不是挺干净的：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/56b8bfdf46d74f309288e59a0deabb35~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=1080&h=635&s=36086&e=webp&b=202324)

安装好了之后都需要配置代理和 https 证书，这点 Proxyman 做的非常好，首先点击顶部导航上的证书，可以看到所有安装证书的选项：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/119df1cbfb864c1bbdf2bba1ccb9e615~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=630&h=636&s=21920&e=webp&b=333333)

教程是全中文的，而且设置步骤非常详细，比如 iOS 设置指南：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e40a5ce5973e44569e9a602a83bfd4da~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=1080&h=1255&s=69324&e=webp&b=3a3a3a)

Proxyman 针对 iOS 开发还提供了一种**无配置**的方案，可以直接通过 Pod 或者 SPM 添加 `atlantis-proxyman`框架，这样可以在不进行任何配置的情况下进行代理监听：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bf6421e9b0b14c788d55ea67f9a728d8~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=600&h=556&s=127822&e=png&b=2a2a2a)

除了监控手机的流量，也可以很方便地添加 iOS 模拟器的监控，只需要选择**顶部菜单 -> 证书 -> 在 iOS 上安装证书 -> 模拟器**：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/306f82641c4641df8ef7704c20c9f775~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=600&h=351&s=74929&e=png&b=3b3b3b)

按照以上步骤操作即可。

### 使用

配置完成之后就可以在 Proxyman 主页面上看到接口请求了，接下来介绍一些常用的功能。

### 本地 Mock 数据

本地 Mock 数据是很常见的需求，你只需要选中某个接口后，鼠标右键，选择**工具 -> 本地映射**：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ee929afb3e1348a7867860a7c03626e8~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=600&h=857&s=307765&e=png&b=252628)

然后在弹出的新页面中编辑相应即可，非常方便：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2d980658da5840308a5fd0cf47ede266~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=600&h=460&s=82497&e=png&b=202020)

### 断点

断点工具可以让我们动态编辑请求或响应的内容。

它本地映射在同一个菜单栏里，鼠标右键，选择**工具 -> 断点**，然后进行对应的设置即可。

创建断点后，Proxyman 将在收到我们想要拦截的请求或响应后立即打开一个新的编辑窗口。然后我们根据需要修改数据，最后再继续即可。

### 导出请求和响应数据

有时候我们需要把有问题的接口保存下载给其他服务端的同学查看。选中具体的请求，点击鼠标右键，选择**导出**，然后再选择你要导出的格式：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/84a930d7d4de4d2f8da35ef32b2c7cd7~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=600&h=897&s=314544&e=png&b=27282a)

不过这里导出的 Proxyman 日志需要使用 Proxyman 才能打开，也就是说，需要想查看这条请求的人的电脑上也安装 Proxyman，如果他没有安装，也可以选择拷贝 cURL。

### 模拟弱网

好的产品一定能够在弱网下正常使用，所以弱网测试也成为了日常开发必要的步骤，点击顶部菜单栏，选择**工具 -> 网络状况**，可以打开一个新页面，然后点击左下角为一个新的域名添加网络状况，这里可以根据你的需求选择不同的网络状况：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9343c872fece4a38ba5a2edca3757f62~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=600&h=274&s=54910&e=png&b=232323)

版权
谈起网络调试工具的时候，相信大家都能联想到一些工具，比如Charles和Fiddler，但是时隔今日，当我们再次谈论起网络抓包工具的时候，我不得不推荐一款名叫 Tanggo 的工具了。

### 工具对比
既然是网络调试工具，那么我们直观对比一下各个工具的区别：

#### Fiddler
下载链接：[Download Fiddler Web Debugging Tool for Free by Telerik](https://www.telerik.com/download/fiddler "Download Fiddler Web Debugging Tool for Free by Telerik")

Fiddler工具非常经典且强大。它可以提供电脑端、移动端的抓包、包括http协议和https协议都可以捕获到报文并进行分析；可以设置断点调试、截取报文进行请求替换和数据篡改，也可以进行请求构造，还可以设置网络丢包和延迟进行APP弱网测试等。

优点：

免费：Fiddler 是开源免费软件。
功能齐全：Fiddler具有非常丰富的功能，例如自动响应、脚本编辑、性能测试等
插件支持：Fiddler支持插件扩展，用户可以根据自己的需求安装不同的插件来增强Fiddler的功能。
缺点：

平台支持：主要支持Windows，其他系统操作毫无用武之地。
界面复杂：Fiddler的用户界面相对较为复杂，对于新手来说可能需要一定的学习成本。
配置繁琐：Fiddler的某些功能配置相对繁琐，例如设置SSL代理抓取HTTPS请求，需要进行证书安装等操作。
![Fiddler](img/markdown_post/Fiddler.png "实例")

#### Charles
下载地址：[Download a Free Trial of Charles • Charles Web Debugging Proxy](https://www.charlesproxy.com/latest-release/download.do "Download a Free Trial of Charles • Charles Web Debugging Proxy")

Charles工具别名“花瓶”，它是通过代理来实现的抓包，也就是我们在访问网页时配置代理指向Charles监听的端口，之后所有的请求Charles会帮我们转发并记录。

优点：

跨平台：Charles支持Windows、Mac和Linux操作系统
界面友好：Charles的用户界面相对更加直观和简洁，对于新手来说更容易上手。
支持SSL代理：Charles可以轻松地设置SSL代理，使得用户可以抓取HTTPS请求并查看明文信息。
缺点：

价格昂贵：Charles是收费软件，个人版需要购买许可证，
功能相对较少：相较于Fiddler，Charles的功能相对较少，可能无法满足一些高级用户的需求。
![Charles](img/markdown_post/Charles.png "实例")

#### TangGo
下载地址：[TangGo测试平台](https://tanggo.nosugar.tech/ "TangGo测试平台")

TangGo测试平台是一款国产化综合性测试平台，为软件测试、网络安全从业人员提供强大且易用的测试工具及多人协同的工作环境，主要用于Web站点的功能测试、安全测试和安全评估。

优点：

跨平台：TangGo支持Windows、Mac和Linux操作系统
免费：TangGo 社区版完全免费，并且社区版和付费版抓包工具功能没有任何阉割
功能齐全：支持多种测试场景，如半自动测试、自定义流程、强大的数据包编辑等。
插件支持：Tanggo 支持多种插件，支持用户自定义编写也支持内置下载。
界面友好：Tanggo 为中文界面，布局清晰，对新手很友好。
配置轻松：用户无需繁杂配置，轻松抓取 SSL 请求。
缺点：

处于上升期，更新会较为频繁
国内新产品，用惯国外产品可能需要适应期间
![TangGo](img/markdown_post/TangGo.png "实例")

### 总结

综上所述，TangGo 这款国产化的工具它集成了Charles 和Fiddle 的优点，同时也摒弃了它们的缺点，不过目前测试抓包工具也是非常多，而它们各有各的优势，也有对应的不足，所以根据自己的使用场景，选择适合的抓包工具才是重要的！

从流畅度、功能引导等方面，我感觉 Proxyman 是比 Charles 好用的，除了以上介绍到的功能，还有很多更强大更全面的功能。例如远程映射、保存会话、GraphQL 调试、黑名单白名单、Protobuf、自定义脚本等等，大家可以自己试试看。