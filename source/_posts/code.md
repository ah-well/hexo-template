---
title: code
date: 2019-04-04 16:39:47
tags: 题目
---

- 函数式编程
  ```js
  ['2', '3', '4'].map(parseInt) // [2, NaN, NaN]
  ```
  - 因为 map 的算子是有两个参数的，第一个参数是被迭代数组的元素，第二个参数是该元素的下标。所以 ['2', '3', '4'].map(parseInt) 实际上相当于执行了 [parseInt('2', 0), parseInt('3', 1), parseInt('4', 2)]，结果就变成了 [2, NaN, NaN] 了。