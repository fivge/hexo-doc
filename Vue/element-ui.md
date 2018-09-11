---
title: element-ui
date: 2018-08-23 15:04:51
tags:
- Vue
- element-ui
categories:
- Vue
---

<https://element.eleme.io/#/zh-CN/component/installation>

### 安装

```bash
vue create contract

yarn add element-ui
```

### 使用

`main.js`

```js
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';

Vue.use(ElementUI);
```

<!--more-->

##### 自定义组件宽度

> `style="width: 70%"`

```vue
  <el-select v-model="value" placeholder="请选择" style="width: 100%">
    <el-option v-for="item in options" :label="item.label" :value="item.value">
    </el-option>
  </el-select>
```

##### input框模糊查询提醒

<https://blog.csdn.net/sanlingwu/article/details/81335843>

