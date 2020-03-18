---
layout:     post
title:      jenkins 同时拉取多个git仓库
subtitle:   Jenkins编译任务如何下载多个git库代码到同一本地仓库
date:       2020-03-18
author:     邹壮壮
header-img: img/post-ios13.jpeg
catalog: true
tags:
    - iOS
    - jenkins
---

 随着公司不断发展，很多程序代码量和业务越来越多，组件化开发已经成为公司项目开发的主要选择。

##### 组件化拆分：

- 基础组件拆分（宏定义、分类、工具类...）
- 功能拆分（数据库、网络框架、图片加载...）
- 业务拆分（登录、聊天、商城、社区...）
- Router（负责模块之间的业务往来）

每个组件对应一个仓库，为了便于对代码管理，每个仓库又创建多个分支。这对Jenkins又有新的要求：Jenkins里下载代码时出现代码在不同的git库里面，怎么将不同位置的不同代码下载到同一个本地目录下？

解决方案：安装[Multiple SCMs Plugin](https://wiki.jenkins-ci.org/display/JENKINS/Multiple+SCMs+Plugin)插件.

(1) 安装好插件之后，选择Multiple SCMs，选择添加多个Git库

![sign_app_11](https://zou145688zhuang.github.io/img/jenkins/jenkis_1.png"创建 Services IDs")　

(2)每一个git库下载代码，指定下载到本地工作空间中指定的代码目录 

![sign_app_11](https://zou145688zhuang.github.io/img/jenkins/jenkins_2.png"创建 Services IDs")

（3）便于选择仓库的分支通过git parameter配置

![sign_app_11](https://zou145688zhuang.github.io/img/jenkins/jenkins_3.png"创建 Services IDs")

