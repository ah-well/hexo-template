---
title: something
date: 2019-04-03 14:21:38
tags:
---

### something else

- Any words I won't say to them, I only want to develop myself firstly.
- I am tired.And I have to keep sadness and grief away from me.
- Now I should read more technical books and practice more codes.
- Anything I won't think about all the day, just do it.
- I will keep myself learning something new, both technology and life.

- 怎么说吧，现阶段挺尴尬的，周围也尽是相似的风景，坚持自己的初心吧。
- 掘金url hash
- nodejs、混合app、
- flutter、
- 算法,聊天,面试,网络
  
- 网络是怎样连接的
- HTTP 权威指南
- JavaScript 面向对象精要
- 现代前端技术解析
- 深入理解 ES6
- ES6 标准入门
- 高性能的 JavaScript
- JavaScript 语言精粹
- 数据结构与算法 JavaScript 描述

``` text
前言
嗯ennnnnn，，，，懒癌症拖延的毛病，趁着最后一个上班日赶紧把最近一周的面试做个总结(虽然我下周一才入职)，作为一位去年才毕业的前端妹子来说，其实还是个技术小白啦，近几年还是想在技术上能有一个很大的提升，而且不是说金三银四嘛(嘤嘤嘤，好像是真的)，所以在试水了两家公司之后，开启了我一周左右的面经之路，大大小小的公司都有面，我就是奔着涨知识和积累经验去的！！！加起来差不多10家公司左右吧，成绩自己也还挺满意的，拿到了6家公司的offer，大小公司也都有，像大华、华三，但是最终综合考虑的结果，去了一家自己面试体验最好的公司，至少也是一家上市公司啦~

面试前需要注意的细节点
简历一定要写好，这个不用多说啦
先想清楚你辞职想去的下一家的初衷是什么，是加薪资、提升技术 or 换个工作环境。根据你自己的真实情况，投简历的时候针对性地看看公司的招聘要求，先看看符合度是多少，以免遇到要求极度不符合又没有在商量的前提下去面试了，最后的结果可能就是你还不错，但是不符合我们公司的要求。
准备工作要做好，我是因为才去年毕业啦，所以集中准备在基础知识和目前在用的VUE框架这两块啦，其他的知识点我平时在撸代码的时候都有在做笔记，所以都会扫一遍知识点，其他的你实际工作中没有用到的但是比较流行的也不能忽略哦，了解一下或者临时补一下，不要被问到没有听过有点尴尬的。面试完一家记得被面到不会的要做笔记做笔记！！！！就当做是学习吧，而且有时候真的受益匪浅~
规划好你自己的面试时间，提前要面试的公司做个简单的背景了解。我是一个比较想把时间集中在一起做的人，所以提完离职后专心面试，一天会安排2-3家面试，面试前看看你即将面试的公司规模大小背景简单地了解一下，公司的面试流程一般是笔试 or 电话面试 (可无) —> 技术面(1-2轮) —> HR面 。
面试知识点
在面两个大公司和一个小公司的时候，尤其是一个传统行业的大型公司时，也有可能是我年限的问题，尤其注意基础，无论是笔试还是技术主管面试的时候都集中在这块，像原生JS、原生Ajax等，，(这些虽然我在工作中用的也不是很多ennnn,原生的是用的不多，但是我自己很注重)，说下面试碰到的吧(一些记不住了，想起来我补上哈~)。

HTML以及CSS篇，集中在CSS
说下你常用的几种布局方式
集中往盒模型、flex布局说(至于grid布局，这个我看过没有用到过)
实现水平居中的几种方法？
animate和translate有没有用过，一些常见的属性说下？
CSS实现宽度自适应100%，宽高16:9的比例的矩形。
如何实现左边两栏一定比例，左栏高度随右栏高度自适应？
JavaScript篇(重要)
变量提升遇到的一些简单code题
说一下对闭包的理解，以及你在什么场景下会用到闭包？
说一下你对原型与原型链的了解度，有几种方式可以实现继承，用原型实现继承有什么缺点，怎么解决？
iframe的缺点有哪些？
Ajax的原生写法
为什么会有同源策略？
前端处理跨域有没有遇到过，处理跨域的方式有哪几种方式去解决
怎么判断两个对象是否相等
代码实现一个对象的深拷贝
从发送一个url地址到返回页面，中间发生了什么
说下工作中你做过的一些性能优化处理
ES6篇(引导篇，相对重要)
这块面试官主要是问你哪块用的比较多，你可以引导性地把面试官往你会的地方说

箭头函数中的this指向谁？
如何实现一个promise，promise的原理，以及它的两个参数是什么？
promise中第二个参数的reject中执行的方法和promise.catch()都是失败执行的，分别这么写有什么区别，什么情况下会两个都同时用到？
map和set有没有用过，如何实现一个数组去重，map数据结构有什么优点？
计算机网络篇(相对重要)
ennnnn,因为我专业是网络工程的，在华三和另一家公司面试的时候没有被少问这些问题

http、https、以及websocket的区别
http常见的状态码，400,401,403状态码分别代表什么？
协商缓存和强缓存的区别
说下计算机网络的相关协议？
浏览器兼容性问题
因为我的工作主要还在专注在web端，所以浏览器兼容性的问题没有少碰到过，因主要是兼容IE8以上以及其他各个浏览器，这个就当做总结一下吧(在被问到这一块的时候其实我是有加分的，因为回答的比较多2333)

使用meta标签来调节浏览器的渲染方式，告诉浏览器用哪种内核渲染，360双核浏览器就是在ie和chrome之间来回切换，现在使用meta标签来强制使用最新的内核渲染页面

<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
rgba不支持IE8
解决：用opacity
CSS3前缀

-webkit- webkit渲染引擎  chrome/safari
-moz gecko引擎    firefox
-ms- trident渲染引擎 IE
-o-    opeck渲染引擎 opera
过渡不兼容IE8，可以用JS动画实现
background-size不支持IE8，可以用img
使用PIE.htc让IE6/7/8支持CSS3部分属性，像CSS3的border-radius，box-shadow，css backgrounds(-pie-background),Gradients,RGBA属性

.border-radius {
border-radius: 10px;
-webkit-border-radius: 10px;
-moz-border-radius: 10px;
background: #abcdef;
behavior: url(css/PIE.htc);
 }
用css hack

IE6: _
IE7/7: *
IE7/Firefox: !important
IE7: *+
IE6/7/8: \9
IE8: \0
:IE浮动margin产生的双倍距离,通常使用float:left来实现，浏览器存在兼容性问题，导致图片与 后面的内容存在margin不一致的问题，解决方法就是给图片添加diaplay:inline即可

ie8不支持nth-child，但支持first-child和last-child，可以通过转化写法来处理问题，span:nth-child(2)可以转换为span:first-child+span,可以使ie8显示该内容，last-child可以自定义一个class类兼容ie8写法
IE8下不支持HTML5属性placeholder，解决问题的js插件挺多的，常用的使用jquery.JPlaceholder.js插件处理问题
识别HTML5元素，IE中可能无法识别nav/footer，使用html5shiv
火狐下表单阻止表单默认提交事件：在form中添加 action="javascript:",秒杀上述所有默认行为;
始终为按钮button添加type属性，IE下的默认类型是button，其他浏览器下的默认类型是submit
IE下删除所有不必要的console语句，IE下当遇到console时不识别之后报错，代码不会执行，或者全局自定义一个window.console方法
IE浏览器下由于参数过长导致通过GET请求下载文件方法报错，解决改为POST请求
IE浏览器下iframe弹窗中输入框光标丢失（无法输入）问题，解决清一下frame
兼容IE8 new Date()返回NaN问题，解决自定义方法

function parseISO8601(dateStringInRange) {
    var isoExp = /^\s*(\d{4})-(\d\d)-(\d\d)\s*$/,
        date = new Date(NaN), month,
        parts = isoExp.exec(dateStringInRange);

    if(parts) {
        month = +parts[2];
        date.setFullYear(parts[1], month - 1, parts[3]);
        if(month != date.getMonth() + 1) {
            date.setTime(NaN);
        }
    }
    return date;
}
Vue相关知识点 (框架之一重要)
因为我简历上主要写的是会vue啦，其实也不是精通，因为边学边开发，主要是实践的项目不是特别复杂，不过常见的一些坑点还是有遇到的啦，这个是看你会的框架问相应的知识点

简单阐述一下vue的生命周期
如何实现一个自定义组件，不同组件之间如何通信的？
父子组件如何通信的？
前端路由有没有用过，你在项目中怎么实现路由的嵌套？
nextTick和Vuex两个有没有用过，分为什么情况下用到？
Vue的响应式原理你知道是怎么实现的吗？你觉得订阅者-发布者模式和观察者模式有区别吗？有的话，说一下它们的区别。
构建工具
因为项目还在前后端未分离的时候，我研究的gulp比较多，像grunt、fis3也有了解过，webpack还不是很熟(感觉要GG)，所以这块问的比较少，面试官也就没有这么问，不过我觉得还是有必要去熟悉或者实践一下一下

Other
有一些技术主管会考量一下你除了前端之外的技术能力，例如你熟悉的后端语言，sql会不会，还有人问我Linux命令会不会的(我内心:不会不会不会====),不过node多多少少都有在用，这个也是前端应该要会的啦(but技术小白我不会，只是用到一点点~)

最后
把面试当做学习，这个过程你会收益很大。自己也拿到了几家还不错的offer，最后选择了我比较满意的一家公司，我并没有特别在意薪资这块，都是综合考虑的一个结果啦！前端知识很杂，可能实际工作中用到的技术，像框架都是跟着公司的要求走的，像我最近也在看React啦，Vue和React都对比着再学习，不要问我为什么没有在看Angular(懒懒懒),因为新公司说是偏向于React，所以最重要的还是更看重基础知识的积累吧，当然，开心最重要~
```