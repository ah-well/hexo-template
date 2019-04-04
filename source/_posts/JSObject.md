---
title: JS Object
date: 2019-04-04 11:36:07
tags:
---

- 在JavaScript的世界里万物皆对象
```js
typeof 123; // 'number'
typeof NaN; // 'number'
typeof 'str'; // 'string'
typeof true; // 'boolean'
typeof undefined; // 'undefined'
typeof Math.abs; // 'function'
typeof null; // 'object'
typeof []; // 'object'
typeof {}; // 'object'
```
  - 可见，number、string、boolean、function和undefined有别于其他类型。特别注意null的类型是object，Array的类型也是object，如果我们用typeof将无法区分出null、Array和通常意义上的object——{}。

- 注意一下几点
  - 不要使用new Number()、new Boolean()、new String()创建包装对象；
  - 用parseInt()或parseFloat()来转换任意类型到number；
  - 用String()来转换任意类型到string，或者直接调用某个对象的toString()方法；
  - 通常不必把任意类型转换为boolean再判断，因为可以直接写if (myVar) {...}；
  - typeof操作符可以判断出number、boolean、string、function和undefined；
  - 判断Array要使用Array.isArray(arr)；
  - 判断null请使用myVar === null；
  - 判断某个全局变量是否存在用typeof window.myVar === 'undefined'；
  - 函数内部判断某个变量是否存在用typeof myVar === 'undefined'。

- Date 里的月份是从0开始