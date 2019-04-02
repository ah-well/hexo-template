---
title: js basic
date: 2019-04-02 14:30:43
tags: js
---

## js 变量
### 分类
- Number（数字）
- String（字符串）
- Boolean（布尔）
- Symbol（符号）（第六版新增）
- Object（对象）- 一组由键-值组成的无序集合
  - Function（函数）(严格意义上也算Object)
  - Array（数组） 有序
  - Date（日期）
  - RegExp（正则表达式）
- Null（空）
- Undefined（未定义）

JavaScript 还有一种内置Error（错误）类型
### 数字
- JavaScript不区分整数和浮点数，统一用Number表示，以下都是合法的Number类型：
``` js
123;      // 整数123
0.456;    // 浮点数0.456
1.2345e3; // 科学计数法表示1.2345x1000，等同于1234.5
-99;      // 负数
NaN;      // NaN表示Not a Number，当无法计算结果时用NaN表示
Infinity; // 表示无限大，当数值超过了JavaScript的Number所能表示的最大值时，就表示为Infinity
```
- 0.1 + 0.2 = 0.30000000000000004

### 字符串
- JavaScript 中的字符串是一串Unicode 字符序列

### 布尔值
- 通过布尔运算计算出来的结果
- 
### undefined null
- JavaScript 允许声明变量但不对其赋值，一个未被赋值的变量就是 undefined 类型。还有一点需要说明的是，undefined 实际上是一个不允许修改的常量。
- null表示一个空值（non-value），必须使用null关键字才能访问
  
### strict模式
JavaScript在设计之初，为了方便初学者学习，并不强制要求用var申明变量。这个设计错误带来了严重的后果：如果一个变量没有通过var申明就被使用，那么该变量就自动被申明为全局变量：
``` js
i = 10; // i现在是全局变量
```

### 对象
- JavaScript用一个{...}表示一个对象，键值对以xxx: xxx形式申明，用,隔开。注意，最后一个键值对不需要在末尾加,，如果加了，有的浏览器（如低版本的IE）将报错。
- 访问属性是通过.操作符完成的，但这要求属性名必须是一个有效的变量名。如果属性名包含特殊字符，就必须用''括起来：
  ```js
  var xiaohong = {
    name: '小红',
    'middle-school': 'No.1 Middle School'
  };
   ```
  - xiaohong的属性名middle-school不是一个有效的变量，就需要用''括起来。访问这个属性也无法使用.操作符，必须用['xxx']来访问：
- 如果访问一个不存在的属性会返回什么呢？JavaScript规定，访问不存在的属性不报错，而是返回undefined：
- 由于JavaScript的对象是动态类型，你可以自由地给一个对象添加或删除属性：
- 如果我们要检测xiaoming是否拥有某一属性，可以用in操作符, 不过要小心，如果in判断一个属性存在，这个属性不一定是xiaoming的，它可能是xiaoming继承得到的：
  ```js
  var xiaoming = {
    name: '小明',
    birth: 1990,
    school: 'No.1 Middle School',
    height: 1.70,
    weight: 65,
    score: null
  };
  'name' in xiaoming; // true
  'grade' in xiaoming; // false

  'toString' in xiaoming; // true

  var xiaoming = {
    name: '小明'
  };
  xiaoming.hasOwnProperty('name'); // true
  xiaoming.hasOwnProperty('toString'); // false
  ```
- 因为toString定义在object对象中，而所有对象最终都会在原型链上指向object，所以xiaoming也拥有toString属性。

要判断一个属性是否是xiaoming自身拥有的，而不是继承得到的，可以用hasOwnProperty()方法：
  
### 声明变量关键字 let const var
- let 语句声明一个块级作用域的本地变量，并且可选的将其初始化为一个值。
- const 允许声明一个不可变的常量。这个常量在定义域内总是可见的。
- var 是最常见的声明变量的关键字。它没有其他两个关键字的种种限制。这是因为它是传统上在 JavaScript 声明变量的唯一方法。使用 var 声明的变量在它所声明的整个函数都是可见的。

> JavaScript 与其他语言的（如 Java）的重要区别是在 JavaScript 中语句块（blocks）是没有作用域的，只有函数有作用域。因此如果在一个复合语句中（如 if 控制结构中）使用 var 声明一个变量，那么它的作用域是整个函数（复合语句在函数中）。 但是从 ECMAScript Edition 6 开始将有所不同的， let 和 const 关键字允许你创建块作用域的变量。