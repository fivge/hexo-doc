---
title: vue-router
date: 2018-09-05 11:05:33
tags:
- Vue
- Vue-router
categories:
- Vue
---

### 思路一*(待重构)*

##### 安装

```bash
yarn add vue-router
```

##### 配置

```bash
➜  tree -L 2 -I node_modules

.
├── README.md
├── babel.config.js
├── package.json
├── public
│   ├── favicon.ico
│   └── index.html
├── src
│   ├── App.vue
│   ├── assets
│   ├── components
│   ├── main.js
│   ├── mock
│   ├── routers.js
│   ├── store
│   └── views
├── vue.config.js
└── yarn.lock
```

`main.js`

```js
import VueRouter from 'vue-router'
import routers from './routers' // ./routers <=> ./routeers.js 

Vue.use(VueRouter)

const router = new VueRouter({
  mode: 'history',
  routes: routers,
  base: '/contract/view/'
})

const vue = new Vue({
  router,
  render: h => h(App)
})
vue.$mount('#app')
```

`vue.config.js`

```js
module.exports = {
    baseUrl: './'
}
```

`routers.js`

*待优化*

> 项目一

```js
import Home from './components/home.vue'
import First from './components/children/first.vue'
import Login from './components/children/login.vue'

const routers = [
  {
    path: '/',
    component: Home,
　　 children: [ 
　　　{ 
　　　　path: '/', 
 　　　 component: Login 
　　  }
　　]
  },
  {
    path: '/home',
    name: 'home',
    component: Home,
    children: [
      {
        path: '/',
        name: 'login',
        component: Login
      },
      {
        path: 'first',
        name: 'first',
        component: First
      } 
    ]
  }
]

export default routers
```



> 项目二

```js
import Home from './views/home'
import Success from './views/success'
import Review from './views/review'
import Reject from './views/reject'
import Contract from './views/contract'
import Test from './views/test'
import Certified from './views/certified'
import Failure from './views/failure'
import Submitted from './views/submitted'

const routers = [{
    path: '/',
    component: Home,
    children: [{
            path: '/',
            component: Test
        }, {
            path: 'certified',
            component: Certified
        },
        {
            path: 'failure',
            component: Failure
        },
        {
            path: 'success',
            component: Success
        }, {
            path: 'review',
            component: Review
        }, {
            path: 'reject',
            component: Reject
        }, {
            path: 'contract',
            component: Contract
        }, {
            path: 'test',
            component: Test
        }, {
            path: 'submitted',
            component: Submitted
        }
    ]
}]

export default routers
```

`App.vue`

```vue
<template>
  <div>
    <router-view></router-view>
  </div>
</template>
```

`./views/home.vue`

```vue
<template>
<div id="app">
    <headerDiv></headerDiv>
    <router-view></router-view>
    <footerDiv></footerDiv>
</div>
</template>


<script>
import headerDiv from "../components/header";
import footerDiv from "../components/footer";

export default {
  name: "app",
  components: {
    headerDiv,
    footerDiv
  }
};
</script>

<style>
/* 全局样式 */

#app {
  font-family: "Helvetica Neue", Helvetica, "PingFang SC", "Hiragino Sans GB",
    "Microsoft YaHei", "微软雅黑", Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  /* margin-top: 60px; */
  /* background-image: image-set("") */
  /* background-image: url(../assets/bg4.jpg); */
  /* background-color: black; */
  /* background.jpg */
}

.el-row {
  margin-bottom: 20px;
}

h1 {
  font-size: 30px;
  padding: 0;
  margin: 0;
  margin-bottom: 20px;
}

h2 {
  font-size: 20px;
  padding: 0;
  margin: 0;
  margin-bottom: 20px;
}

h3 {
  font-size: 16px;
  padding: 0;
  margin: 0;
  margin-bottom: 20px;
}
</style>

```

##### 使用

```js
// 跳转路由
this.$router.push("/");
```

<!--more-->