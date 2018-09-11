---
title: Html
date: 2018-08-22 17:39:24
tags:
categories:
---



<!--more-->

### 引用js乱码

```html
charset="UTF-8"
```

### 上传按钮

<https://www.jianshu.com/p/07c27e576b26>

### 表格

<http://bootstrap-table.wenzhixin.net.cn/zh-cn/documentation/>

### 鼠标移入移出事件 blur

<http://www.w3school.com.cn/jquery/event_blur.asp>

### 下拉框默认值

```html
<tr>
<td>证件类型：<input id="cert_type" value="<{$data.cli_cert_type}>" type="text"/></td>
<td>
<select name="cli_cert_type"id="cli_cert_type"  style="width:160px">
<option value="身份证" >身份证</option>
<option value="士兵证">士兵证</option>
<option value="军官证">军官证</option>
<option value="护照" >护照</option>
<option value="户口本">户口本</option>
</select>
</td>
</tr>
<script>
$(document).ready(function(){
   $("#cli_cert_type").val("$(ssssss)");
});
    
```

