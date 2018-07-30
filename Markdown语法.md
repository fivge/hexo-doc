---
title: Markdown语法
tags: 
- Markdown
date: 2015-12-02 20:00:38
---

### 0x01 标题

```markdown
#一级标题
##二级标题
###三级标题
####四级标题
#####五级标题
######六级标题
#######没有七级标题
```

#一级标题
##二级标题
###三级标题
####四级标题
#####五级标题
######六级标题
#######没有七级标题
或者	

```	markdown
一级标题
======
二级标题
---
```


一级标题
======

二级标题
---
**三个（含）以上的`=`或者`-`就行了**

### 0x02 引用

```markdown
>区块引用
>>二级区块引用
>>>三级区块引用
```

>区块引用
>>二级区块引用
>>>三级区块引用

```markdown
>区块引用
```

>区块引用

### 0x03 列表

###### 无序列表

```markdown
* 无序列表1
* 无序列表2
* 无序列表3
```
可以用`*`、`+`或`-`加上空格` `表示
* 无序列表1
* 无序列表2
* 无序列表3

****

###### 有序列表

```markdown
1. 有序列表1
2. 有序列表2
3. 有序列表3
4. 有序列表4
```

1. 有序列表1
2. 有序列表2
3. 有序列表3
4. 有序列表4

****

###### 混合式

```markdown
+ First
  - 无序列表1
  - 无序列表2
  - 无序列表3
+ Next
+ Third
  1. Love
  2. is
  3. a
  4. **great**
  5. thing
+ Last 
```

+ First
  - 无序列表1
  - 无序列表2
  - 无序列表3
+ Next
+ Third
  1. Love
  2. is
  3. a
  4. **great**
  5. thing
+ Last 

### 0x04 代码
只需要在代码前插入4个（含）以上空格即可    
或者是

```markdown
​```
#include<stdio.h>
int main()    
{    
    print("Hello World!\n");    
return 0;    
}    
​```
```

***

```markdown
#include<stdio.h>
int main()
{
	print("Hello World!\n");
return 0;
}
```

### 0x05 代码段
用两个``` ` ```引用起来    

```markdown
这是一个代码段`fun()`    
```
这是一个代码段`fun()`

### 0x06 分割线
用三个（含）以上的`*`、`-`或者`_`即可

```markdown
---
***
______
```

---

***

______

### 0x07 链接
链接可以是网址，也可以是文件位置    
链接后加入`"标题"`可设置标题    

```markdown
链接1[Home](http://luanxingtong.com)
链接2[love](/source/"标题")
```
链接1[Home](http://luanxingtong.com)    
链接2[love](/source/"标题")

```markdown
    参考式链接 [Home][1]    
    [1]:    http://love.com "Title"    
    隐藏式链接[Google][]
    [Google]:    http://www.google.com
```

参考式链接 [Home][1]    
[1]:    http://love.com "Title"
隐藏式链接[Google][]
[Google]:    http://www.google.com

### 0x08 图片
###### (1) 行内式图片
```markdown
 ![Smaller icon](http://25.io/smaller/favicon.ico "Title here")
```
![Smaller icon](http://25.io/smaller/favicon.ico "Title here")
###### (2)参考式图片

```markdown
    ![Resize icon][Love] 
    [Love]: http://resizesafari.com/favicon.ico "Title"
```
![Resize icon][Love] 

[Love]:     http://resizesafari.com/favicon.ico "Title"
### 0x09 自动链接
```markdown
<http://pan.baidu.com>
<1214238229@qq.com>
```
<http://pan.baidu.com>

<1214238229@qq.com>

### 0x010 注释

```markdown
    测试注释[^1]
    [^1]: 	这是注释
```

测试注释[^1]
[^1]: 这是注释

### 0x11 强调
```markdown
*倾斜*
**加粗**
***倾斜&加粗***
_倾斜_
__加粗__
___倾斜&加粗___
```
*倾斜*

**加粗**

***倾斜&加粗***

_倾斜_

__加粗__

___倾斜&加粗___
### 0x12 删除线
```markdown
~~Snnnn~~
```
~~Snnnn~~
### 0x13 公式支持
```markdown
$$y=x^2$$
```
$$y=x^2$$
### 0x14 反斜杠\
`\`加以下字符可输入以下字符    
\+	\-	\*	\\	\#	\!	\.	\`	\_	\{}	\[]	\()	
### 0x15 表格
```markdown
列1 | 列2 | 列3 | 列4
--: | :---:| :---| ---
a   | b    |   c   | d   
A  |  B  |  C   | D  
```

|   列1 |  列2  | 列3   | 列4   |
| ---: | :--: | :--- | ---- |
|    a |  b   | c    | d    |
|    A |  B   | C    | D    |
