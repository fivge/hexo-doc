---
title: js array
date: 2018-09-06 10:23:12
tags:
categories:
---

### 0x01 数组判空

```js
JSON.stringify(arr) === '[]'
arr.length === 0
+arr === 0
```

```js
// 实例
var arr = [];
if(Array.isArray(arr) && arr.length === 0){
    console.log('是空数组');
}
```



<!--more-->

### 0x02 元素是否在数组中

##### 循环

```js
var arr = ['a','s','d','f'];
console.info(isInArray(arr,'a'));//循环的方式

/**
 * 使用循环的方式判断一个元素是否存在于一个数组中
 * @param {Object} arr 数组
 * @param {Object} value 元素值
 */
function isInArray(arr,value){
    for(var i = 0; i < arr.length; i++){
        if(value === arr[i]){
            return true;
        }
    }
    return false;
}
```

##### Array.indexOf()

<https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf>

> `indexOf()`方法返回在数组中可以找到一个给定元素的第一个索引，如果不存在，则返回-1

```js
var beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

console.log(beasts.indexOf('bison'));
// expected output: 1

// start from index 2
console.log(beasts.indexOf('bison', 2));
// expected output: 4

console.log(beasts.indexOf('giraffe'));
// expected output: -1
```

### 0x03 copy

##### Array.slice()

> `slice()` 方法返回一个从开始到结束（**\*不包括结束***）选择的数组的一部分**浅拷贝**到一个新数组对象。且原始数组不会被修改。

<https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/slice>



```js
arr.slice();
// [0, end]

arr.slice(begin);
// [begin, end]

arr.slice(begin, end);
// [begin, end)
```



```js
// 实例
var animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// expected output: Array ["bison", "camel", "duck", "elephant"]

```

