---
title: js生成uuid
date: 2018-09-05 10:14:29
tags:
- JavaScript
- uuid
categories:
- JavaScript
---

*(未验证)*

<!--more-->

### 0x01 just random numbers that *look* like GUIDs

<https://stackoverflow.com/questions/105034/create-guid-uuid-in-javascript#>

##### sol 1

```js
function guid() {
  function s4() {
    return Math.floor((1 + Math.random()) * 0x10000)
      .toString(16)
      .substring(1);
  }
  return s4() + s4() + '-' + s4() + '-' + s4() + '-' + s4() + '-' + s4() + s4() + s4();
}

var uuid = guid();
```

##### sol 2

```js
function uuidv4() {
  return ([1e7]+-1e3+-4e3+-8e3+-1e11).replace(/[018]/g, c =>
    (c ^ crypto.getRandomValues(new Uint8Array(1))[0] & 15 >> c / 4).toString(16)
  )
}

console.log(uuidv4());
```

### 0x02 real GUID

##### node-uuid

<https://github.com/kelektiv/node-uuid>

###### 安装

```bash
# 安装
yarn add uuid
```

###### 使用

Version 1 (timestamp):

```js
const uuidv1 = require('uuid/v1');
uuidv1(); // ⇨ '3b99e3e0-7598-11e8-90be-95472fb3ecbd'
```

Version 3 (namespace):

```js
const uuidv3 = require('uuid/v3');

// ... using predefined DNS namespace (for domain names)
uuidv3('hello.example.com', uuidv3.DNS); // ⇨ '9125a8dc-52ee-365b-a5aa-81b0b3681cf6'

// ... using predefined URL namespace (for, well, URLs)
uuidv3('http://example.com/hello', uuidv3.URL); // ⇨ 'c6235813-3ba4-3801-ae84-e0a6ebb7d138'

// ... using a custom namespace
//
// Note: Custom namespaces should be a UUID string specific to your application!
// E.g. the one here was generated using this modules `uuid` CLI.
const MY_NAMESPACE = '1b671a64-40d5-491e-99b0-da01ff1f3341';
uuidv3('Hello, World!', MY_NAMESPACE); // ⇨ 'e8b5a51d-11c8-3310-a6ab-367563f20686'
```

Version 4 (random):

```js
const uuidv4 = require('uuid/v4');
uuidv4(); // ⇨ '3a017fc5-4f50-4db9-b0ce-4547ba0a1bfd'
```

Version 5 (namespace):

```js
const uuidv5 = require('uuid/v5');

// ... using predefined DNS namespace (for domain names)
uuidv5('hello.example.com', uuidv5.DNS); // ⇨ 'fdda765f-fc57-5604-a269-52a7df8164ec'

// ... using predefined URL namespace (for, well, URLs)
uuidv5('http://example.com/hello', uuidv5.URL); // ⇨ '3bbcee75-cecc-5b56-8031-b6641c1ed1f1'

// ... using a custom namespace
//
// Note: Custom namespaces should be a UUID string specific to your application!
// E.g. the one here was generated using this modules `uuid` CLI.
const MY_NAMESPACE = '1b671a64-40d5-491e-99b0-da01ff1f3341';
uuidv5('Hello, World!', MY_NAMESPACE); // ⇨ '630eb68f-e0fa-5ecc-887a-7c7a62614681'
```