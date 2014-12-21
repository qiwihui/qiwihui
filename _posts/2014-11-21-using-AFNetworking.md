---
layout: post
title: 在Swift中使用AFNetworking框架
description: 在Swift中使用AFNetworking框架
category: ProgramThinking
commentIssueId: 6
tags: swift, AFNetworking
---

如何在Swift项目中使用[AFNetworking](https://github.com/AFNetworking/AFNetworking)框架？

1. 安装[CocoaPods](http://cocoapods.org/)

   ```sh
   $ sudo gem install cocoapods
   ```

2. 安装AFNetworking。在项目的根目录中创建Podfile文件，写入如下内容：

   ```
   source 'https://github.com/CocoaPods/Specs.git'
   platform :ios, '8.0'
   pod 'AFNetworking'
   ```

   然后安装AFNetworking：

   ```
   pod install
   ```

3. 在项目中创建一个新的头文件，引用AFNetworking框架：

   ```
   #import <AFNetworking/AFNetworking.h>
   ```

4. 在`Build Settings->Objective-C Bridging Header`中引用这个头文件。

   ```
   yourappname/yourbridgefile.h
   ```

   这样就可以使用AFNetworking了：

   ```swift
   let manager = AFHTTPRequestOperationManager()
   manager.GET(  
     "http://headers.jsontest.com",
     parameters: nil,
     success: { (operation: AFHTTPRequestOperation!,
                 responseObject: AnyObject!) in
         println("JSON: " + responseObject.description)
     },
     failure: { (operation: AFHTTPRequestOperation!,
                 error: NSError!) in
         println("Error: " + error.localizedDescription)
     }
   )
   ```

更详细的[在这](https://github.com/AFNetworking/AFNetworking/wiki/Getting-Started-with-AFNetworking)
