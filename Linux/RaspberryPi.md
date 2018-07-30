---
title: RaspberryPi
date: 2016-10-12 20:08:47
tags:
- RaspberryPi
---

### 设置静态ip

```bash
sudo ifconfig eth0 192.168.1.222 netmask 255.255.255.0

sudo route add default gw 192.168.1.1

sudo ifconfig eth0 up
```



修改 /etc/network/interfaces

```shell
sudo vim /etc/network/interfaces
```



修改为：

```shell
auto lo  

iface lo inet loopback  

iface eth0 inet static  

address 192.168.1.222  

netmask 255.255.255.0  

gateway 192.168.1.1  

allow-hotplug wlan0  

iface wlan0 inet manual  

wpa-roam /etc/wpa_supplicant/wpa_supplicant.conf  

```



重启服务

```shell
sudo service networking restart
```



### DNS

```shell
sudo cat /etc/resolv.conf
```

改成类似的即可

```shell
nameserver 8.8.8.8

nameserver 8.8.4.4

nameserver 208.67.220.220

nameserver 208.67.222.222

nameserver 10.10.10.10

```





```shell
root@raspberrypi:~# sudo service networking restart
```





### 自定义分辨率

<http://shumeipai.nxez.com/2013/08/31/custom-display-resolution-raspberry-pie.html>

修改`config.txt`文件

- 修改overscan选项

```shell
# uncomment this if your display has a black border of unused pixels visible and your display can output without overscan

disable_overscan=1

```



- 修改屏幕分辨率

```shell
# uncomment to force a console size. By default it will be display's size minus
# overscan.
framebuffer_width=1280
framebuffer_height=1024
```



- 修改屏幕属性

hdmi_group=2 选择计算机显示器分辨率。hdmi_mode=35 选择屏幕分辨率和刷新屏幕。
hdmi_ignore_edid=0xa5000080 命令树莓派不检测HDMI设备的任何信息，按照指定的分辨率输出。

```shell
# uncomment to force a specific HDMI mode (this will force VGA)
hdmi_group=2
hdmi_mode=35
hdmi_ignore_edid=0xa5000080
```

