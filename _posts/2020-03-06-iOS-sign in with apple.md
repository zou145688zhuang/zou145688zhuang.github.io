---
layout:     post
title:      Sign In With Apple
subtitle:   开发Sign In with Apple
date:       2020-03-06
author:     邹壮壮
header-img: img/post-ios13.jpeg
catalog: true
tags:
    - iOS
    - iOS开发基础

---



现有的应用和应用中，更新符合苹果审核规则中关于接入<font color=#F06045>Sign In With Apple</font>功能要求的必须进行接入.在 iOS 13 中苹果推出一种在 App 和网站上快速、便捷登录的方式: <font color=#F06045>Sign In With Apple</font>。这是 iOS 13 新增的功能，因此需要使用 Xcode 11 进行开发。关于应用是否要求接入此登录方式，苹果在 App Store 应用审核指南 中提到：





> Apps that exclusively use a third-party or social login service (such as Facebook Login, Google Sign-In, Sign in with Twitter, Sign In with LinkedIn, Login with Amazon, or WeChat Login) to set up or authenticate the user’s primary account with the app must also offer Sign in with Apple as an equivalent option.

如果你的应用使用了第三方或社交账号登录服务（如Facebook、Google、Twitter、LinkedIn、Amazon、微信等）来设置或验证用户的主账号，就必须把 <font color=#F06045>Sign In With Apple</font> 作为同等的选项添加到应用上。如果是下面这些类型的应用则不需要添加：

仅仅使用公司内部账号来注册和登录的应用；
要求用户使用现有的教育或企业账号进行登录的教育、企业或商务类型的应用；
使用政府或业界支持的公民身份识别系统或电子标识对用户进行身份验证的应用；
特定第三方服务的应用，用户需要直接登录其邮箱、社交媒体或其他第三方帐户才能访问其内容。

另外需要注意，关于何时要求接入 <font color=#F06045>Sign In With Apple</font>，苹果在 [News and Updates](https://developer.apple.com/news/) 中提到：

> Starting today, new apps submitted to the App Store must follow these guidelines. Existing apps and app updates must follow them by April 2020.



<font color=red>2019 年 9 月 12 日 起，提交到 App Store 的新应用必须按照应用审核指南中的标准进行接入；现有应用和应用更新必须也在 2020 年 4 月前完成接入。</font>

### 前期工作准备

1. 在开发者网站，在需要添加<font color=#F06045>Sign In With Apple</font>功能

