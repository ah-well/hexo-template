---
title: vue试题
date: 2019-05-14 23:16:33
tags:
---

### vue试题

- vue视图不会更新
  - data里边设置 $set
- nextTick()
  - 在Vue生命周期的created()钩子函数进行的DOM操作一定要放在Vue.nextTick()的回调函数中
- vue路由导航钩子（）
  1. 全局导航钩子：分为前置守卫、后置钩子
     1. 前置守卫：router.beforeEach
     
       ``` JS
       const router = new VueRouter({ ... });
       router.beforeEach((to, from, next) => {
           // do someting
       });
       ```

       > next 方法必须要调用，否则钩子函数无法 resolved

       1. to: Route，代表要进入的目标，它是一个路由对象
       2. from: Route，代表当前正要离开的路由，同样也是一个路由对象
       3. next: Function，这是一个必须需要调用的方法，而具体的执行效果则依赖 next 方法调用的参数  
           next()：进入管道中的下一个钩子，如果全部的钩子执行完了，则导航的状态就是 confirmed（确认的）  
           next(false)：这代表中断掉当前的导航，即 to 代表的路由对象不会进入，被中断，此时该表 URL 地址会被重置到 from 路由对应的地址  
           next('/') 和 next({path: '/'})：在中断掉当前导航的同时，跳转到一个不同的地址  
           next(error)：如果传入参数是一个 Error 实例，那么导航被终止的同时会将错误传递给 router.onError() 注册过的回调

     2. 后置钩子：

       ``` js
       router.afterEach((to, from) => {
           // do someting
       });

       > 不同于前置守卫，后置钩子并没有 next 函数，也不会改变导航本身
        ```

    2. 路由独享的钩子：单个路由独享的导航钩子，它是在路由配置上直接进行定义的

- Vuex 状态管理