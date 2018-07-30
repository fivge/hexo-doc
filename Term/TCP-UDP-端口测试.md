---
title: Linux下 TCP/UDP 端口测试
date: 2017-07-07 15:19:45
tags:
- TCP/UDP
- nc
- Term
categories:
- Term
---

# Linux下 TCP/UDP 端口测试

### 开启端口

> nc -- arbitrary TCP and UDP connections and listens

<!-- more -->

```shell
### server开启TCP端口
nc -l -p 22
### server开启UDP端口
nc -ul -p 123
### server查看TCP开启情况
netstat -ntpl
### server查看UDP开启情况
netstat -nupl
### h1/h2检验server端口连通性
### TCP
nc -vz 10.0.0.3 22
### UDP
nc -u -vz 10.0.0.1 123
```



### 检查端口连接性(待补充)

