---
title: Windows安装
date: 2016-01-11 23:39:32
categories:
- Windows
---

## Windows安装

### 0x01 名词解释

+ 镜像

  常用镜像下载网站[I tell you](http://msdn.itellyou.cn)

+ Bios，UEFI

+ 分区格式:GPT,MBR

### 0x02 安装前的准备

#### (1) 检查刻录镜像

如果电脑是4G及以上的内存，则安装64位的操作系统

如果电脑的内存为2G或更低，则安装64位的操作系统

#### (2) 直接安装法

直接双击`setup.exe`安装

Win8,Win8.1及Win10下直接双击镜像文件即可;

Win7及更低版本需解压镜像文件(一般解压到非系统盘(一般为C盘)下，以免安装失败)

#### (3) 启动盘安装法

* 使用软件刻录镜像到U盘，制造启动盘

Win下推荐使用[软碟通](https://drive.google.com/open?id=0BzUyH3cJ-_5gVDY3bXJyX0VYeGs)进行刻录

![](http://ww2.sinaimg.cn/large/006tNc79ly1ffplj6gda7j30lh0f70tp.jpg)

![](http://ww4.sinaimg.cn/large/006tNc79ly1ffpljd9oeyj30lf0eo75f.jpg)

![](http://ww1.sinaimg.cn/large/006tNc79ly1ffpljhd6a7j30l70etabl.jpg)

![](http://ww4.sinaimg.cn/large/006tNc79ly1ffpljlhl66j30lb0etjsx.jpg)

![](http://ww4.sinaimg.cn/large/006tNc79ly1ffpljq0ac4j30f50faq33.jpg)


* 开机按`F2`或`F12`(一般这俩键了)进入`Bios`
* 设置Bios中U盘为第一启动项
* `F10`保存并退出(一般是F10)

![](http://ww1.sinaimg.cn/large/006tNc79ly1ffplkap5puj30hs0dcjre.jpg)

![](http://ww1.sinaimg.cn/large/006tNc79ly1ffplkgrbg9j30hs0dcmx5.jpg)



#### (4) 进入PE安装系统

首先，刻录WinPE到U盘，然后进入PE安装系统

推荐使用[微PE](http://www.wepe.com.cn)刻录WinPE 


**推荐使用第二种方法安装系统<br>若原系统能进入，可使用第一种方法**



### 0x03 开始安装系统

#### 安装XP


#### 安装Win7

安装Win7有两种方法

* 如果电脑支持UEFI启动，那么就选择UEFI+GPT的安装方法

* 如果电脑不支持UEFI,只支持Bios，那么就选择Bios+MBR的安装方法

#### 安装Win8 && Win8.1

#### 安装Win10

安装Win8,Win8.1及Win10一般都使用UEFI+GPT的方案

* 原系统内，直接进去CMD就好(别问我什么是CMD)
* 如果进入系统安装界面了，则按Shift+F10 调出CMD

然后输入:

```
diskpart    
list disk    //列出所有磁盘
sel disk 0    //选择磁盘0
convert GPT    //将磁盘转换成GPT格式的(如果是GPT的就不要转换了)
create partition EFI size=300    (选择EFI为300M是为了安装其他系统(如Mac)方便)
create partition MSR size=128    
exit
exit
```

**convert GPT[^1]**

[^1]: 若无法转换，可在PE下通过磁盘工具无损转换分区格式

![](http://ww4.sinaimg.cn/large/006tNc79ly1ffplkp9p7dj30qt0ftqo4.jpg)

![](http://ww3.sinaimg.cn/large/006tNc79ly1ffpll1df5wj30hs0bg124.jpg)

### 0x04 安装之后

#### 激活Windows

安装系统之后使用KMS激活，如想体验正版Win10，可加入[Insider计划](https://insider.windows.com)免费激活Win10

---

**激活器**

+ 激活Win10及Office2016[KMSpico Portable](https://drive.google.com/open?id=0BzUyH3cJ-_5gZXZzZFJoS1ZhdUk)先以管理员身份运行`Auto (Run as Admin).cmd` ,再以管理员身份运行`AutoPico.exe`
+ 激活Windows及Office常用 [HEU KMS Activator v10.0.0](https://drive.google.com/open?id=0BzUyH3cJ-_5gaXhXNjlmYVpYeW8)
+ 如无法激活可尝试使用[KMSpico_Install.3987](https://drive.google.com/open?id=0BzUyH3cJ-_5gV0ZCMnY1eklIbzQ)

#### 设置Win8，Win8.1及Win10自动登录

运行`（Win+R）`->输入“netplwiz”后进入
