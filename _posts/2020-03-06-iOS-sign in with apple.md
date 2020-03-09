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

###前期工作准备

1. 在开发者网站，在需要添加<font color=#F06045>Sign In With Apple</font>功能

   ![sign_app_1](https://zou145688zhuang.github.io/img/sign_app/sign_app_1.png"开启Sign In With Apple")

登录开发者中心，进入`Certificates, Identifiers & Profiles`，点击自己项目`App ID`，添加`Sign in with Apple`，保存

2. 创建 <font color=#F06045>Services IDs</font>

   ![sign_app_2](https://zou145688zhuang.github.io/img/sign_app/sign_app_2.png"创建 Services IDs")

点击左侧进入`Identifiers`，创建服务ID

![sign_app_3](https://zou145688zhuang.github.io/img/sign_app/sign_app_3.png"创建 Services IDs")

选择 `Services IDs`,然后`Continue`

![sign_app_4](https://zou145688zhuang.github.io/img/sign_app/sign_app_4.png"创建 Services IDs")

填写描述和服务 ID，服务 ID 填写规则如下面提示（我的 Demo `BundleID` 为 `com.hellohchen.signdemo`, 所以直接加了一个`.sign`，可以按照自己的项目和提示一样写，如示例`com.domainname.appname`），然后 点击`Configure`

![sign_app_5](https://zou145688zhuang.github.io/img/sign_app/sign_app_5.png"创建 Services IDs")

选择要实现`Sign in with Apple``APP ID``Sign in with Apple``Save`

点击`Services IDs`页面右上角`Continue`进入确认页，点击`Register`。

3. 创建基于<font color=#F06045>APP id</font>的密钥，以实现使用Apple登录

![sign_app_6](https://zou145688zhuang.github.io/img/sign_app/sign_app_6.png"创建 Services IDs")

进入证书主页面，点击左侧`Keys`，创建`Key`

![sign_app_7](https://zou145688zhuang.github.io/img/sign_app/sign_app_7.png"创建 Services IDs")

填写 `key Name`，选中`Sign in with Apple`，然后`Configure`

![sign_app_8](https://zou145688zhuang.github.io/img/sign_app/sign_app_8.png"创建 Services IDs")

选择要实现`Sign in with Apple`的 `APP ID`，保存`Save`，然后`Continue`进入确认页，点击`Register`

![sign_app_9](https://zou145688zhuang.github.io/img/sign_app/sign_app_9.png"创建 Services IDs")

按要求点击 `Done`，

![sign_app_10](https://zou145688zhuang.github.io/img/sign_app/sign_app_10.png"创建 Services IDs")

然后我们点击刚刚创建好的`Key` ，点击 `Download`

> <font color=red>注意！！该文件只能下载一次，注意好保存措施 ！</font>

###Xcode 项目配置

![sign_app_11](https://zou145688zhuang.github.io/img/sign_app/sign_app_11.png"创建 Services IDs")

项目添加 `Sign in with Apple`

###代码集成

1. 导入头文件

   ```objective-c
   #import <AuthenticationServices/AuthenticationServices.h>
   ```

2. 遵循代理

3. ```objective-c
   <ASAuthorizationControllerDelegate,ASAuthorizationControllerPresentationContextProviding>
   ```

- ASAuthorizationControllerDelegate 处理数据回调
- ASAuthorizationControllerPresentationContextProviding 设置上下文，管理视图弹出在哪里

3. 初始化按钮

   ```objective-c
   -(void)configUI{
       if (@available(iOS 13.0, *)) {
           self.authorizationButton = [[ASAuthorizationAppleIDButton alloc]init];
           [self.authorizationButton addTarget:self action:@selector(click) forControlEvents:(UIControlEventTouchUpInside)];
           self.authorizationButton.center = self.view.center;
           [self.view addSubview:self.authorizationButton];
       } else {
           // Fallback on earlier versions
       }
   }
   
   -(void)click API_AVAILABLE(ios(13.0)){
       ASAuthorizationAppleIDProvider *appleIDProvider = [[ASAuthorizationAppleIDProvider alloc]init];
       ASAuthorizationAppleIDRequest *request = [appleIDProvider createRequest];
       request.requestedScopes = @[ASAuthorizationScopeFullName,ASAuthorizationScopeEmail];
       ASAuthorizationController *auth = [[ASAuthorizationController alloc]initWithAuthorizationRequests:@[request]];
       auth.delegate = self;
       auth.presentationContextProvider = self;
       [auth performRequests];
   }
   
   
   4. 处理代理回调数据
   
      ///代理主要用于展示在哪里
      -(ASPresentationAnchor)presentationAnchorForAuthorizationController:(ASAuthorizationController *)controller API_AVAILABLE(ios(13.0)){
          return self.view.window;
      }
   
      -(void)authorizationController:(ASAuthorizationController *)controller didCompleteWithAuthorization:(ASAuthorization *)authorization API_AVAILABLE(ios(13.0)){
              if([authorization.credential isKindOfClass:[ASAuthorizationAppleIDCredential class]]){
                  ASAuthorizationAppleIDCredential *apple = authorization.credential;
                  ///将返回得到的user 存储起来
                  NSString *userIdentifier = apple.user;
                  NSPersonNameComponents *fullName = apple.fullName;
                  NSString *email = apple.email;
                  //用于后台像苹果服务器验证身份信息
                  NSData *identityToken = apple.identityToken;
              NSLog(@"%@%@%@%@",userIdentifier,fullName,email,identityToken);
          }else if ([authorization.credential isKindOfClass:[ASPasswordCredential class]]){
              
              //// Sign in using an existing iCloud Keychain credential.
              ASPasswordCredential *pass = authorization.credential;
              NSString *username = pass.user;
              NSString *passw = pass.password;
              
          }
      }
   
      ///回调失败
      -(void)authorizationController:(ASAuthorizationController *)controller didCompleteWithError:(NSError *)error API_AVAILABLE(ios(13.0)){
          NSLog(@"%@",error);
      }
   ```

   

   

   

   

   