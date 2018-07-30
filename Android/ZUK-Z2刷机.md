---
title: ZUK-Z2刷机
date: 2017-05-13 21:49:23
tags: 
- Android
- ZUK Z2
categories:
- Android
---

> ### 0x00 刷前须知

ZUK Z2 与 Z2 plus 通刷

> ### 0x01 进入开发者模式



> ### 0x02 解锁bootloader

<http://developer.zuk.com/bootloader_3>

```shell
adb devices
adb reboot bootloader
fastboot devices
fastboot flash unlock unlock_bootloader.img
fastboot oem unlock 
```



> ### 0x03 刷入recovery

```shell
fastboot flash recovery twrp-3.1.0-3-z2_plus.img
```



> ### 0x04 刷入镜像
>
> ### 0x05 刷supersu
>
> ### 0x06 刷opengapps



> ### 0x07 重新锁上bootloader

```shell
fastboot oem lock 
```

这时手机重启后无法 ~~开机~~ 关机，长按电源键手机重启，zuk开机第一屏闪过，呼吸灯常亮。

 **手机无法进入recovery，bootloader，更无法进入系统** 

> ### 0x08 重新关机

在网上逛了各种论坛，试了各种组合键，仍无解。

突然找到，长按电源键，带手机自动重启 **十一二次左右** (不一定就是11次)，会发现手机会完全关机而不再重启。这时，松开电源键即可。

> ### 0x09 重新解锁

此时手机会是完全关机的状态。若要进入bootloader，按住 `音量+` 与 `音量-` 键，然后把数据线插入电脑， ~~我也不知道为什么(ーー;)~~ ，然后松开音量加减键，会发现手机神奇般的进入了bootloader。

重复解锁步骤即可。
