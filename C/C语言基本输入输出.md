---
title: C语言基本输入输出
date: 2018-07-14 23:37:33
tags:
- C
categories:
- C
---

`printf("Hello World\n");`

<!--more-->

### 0x01 基本输入

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    //第一种情况
    //有多组测试数据，直到读至输入文件结尾为止
    int a;
    int b;
    while(scanf("%d %d",&a,&b)!=EOF){
        printf("%d\n",a+b);
    }
    //第二种情况
    //在开始的时候输入一个N，接下来是N组数据
    int n;
    int sum = 0;
    int i;
    scanf("%d",&n);
    for(i = 0; i < n; i++){
        int t;
        scanf("%d",&t);
        sum = sum + t;
    }
    printf("%d\n",sum);
    //第三种情况
    //输入不说明有多少组数据,但以某个特殊输入为结束标志
    //以输入 0 0 结束
    int a,b;
    while( scanf("%d %d",&a,&b) && (a || b) )
    {
        printf("%d\n",a+b);
    }
	//字符串输入
    //一整行字符串
    char buf[20];
    gets(buf);
    return 0;
}
```

