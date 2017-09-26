# Modern JavaScript Cheatsheet 简体中文版

![Modern JavaScript cheatsheet](https://i.imgur.com/aexPxMb.png)
<small>Image Credits: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</small>

## 简介

### 初心

这份文档整理了在当前前端项目中经常需要查阅的内容，并给出了最新的代码示例。

你或许会因为不熟悉当前一些新的代码库（例如 React）所用到的 JavaScript 概念，而很难上手这些新框架。所以本文档的目的并非从零教你 JavaScript，而是帮助已经有一定编程基础的你。

除此之外，我（作者：[Manuel Beaudru](https://github.com/mbeaudru)）偶尔会写上一些我的小技巧，也会注意提示这只是我的个人提议。

> **注：** 这篇文档里提到的大多数概念来自于目前最新的 JavaScript（ES2015，即 ES6），你可以在[这里](http://es6-features.org)查看新增的特性，网站做得很棒。

### 参考材料

当你觉得有的概念不容易理解时，你可以在下面的链接里面寻找答案。

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/fr/search?q=)
- [You don't know JS（书）](https://github.com/getify/You-Dont-Know-JS)
- [ES6 新特性和例子](http://es6-features.org)
- [WesBos 博客中 ES6 类别](http://wesbos.com/category/es6/)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) 可直接查找特定的博客和资源

## 目录

- [Modern JavaScript cheatsheet 中文版](#modern-javascript-cheatsheet)
  * [简介](#introduction)
    + [初心](#motivation)
    + [参考材料](#complementary-resources)
  * [目录](#table-of-contents)
  * [概念](#notions)
    + [变量声明: var, const, let](#variable-declaration-var-const-let)
      - [简述](#short-explanation)
      - [Sample code](#sample-code)
      - [Detailed explanation](#detailed-explanation)
      - [External resource](#external-resource)

## 概念

### 变量声明： var, const, let

在 JavaScript 中，声明变量时可以用三个不同的关键词，分别是 ```var```，```let``` 以及 ```const``` ，它们各有异同。

#### 简述

用 ```const``` 声明的变量，不能被重新赋值，而另两个 ```var``` 和 ```let``` 是可以的。

所以我建议默认情况下你都用 ```const``` 来声明变量，在你需要 *改变* 或是声明之后再重新指派它的时候，才用 ```let``` 来声明变量。


| - | 作用域 | 是否可重新赋值 | 是否可变 | [暂存死区](#tdz_sample) |
|---|---|---|---|---|
| const | 块级 | × |  [√](#const_mutable_sample) |  √ |
| let | 块级 | √ | √ | √ |
| var | 函数 | √ | √ | × |

#### 代码

```javascript
const person = "Nick";
person = "John" // Will raise an error, person can't be reassigned
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", reassignment is allowed with let
```
