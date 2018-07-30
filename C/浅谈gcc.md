---
title: 浅谈gcc
date: 2017-03-12 08:29:00
updated: 2018-07-15 18:34:33
tags:
- C
- gcc
categories:
- C
---

```c
#include<stdio.h>

int main(){
    printf("Hello World!\n");
    return 0;
}
```

<!--more-->

### 0x01简单编译

```bash
  gcc hello.c -o hello
  ### 或者
  gcc -o hello hello.c
  
  # 预处理
  gcc -E hello.c -o hello.i 
  # 编译成汇编代码Compilation
  gcc -S hello.i -o hello.s
  # 汇编Assembly
  gcc -c hello.s -o hello.o
  # 连接Linking
  gcc hello.o hello
```

**如果有用到math.h库等非gcc默认调用的标准库，使用 -lm参数**

### 0x02多程序编译

```shell
gcc a.c b.c -o run
```

###  0x03 错误检测

```bash
# 输出Warnning
gcc -pedantic hello.c -o hello
gcc -Wall hello.c -o hello
# 在有Warnning的地方强制停止
gcc -Werror hello.c -o hello
```

###  0x04 库文件链接

函数库实际上就是一些头文件（.h）和库文件（so、或lib、dll）的集合

库文件分为两大类分别是动态链接库（通常以.so结尾）和静态链接库（通常以.a结尾）,优先使用动态链接库

```bash
gcc –c –I /usr/dev/mysql/include test.c –o test.o
gcc –L /usr/dev/mysql/lib –lmysqlclient test.o –o test
```



### 参考文章

- <http://www.cnblogs.com/ggjucheng/archive/2011/12/14/2287738.html>
- http://wiki.ubuntu.org.cn/Compiling_C
- https://gcc.gnu.org/onlinedocs/gcc/Optimize-Options.html