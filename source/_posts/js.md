---
title: js basic
date: 2019-04-02 14:30:43
tags: js
---

## js 变量（大小写敏感）
### 分类
- Number（数字）
- String（字符串）
- Boolean（布尔）
- Symbol（符号）    （第六版新增）
- Object（对象）     - 由键-值组成的无序集合
  - Function（函数） (严格意义上也算Object)
  - Array（数组）    - 有序集合
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
- 由于JavaScript的对象是动态类型(这意味着相同的变量可用作不同的类型)，你可以自由地给一个对象添加或删除属性：
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

  // 声明空对象的两种方法
  var obj = new Object();
  var obj = {};
  ```
- 因为toString定义在object对象中，而所有对象最终都会在原型链上指向object，所以xiaoming也拥有toString属性。要判断一个属性是否是xiaoming自身拥有的，而不是继承得到的，可以用hasOwnProperty()方法
- 
  
### 声明变量关键字 let const var
- let 语句声明一个块级作用域的本地变量，并且可选的将其初始化为一个值。
- const 允许声明一个不可变的常量。这个常量在定义域内总是可见的。
- var 是最常见的声明变量的关键字。它没有其他两个关键字的种种限制。这是因为它是传统上在 JavaScript 声明变量的唯一方法。使用 var 声明的变量在它所声明的整个函数都是可见的。

> JavaScript 与其他语言的（如 Java）的重要区别是在 JavaScript 中语句块（blocks）是没有作用域的，只有函数有作用域。因此如果在一个复合语句中（如 if 控制结构中）使用 var 声明一个变量，那么它的作用域是整个函数（复合语句在函数中）。 但是从 ECMAScript Edition 6 开始将有所不同的， let 和 const 关键字允许你创建块作用域的变量。

### 声明变量类型
- 用new来声明。JavaScript 变量均为对象。当您声明一个变量时，就创建了一个新的对象。

### 数组
- Array.length 并不总是等于数组中元素的个数
  ```js
  var a = ["dog", "cat", "hen"];
  a[100] = "fox";
  a.length; // 101
  ```

## 控制结构
### 循环
- for
- for...of循环，ES2015 引入了更加简洁的，可以用它来遍历可迭代对象，例如数组：
  ```js
  for (const currentValue of a) {
    // Do something with currentValue
  }
  ```
- for...in  注意，如果有人向 Array.prototype 添加了新的属性，使用这样的循环这些属性也同样会被遍历。所以并不推荐使用这种方法遍历数组：
- forEach()
- while
- do...while
  
> do...while循环体会至少执行1次，而for和while循环则可能一次都不执行。


### 执行环境和作用域
- 执行环境（execution context，为简单起见，有时也称为“环境”）是 JavaScript 中最为重要的一个概念。执行环境定义了变量或函数有权访问的其他数据，决定了它们各自的行为。每个执行环境都有一个与之关联的变量对象（variable object），环境中定义的所有变量和函数都保存在这个对象中。虽然我们编写的代码无法访问这个对象，但解析器在处理数据时会在后台使用它。
- 全局执行环境是最外围的一个执行环境。根据 ECMAScript 实现所在的宿主环境不同，表示执行环境的对象也不一样。在 Web 浏览器中，全局执行环境被认为是 window 对象（第 7 章将详细讨论），因此所有全局变量和函数都是作为 window 对象的属性和方法创建的。某个执行环境中的所有代码执行完毕后，该环境被销毁，保存在其中的所有变量和函数定义也随之销毁（全局执行环境直到应用程序退出——例如关闭网页或浏览器——时才会被销毁）。
- 每个函数都有自己的执行环境。当执行流进入一个函数时，函数的环境就会被推入一个环境栈中。而在函数执行之后，栈将其环境弹出，把控制权返回给之前的执行环境。ECMAScript 程序中的执行流正是由这个方便的机制控制着。
- 当代码在一个环境中执行时，会创建变量对象的一个作用域链（scope chain）。作用域链的用途，是保证对执行环境有权访问的所有变量和函数的有序访问。作用域链的前端，始终都是当前执行的代码所在环境的变量对象。如果这个环境是函数，则将其活动对象（activation object）作为变量对象。活动对象在最开始时只包含一个变量，即 arguments 对象（这个对象在全局环境中是不存在的）。作用域链中的下一个变量对象来自包含（外部）环境，而再下一个变量对象则来自下一个包含环境。这样，一直延续到全局执行环境；全局执行环境的变量对象始终都是作用域链中的最后一个对象。
- 标识符解析是沿着作用域链一级一级地搜索标识符的过程。搜索过程始终从作用域链的前端开始，然后逐级地向后回溯，直至找到标识符为止（如果找不到标识符，通常会导致错误发生）。

- 函数参数也被当作变量来对待，因此其访问规则与执行环境中的其他变量相同。
---
P.S.本文部分内容参考了 [廖雪峰博客](https://www.liaoxuefeng.com) 、 [MDN Web docs](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)




