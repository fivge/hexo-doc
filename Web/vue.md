---
title: vue
date: 2018-08-27 14:21:41
tags:
- vue
categories:
- Web
---



<!--more-->



> ### vue
>
> UI iview/element
>
> ```shell
> yarn add iview
> 
> yarn add element-ui
> 
> yarn add vue-router
> 
> yarn add axios
> 
> yarn add axios-mock-adapter
> 
> yarn add vuex
> ```
>
>
>
> ### 路由 vue-router
>
> ### 前后端交互 axios
>
> ### mock axios-mock-adapter
>
> ### 组件通信,传值 vuex
>
> #### 不同组件之间传值，通过eventBus（小项目少页面用eventBus，大项目多页面使用 vuex）

```
  QRCode.toCanvas(canvas,this.url,error=>{
if(error){
this,message.ennoni’下载失败！

}一
})
//下载二维码图片
letbase64Imgcanvas.toDataURL();
letoAdocument.cneateElement('a'
oA.hnefbase64Img;
oA.downloadparams.c一name;
leteventdocument.createEvent('MouseEvents');
ev/ent.initMouseEvent('click*,true,false,window,0,0,0,0,0,false,false,false,false,0,null);
oA.dispatchEvent(evzent);

```

### vuex

```js
    /* 
    ...mapActions({
      addCount: "increment"
    }),
    =>
    ...mapMutations({
      addCount: "increment"
    }),
    */
    /* 等价于
    => 
    addCount() {
      this.$store.commit("increment");
    },
    */
```

```
    get new_data() {
        return this._new_data;
    },
    set new_data(value) {
        this._new_data = value;
    },
```

---

`store/index.html`

```js
import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)

const state = {
    // 声明一个需要全局维护的状态 state
    success_data: {}, //  成功
    review_data: {}, // 审核
    reject_data: {}, // 驳回
    new_data: {}, // 新建
    modify_data: {}, // 修改
    status: "" // 状态 new / modify
}

const getters = {
    // ?
    // doneTodos: state => {
    //     return state.todos.filter(todo => todo.done)
    // },
    // doneTodosCount: (state, getters) => {
    //     return getters.doneTodos.length
    // }

}

const actions = {
    // increment(context) {
    //     context.commit('increment')

    // => this.$store.commit("increment");
    // }
    // => 
    // increment({
    //     commit
    // }) {
    //     commit('increment')
    // }
}

const mutations = {
    // // 每个 mutation 都有一个字符串的 事件类型 (type) 和 一个 回调函数 (handler)。
    // increment(state) {
    //     state.count++
    // },
    // increment2(state, n) {
    //     state.count += n
    // },
    // increment3(state, payload) {
    //     state.count += payload.amount
    // },
    // // person
    // set_person(state, payload) {
    //     state.person = payload
    // },
    set_success_data(state, payload) {
        state.success_data = payload
    },
    set_review_data(state, payload) {
        state.review_data = payload
    },
    set_reject_data(state, payload) {
        state.reject_data = payload
    },
    set_new_data(state, payload) {
        state.new_data = payload
    },
    set_modify_data(state, payload) {
        state.modify_data = payload
    },
    set_status(state, payload) {
        state.status = payload
    },


}

// 注册上面引入的各大模块
const store = new Vuex.Store({
    state, // 共同维护的一个状态，state里面可以是很多个全局状态
    getters, // 获取数据并渲染
    actions, // 数据的异步操作
    mutations // 处理数据的唯一途径，state的改变或赋值只能在这里
})

export default store // 导出store并在 main.js中引用注册。

// ...mapActions(
//         // 语法糖
//         ["modifyAName"] // 相当于this.$store.dispatch('modifyName'),提交这个方法
//     ),
//     trunToB() {
//         this.$router.push({
//             path: "/home/componentB"
//         }); // 路由跳转到B
//     }
// },
// computed: {
//     ...mapGetters(["resturantName"]) // 动态计算属性，相当于this.$store.getters.resturantName
// }
```

```js
// 加载页面

  <div v-loading.fullscreen.lock="fullscreenLoading">
    <h3>正在载入页面...</h3>
  </div>

  data() {
    return {
      fullscreenLoading: true
    };
  },
      
this.fullscreenLoading = false;  // 否

 setTimeout(() => {
 this.fullscreenLoading = false;
 }, 2000);

```

```
this.$notify.success(`提交成功`);
error info warning  success
this.$message


```

---

### 数组

https://segmentfault.com/a/1190000012429718

https://segmentfault.com/a/1190000003857670

https://www.jianshu.com/p/ec79c4e47370

http://es6.ruanyifeng.com/#docs/array

https://zhuanlan.zhihu.com/p/28508795

