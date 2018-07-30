---
title: Android去除感叹号(7.0+适用)
date: 2017-07-14 20:13:36
updated: 2018-05-20 14:15:43
tags:
- Android
categories:
- Android
---

  刷完国外的 ROM 后,由于国内的环境,WiFi和移动数据那里都有一个感叹号

>  ### 0x01 在 7.0 以前

**打开终端**

1. 关闭网络评估功能

```bash
su
settings put global captive_portal_detection_enabled 0
```

2. 替换服务器地址

```bash
settings put global captive_portal_server t.cn
```

> ### 0x02 7.0以后

然而,7.0以后,该方法失效

于是,替换服务器为google.cn的

```bash
settings put global captive_portal_https_url https://www.google.cn/generate_204
```

> ### 0x03 8.1

然而,在 8.1,在终端中输入以上命令报错.

改为在 adb 中执行

```bash
adb devices
adb shell
su
settings put global captive_portal_https_url https://www.google.cn/generate_204
```

> ### 0x04 搭建自己的 generate_204 服务器

#### Nginx

在nginx的服务器配置中，添加一个location

```bash
location /generate_204 { return 204; }
```

然后重启一下nginx服务就好了。

#### Apache

首先要确保已经安装了rewrite模块，不然以下方法不适用。

在.htaccess文件中（如果没有，就在根目录下新建一个空文件并命名为.htaccess即可）添加以下代码：

```bash
RewriteEngine On  
RewriteCond %{REQUEST_URI} /generate_204$  
RewriteRule $ / [R=204]
```

