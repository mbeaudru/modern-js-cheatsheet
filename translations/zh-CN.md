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

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/zh-CN/search?q=)
- [You don't know JS（书）](https://github.com/getify/You-Dont-Know-JS)
- [ES6 新特性和例子](http://es6-features.org)
- [WesBos 博客中 ES6 类别](http://wesbos.com/category/es6/)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) 可直接查找特定的博客和资源
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)

## 目录

- [Modern JavaScript Cheatsheet 简体中文版](#Modern-JavaScript-Cheatsheet-简体中文版)
  * [简介](#简介)
    + [初心](#初心)
    + [参考材料](#参考材料)
  * [目录](#目录)
  * [正文](#正文)
    + [变量声明: var, const, let](#变量声明-var-const-let)
      - [简述](#简述)
      - [代码示例](#代码示例)
      - [详述](#详述)
      - [延伸资料](#延伸资料)
    + [箭头函数](#箭头函数)
      - [简述](#简述-1)
      - [详述](#详述-1)
          * [简洁性](#简洁性)
          * [*this* 关键字](#this-关键字)
      - [相关资料](#相关资料)
    + [方法默认参数值](#方法默认参数值)

## 正文

### 变量声明： var, const, let

在 JavaScript 中，声明变量时可以用三个不同的关键词，分别是 `var`，`let` 以及 `const` ，它们各有异同。

#### 简述

用 `const` 声明的变量，不能被重新赋值，而另两个 `var` 和 `let` 是可以的。

所以我建议默认情况下你都用 `const` 来声明变量，在你需要 *改变* 或是声明之后再重新指派它的时候，才用 `let` 来声明变量。


| -     | 作用域  | 是否可重新赋值 | 是否可变                       | [暂存死区](#tdz_sample) |
| ----- | ---- | ------- | -------------------------- | ------------------- |
| const | 块级   | ×       | [√](#const_mutable_sample) | √                   |
| let   | 块级   | √       | √                          | √                   |
| var   | 函数   | √       | √                          | ×                   |

#### 代码示例

```javascript
const person = "Nick";
person = "John" // 因为 person 不能被重新赋值，所以会报错
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", 使用 let 声明的变量可以重新赋值
```

#### 详述

简单来讲，变量的作用域（[*scope*](#scope_def)）是指“在这部分代码中可以访问到此变量”。

##### var

使用 `var` 定义的变量，其作用域是定义它的函数内部（*function scoped*），也就是说在函数内部创建一个 `var` 变量的时候，在此函数内部可以任意访问这个变量，但在函数之外，这样的局部变量是无法被访问的。

我建议你这样理解，如果一个变量是 *X 作用域（scoped）* 类型的，那就是说这个变量是 X 的属性之一。（译注：X 有 function 和 block 两类，代表函数作用域和块级作用域。）

```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - 在这个函数中 myVar 可被访问到
}
console.log(myVar); // 抛出错误 ReferenceError, 在函数之外 myVar 则无法访问
```

继续来看变量的作用域，下面有更多精妙的例子：

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // 实际上 myVar 是函数级作用域变量，重新声明的时候，相当于用 "John" 抹去了 myVar 之前的值 "Nick"
  }
  console.log(myVar); // "John" - 可见 if 块中的代码会如何影响变量
}
console.log(myVar); // 抛出错误 ReferenceError, 在函数之外 myVar 则无法访问
```

另外，*var* 声明的变量在执行的时候，就像会被移动到作用域的开始，这就是我们所说的[变量声明提升（var hoisting)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/**var)。

所以看下面这段代码：

```javascript
console.log(myVar) // undefined -- 没有提示错误
var myVar = 2;
```

之所以没有发生错误，是因为它执行时会被解释为这样：

```javascript
var myVar;
console.log(myVar) // undefined -- 没有提示错误
myVar = 2;
```

##### let

`var` 和 `let` 几乎是一样的，但是用 `let` 声明的变量有如下特性：

- *块级作用域*（ block scoped )
- 在被赋值之前，是**无法**访问使用的
- 在同一个作用域之下，不能被重新声明

我们来看看之前例子中提到的块级作用域（ block scoping ）的效果：

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // 实际上 myVar 是块级作用域的变量，在 if 块中，我们相当于是创建了一个新变量，
    // 这个变量在此块之外是无法被访问的，而且它完全区别于我们创建的第一个 myVar 变量！
  }
  console.log(myVar); // "Nick", 可见 if 块中的代码，并没有影响到这个变量的值
}
console.log(myVar); // 抛出错误 ReferenceError，在函数外部无法访问到 myVar。
```

<a name="tdz_sample"></a>现在，来看看 *let*（和 *const* ）声明的变量在赋值前无法访问是什么意思：

```javascript
console.log(myVar) // 提示错误 ReferenceError !
let myVar = 2;
```

这就是它们和 *var* 变量的区别，如果你在还未赋值给 *let* 或者 *const* 变量之前，就想读写它，是会提示错误的。这种情况常被称作暂存死区（[*Temporal dead zone*](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let#let_的暂存死区与错误)）或者 *TDZ*。

> **注意：** 从技术上讲，*let* 和 *const* 变量声明时也存在提升，但并不代表它们的赋值也会被提升。但由于它被设计成了赋值之前无法使用，所以我们直观感觉上它没有被提升，但其实是存在提升的。如果想了解更多细节，请看[这篇文章](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)。


另外，在同一作用域内你不能重新声明一个 *let* 变量。

```js
let myVar = 2;
let myVar = 3; // 提示语法错误 SyntaxError
```

##### const

`const` 声明的变量很像 `let`，但它不能被重新赋值。

总结一下 `const` 变量的特点如下：

- *块级作用域*
- 赋值之前无法使用
- 在同一个作用域内部，你不能重新声明一个变量
- 不能被重新指派

```Javascript
const myVar = "Nick";
myVar = "John" // 提示错误，不允许重新赋值 const 变量
```

<a name="const_mutable_sample"></a>但这里有一个小细节：`const` 变量并非完全[不可变](#mutation_def)，如果这个变量是 `object` 和 `array` 类型的值，那它的值是**可以改变**的。assign

对于对象类型来说：

```js
const person = {
  name: 'Nick'
};
person.name = 'John' // 这会生效的！person 并非完全重新指派（ reassigned ），只是值变化了（ mutated ）
console.log(person.name) // "John"
person = "Sandra" // 提示错误，因为用 const 声明的变量不能被重新指派
```

对于数组类型来说：

```js
const person = [];
person.push('John'); // 这也会生效！person 并非完全重新指派（ reassigned ），只是值变化了（ mutated ）
console.log(person[0]) // "John"
person = ["Nick"] // 提示错误，因为用 const 声明的变量不能被重新指派
```

#### 延伸资料

- [How let and const are scoped in JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Temporal Dead Zone (TDZ) Demystified](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="arrow_func_concept"></a> 箭头函数

ES6 JS 的最新版本已经介绍了*箭头函数*， 箭头函数是以另一种方式声明和使用函数。以下是箭头函数带来的一些好处：

- 更加简洁
- 从上下文获取*this*
- 隐式的返回方式

#### 简述

- 简洁性和隐式的返回方式

```js
function double(x) { return x * 2; } // 传统函数声明方式
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // 同样的函数，使用具有隐式返回方式的箭头函数来表示
console.log(double(2)) // 4
```
- *this* 关键字

在箭头函数中， *this*的值就等于函数所处的封闭的可执行上下文的*this*。简单来说，就是在箭头函数中，当你调用一个位于函数体内部的函数时，在内部函数中，你不需要使用"that = this" 这样的声明语句。

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### 详述

##### 简洁性

箭头函数从很多方面都比传统的函数简洁。案例如下：

- 隐式返回 VS 显式返回

**显式返回** 指的是函数的返回语句使用了return 关键字

```js
  function double(x) {
    return x * 2; // 使用了*return*关键字，显式返回 x * 2
  }
```

传统函数总是伴随着显式返回。使用箭头函数，你可以使用*隐式返回*，即不需要在函数体内使用return关键字就可以返回值。

隐式返回需要将所需代码写在一条语句中。

```js
  const double = (x) => {
    return x * 2; // 显式返回
  }
```

鉴于只返回单值，我们可以使用隐式返回。

```js
  const double = (x) => x * 2;
```

为实现隐式返回，我们只需要 **移除花括号** 和 **return** 关键字。之所以被称为*隐式*返回，是因为*return*关键字不存在的情况下，函数仍可返回 ```x * 2```。

> **注意:** 如果你的函数不是返回一个单值（伴有*连带值*），那么既不可以使用显式返回也不可以使用隐式返回。

除此之外， 如果你想隐式返回一个*object* 则必须使用圆括号对其修饰， 

```js
const getPerson = () => ({ name: "Nick", age: 24 })
console.log(getPerson()) // { name: "Nick", age: 24 } -- 箭头函数返回的对象
```

- 函数只有一个参数

如果你的箭头函数只有一个参数，你可以省略修饰参数的圆括号，重新观察上面的代码：

```js
  const double = (x) => x * 2; // 箭头函数只有一个参数
```

参数外面的圆括号可以省略:

```js
  const double = x => x * 2; // 箭头函数只有一个参数
```

- 函数无参数

当箭头函数无参数时，必须使用圆括号，否则会出现语法错误.

```js
  () => { // 必须提供圆括号
    const x = 2;
    return x;
  }
```

```js
  => { // 无圆括号，错误!
    const x = 2;
    return x;
  }
```

##### *this* 关键字

要理解箭头函数中this的微妙之处，你必须首先了解JavaScript中[this](#this_def) 的行为。

在箭头函数中， *this*的值就等于函数所处的封闭可执行上下文的*this*。这句话的意思就是箭头函数不创建一个新的*this*， 而是从其所处的上下文环境中获取。

没有箭头函数，如果你想要从*this*访问函数内部的函数中的一个变量，你必须使用*that = this*或者*self = this*这样的技巧。

例如, 使用位于myFunc内部的函数setTimeout:

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // that = this 
  setTimeout(
    function() { // 在函数的内部创建一个新的
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // 未定义 -- 请参照上面的函数this定义
    },
    0
  );
}
```

但是一旦使用箭头函数, *this* 将从包含这个箭头函数的上下文中获取:

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => { // 从上下文中获取this, 在这里就是 myFunc
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

#### 相关资料

- [Arrow functions introduction - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript arrow function - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

#### 方法默认参数值

从 ES2015 以后开始，你可以使用下面的语法，给你的方法参数来设置默认值

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- 没有值传入，所以默认的值10传给了myFunc
console.log(myFunc(5)) // 5 -- 一个值被传入，所以x等于5 
console.log(myFunc(undefined)) // 10 -- undefined 值提供了，所以默认值关联了x
console.log(myFunc(null)) // null -- 提供了 (null) , 见一下详细解释
```
默认参数有且只有在以下两种情况下才会生效：
- 没有参数提供的时候
- *undefined* 参数被提供的时候

换句话说，如果你传入*NULL* 默认值**将不会生效**
