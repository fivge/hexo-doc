---
title: Java时间戳
date: 2018-08-22 17:40:10
tags:
categories:
---



<!--more-->

```java

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Calendar;
import java.util.Date;

class Data{
  public static void main(String[] args) {
    //输入日期，转化为毫秒数，用DATE方法()
		/**
		 * 先用SimpleDateFormat.parse() 方法将日期字符串转化为Date格式
		 * 通过Date.getTime()方法，将其转化为毫秒数
		 */
		String date = "2001-03-15 15-37-05";
		SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd HH-mm-ss");//24小时制
//		SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd hh-mm-ss");//12小时制
		long time2 = simpleDateFormat.parse(date).getTime();
		System.out.println(time2);
  }
}

```

