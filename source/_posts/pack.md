---
title: pack
date: 2019-05-15 14:38:51
tags:
---

### wepack

- webpack一些概念区别
  - bundle：是由webpack打包出来的文件
  - chunk：是指webpack在进行模块依赖分析的时候，代码分割出来的代码块
  - module：是开发中的单个模块
  
- webpack gulp比较
  - webpack是一个模块打包器，强调的是一个前端模块化方案，更侧重模块打包，我们可以把开发中的所有资源都看成是模块，通过loader和plugin对资源进行处理。
  - gulp是一个前端自动化构建工具，强调的是前端开发的工作流程，可以通过配置一系列的task，第一task处理的事情（如代码压缩，合并，编译以及浏览器实时更新等）。然后定义这些执行顺序，来让glup执行这些task，从而构建项目的整个开发流程。自动化构建工具并不能把所有的模块打包到一起，也不能构建不同模块之间的依赖关系。
  
- loader plugin
  - loader用于加载某些资源文件。因为webpack本身只能打包common.js规范的js文件，对于其他资源如css，img等，是没有办法加载的，这时就需要对应的loader将资源转化，从而进行加载。
  - plugin用于扩展webpack的功能。不同于loader，plugin的功能更加丰富，比如压缩打包，优化，不只局限于资源的加载。
  
- webpack-dev-server 和 http服务器的区别
  - webpack-dev-server使用内存来存储webpack开发环境下的打包文件，并且可以使用模块热更新，比传统的http服务对开发更加有效。
- devServer配置

    ``` js
    contentBase,  // 为文件提供本地服务器
    port,         // 监听端口，默认8080
    inline,       // 设置为true,源文件发生改变自动刷新页面
    historyApiFallback  // 依赖HTML5 history API,如果设置为true,所有的页面跳转指向index.html
    devServer:{
        contentBase: './src'         // 本地服务器所加载的页面所在的目录
        historyApiFallback: true,   // 不跳转
        inline: true                // 实时刷新
    }
    //然后我们在根目录下创建一个'webpack.config.js'，在'package.json'添加两个命令用于本地开发和生产发布
    "scripts": {
                "start": "webpack-dev-server",
                "build": "webpack"
    ```

---

### fis3

### gulp

