# Modern JavaScript Cheatsheet 正體中文版

![Modern JavaScript cheatsheet](https://i.imgur.com/aexPxMb.png)
<small>圖片來源: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</small>

## 介紹

### 動機

本文檔整理了各種現代化 JavaScript 開發過程中經常使用到的腳本。

該份指南的目標並不是放在幫助初學者從零基礎到入門，而是為了幫助那些因為 Javascript 新式語法導致可能很難熟悉現代函數庫使用方式 (以 React 做為舉例) 的開發人員。

此外我也會偶爾提供一些個人主觀的建議和技巧，而這些建議可能會造成部分的爭議性，但請務必留意，當我做出這些舉例時這僅僅是出自於個人的推薦作法。

> **注意:** 此處介紹的大部分概念出自於 JavaScript 的語言更新 (ES2015，更多人稱其作 ES6)。你可以在[這個好地方](http://es6-features.org)找到更多添加的新功能。

### 配套資源

當你在試圖理解一個新概念時，我建議你可以去瀏覽以下這些資源尋找解答：

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/fr/search?q=)
- [You don't know JS (book)](https://github.com/getify/You-Dont-Know-JS)
- [ES6 Features with examples](http://es6-features.org)
- [WesBos blog (ES6)](http://wesbos.com/category/es6/)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) 搜尋特定相關主題的部落格文章和資源

## 目錄

- [Modern JavaScript cheatsheet 繁體中文版](#modern-javascript-cheatsheet)
  * [介紹](#introduction)
    + [動機](#motivation)
    + [配套資源](#complementary-resources)
  * [目錄](#table-of-contents)
  * [概念](#notions)
    + [變數聲明： var, const, let](#variable-declaration-var-const-let)
      - [簡短解釋](#short-explanation)
      - [範例程式碼](#sample-code)
      - [詳細說明](#detailed-explanation)
      - [外部資源](#external-resource)
    + [箭頭函數](#-arrow-function)
      - [範例程式碼](#sample-code-1)
      - [詳細說明](#detailed-explanation-1)
        * [簡潔性](#concision)
        * [*this* 關鍵字參照](#this-reference)
      - [有用資源](#useful-resources)
    + [函數預設值](#function-default-parameter-value)
      - [外部資源](#external-resource-1)
    + [objects 和 arrays 的解耦](#destructuring-objects-and-arrays)
      - [說明和範例程式碼](#explanation-with-sample-code)
      - [有用資源](#useful-resources-1)
    + [Array 的操作方法 - map / filter / reduce](#array-methods---map--filter--reduce)
      - [範例程式碼](#sample-code-2)
      - [說明](#explanation)
        * [Array.prototype.map()](#arrayprototypemap)
        * [Array.prototype.filter()](#arrayprototypefilter)
        * [Array.prototype.reduce()](#arrayprototypereduce)
      - [外部資源](#external-resource)
    + [展開運算子 "..."](#spread-operator-)
      - [範例程式碼](#sample-code-3)
      - [說明](#explanation-1)
        * [迭代用法 (如同 array)](#in-iterables-like-array)
        * [不定參數](#function-rest-parameter)
        * [Object 屬性擴展](#object-properties-spreading)
      - [外部資源](#external-resources)
    + [Object 屬性簡寫](#object-property-shorthand)
      - [說明](#explanation-2)
      - [外部資源](#external-resources-1)
    + [Promises](#promises)
      - [範例程式碼](#sample-code-4)
      - [說明](#explanation-3)
        * [創造 promise](#create-the-promise)
        * [使用 promise](#use-the-promise)
      - [外部資源](#external-resources)
    + [模板字符串](#template-literals)
      - [範例程式碼](#sample-code-5)
      - [外部資源](#external-resources-2)
    + [Imports / Exports](#imports--exports)
      - [說明與範例程式碼](#explanation-with-sample-code-1)
      - [外部字元](#external-resources-3)
    + [JavaScript *this*](#-javascript-this)
      - [外部資源](#external-resources-4)
    + [Class](#class)
      - [範例](#samples)
      - [外部資源](#external-resources-5)
    + [Async Await](#async-await)
      - [範例程式碼](#sample-code-6)
      - [說明](#explanation-4)
      - [外部資源](#external-resources-7)
  * [術語詞彙](#glossary)
    + [作用域範圍](#-scope)
    + [Variable mutation](#-variable-mutation)

## 概念

### 變數聲明： var, const, let

在 JavaScript 中有三個不同關鍵字可用於宣告一個變數，分別是 ```var```， ```let``` 和 ```const```。

#### 簡短解釋

使用 ```const``` 關鍵字宣告的變數無法被重新指派, 而 ```let``` 和 ```var``` 是可以的。

我會建議在默認情況下一律使用 ```const``` ，當你需要<i>改變</i>它或是稍後才重新指派時才使用 ```let``` 。

<table>
  <tr>
    <th></th>
    <th>作用域範圍</th>
    <th>是否可重新指派</th>
    <th>狀態變更</th>
   <th><a href="#tdz_sample">暫時性死區 (Temporal Dead Zone)</a></th>
  </tr>
  <tr>
    <th>const</th>
    <td>區塊</td>
    <td>不是</td>
    <td><a href="#const_mutable_sample">是</a></td>
    <td>是</td>
  </tr>
  <tr>
    <th>let</th>
    <td>區塊</td>
    <td>是</td>
    <td>是</td>
    <td>是</td>
  </tr>
   <tr>
    <th>var</th>
    <td>函數</td>
    <td>是</td>
    <td>是</td>
    <td>不是</td>
  </tr>
</table>

#### 範例程式碼

```javascript
const person = "Nick";
person = "John" // 會有錯誤跳出，person 不能被重新指派
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John" 在 let 的使用下允許被重新指派
```

#### 詳細說明

變數的 [*作用域範圍 (scope)*](#scope_def) 大致上意味著 "這個變數的效力可被作用在哪段程式碼 (where is this variable available in the code)"。

##### var

```var``` 宣告的變數是 *函數範圍 (function scoped)* 的，這表示當函數中創造變數的時候，該函數中的所有內容都可以訪問並使用該變數。相反的，在函數外創造的 *區塊範圍 (block scoped)* 變數則無法被使用。

我會建議你把它看作是一個 *X scoped* 範圍的變數代表著這個變數是 X 的屬性之一。

```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - myVar 可以在函數範圍之內被使用
}
console.log(myVar); // Undefined, myVar 在函數範圍外部無法被使用
```

持續觀察變數的作用域範圍，這裡有個更細微的範例：

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // actually, myVar 是函數範圍之內的，我們剛剛覆蓋了之前的 myVar 變數，值從 "Nick" 變成 "John"
  }
  console.log(myVar); // "John" - 印出來看看區塊如何影響 myVar 這個變數的值
}
console.log(myVar); // Undefined, myVar 在函數範圍外部無法被使用
```

此外， *var* 宣告出來的變數在程式執行之時就會被移到作用域的頂部。這個就是我們所說的[變數提升 (var hoisting)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting)。

這段程式碼：

```js
console.log(myVar) // undefined -- 沒有錯誤發生
var myVar = 2;
```

在程式執行過程中被解讀為：

```js
var myVar;
console.log(myVar) // undefined -- 沒有錯誤發生
myVar = 2;
```

##### let

```var``` 和 ```let ``` 大致上行為相同， ```let``` 在宣告變數時

- 作用域是 *區塊範圍 (block scoped)*
- 在被指派值以前 **無法** 被存取使用
- 同一個作用域之下不能被重新宣告

採用我們前面的例子來看看區塊範圍 (block scoped) 的影響：

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // 事實上，myVar 是區塊範圍之內的，我們剛剛創造了一個全新的 myVar 變數
    // 這個變數是無法從區塊範圍以外的地方存取，
    // 而且它也是完全獨立於我們創造的第一個 myVar 變數！
  }
  console.log(myVar); // "Nick", 查看 if 區塊中的程式會不會影響到 myVar 這個值
}
console.log(myVar); // Undefined, myVar 在函數範圍外部無法被使用
```

<a name="tdz_sample"></a> 現在我們來看看 *let* ( 和 *const* ) 變數在被賦值以前無法被使用是什麼意思：

```js
console.log(myVar) // 觸發 ReferenceError 錯誤!
let myVar = 2;
```

和 *var* 變數比較之下，如果在指派 *let* 或是 *const* 變數的值之前嘗試讀取或是寫入的動作是會引發錯誤的。這種現象通常被稱之為 [*Temporal dead zone*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_Dead_Zone_and_errors_with_let) 或者是 *TDZ*。

> **注意：** 技術上而言， *let* 和 *const* 變數在聲明時也是會被提升的，但並不是指它們的賦值。因為他們在被指派之前是不能使用的，所以直觀上就像是沒有提升一樣，但它們其實是有的。如果你想知道更多的話請查看 [更加詳細解釋的這篇文章](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)。

此外，你不能重新宣告一個 *let* 變數：

```js
let myVar = 2;
let myVar = 3; // 跳出 SyntaxError 錯誤
```

##### const

```const``` 宣告出來的行為如同 *let* 變數，但它們同樣都不能被重新指派。

總結一下， *const* 變數：

- 作用域是 *區塊範圍 (block scoped)*
- 在被指派值以前 **無法** 被存取使用
- 同一個作用域之下不能被重新宣告
- 無法被重新指派新值

```js
const myVar = "Nick";
myVar = "John" // 跳出錯誤，不允許重新指派新值
```

```js
const myVar = "Nick";
const myVar = "John" // 跳出錯誤， 重新宣告是不被允許的
```

<a name="const_mutable_sample"></a> 但有個微妙之處 : ```const``` 變數是不 [**可變的**](#mutation_def) ! 更具體而言，這代表著 *object* 和 *array* 中由 ```const``` 宣告出來的變數是 **可以** 被改變的。

對於 objects：

```js
const person = {
  name: 'Nick'
};
person.name = 'John' // 這完全可行！ person 這個變數尚未完全被重新指派，但它確實改變了
console.log(person.name) // "John"
person = "Sandra" // 跳出錯誤，因為重新指派時是不允許使用 const 宣告出來的變數的
```

對於 arrays：

```js
const person = [];
person.push('John'); // 這完全可行！ person 這個變數尚未完全被重新指派，但它確實改變了 
console.log(person[0]) // "John"
person = ["Nick"] // 跳出錯誤，因為重新指派時是不允許使用 const 宣告出來的變數的
```

#### 外部資源

- [How let and const are scoped in JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Temporal Dead Zone (TDZ) Demystified](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="arrow_func_concept"></a> 箭頭函數

The ES6 JavaScript update has introduced *arrow functions*, which is another way to declare and use functions. Here are the benefits they bring:

- More concise
- *this* is picked up from surroundings
- implicit return

#### 範例程式碼

- Concision and implicit return

```js
function double(x) { return x * 2; } // Traditional way
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // Same function written as an arrow function with implicit return
console.log(double(2)) // 4
```

- *this* reference

In an arrow function, *this* is equal to the *this* value of the enclosing execution context. Basically, with arrow functions, you don't have to do the "that = this" trick before calling a function inside a function anymore.

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### Detailed explanation

##### Concision

Arrow functions are more concise than traditional functions in many ways. Let's review all the possible cases:

- Implicit VS Explicit return

An **explicit return** is a function where the *return* keyword is used in its body.

```js
  function double(x) {
    return x * 2; // this function explicitly returns x * 2, *return* keyword is used
  }
```

In the traditional way of writing functions, the return was always explicit. But with arrow functions, you can do *implicit return* which means that you don't need to use the keyword *return* to return a value.

To do an implicit return, the code must be written in a one-line sentence.

```js
  const double = (x) => {
    return x * 2; // Explicit return here
  }
```

Since there only is a return value here, we can do an implicit return.

```js
 const double = (x) => x * 2;
```

To do so, we only need to **remove the brackets** and the **return** keyword. That's why it's called an *implicit* return, the *return* keyword is not there, but this function will indeed return ```x * 2```.

> **Note:** If your function does not return a value (with *side effects*), it doesn't do an explicit nor an implicit return.

- Only one argument

If your function only takes one parameter, you can omit the parenthesis around it. If we take back the above *double* code:

```js
 const double = (x) => x * 2; // this arrow function only takes one parameter
```

Parenthesis around the parameter can be avoided:

```js
 const double = x => x * 2; // this arrow function only takes one parameter
```

- No arguments

When there is no argument provided to an arrow function, you need to provide parentheses, or it won't be valid syntax.

```js
  () => { // parenthesis are provided, everything is fine
    const x = 2;
    return x;
  }
```

```js
  => { // No parenthesis, this won't work!
    const x = 2;
    return x;
  }
```

##### *this* reference

To understand this subtlety introduced with arrow functions, you must know how [this](#this_def) behaves in JavaScript.

In an arrow function, *this* is equal to the *this* value of the enclosing execution context. What it means is that an arrow function doesn't create a new *this*, it grabs it from its surrounding instead.

Without arrow function, if you wanted to access a variable from *this* in a function inside a function, you had to use the *that = this* or *self = this* trick.

For instance, using setTimeout function inside myFunc:

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // that = this trick
  setTimeout(
    function() { // A new *this* is created in this function scope
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // undefined -- see function declaration above
    },
    0
  );
}
```

But with arrow function, *this* is taken from its surrounding:

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => { // this taken from surrounding, meaning myFunc here
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

#### Useful resources

- [Arrow functions introduction - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript arrow function - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

### Function default parameter value

Starting from ES2015 JavaScript update, you can set default value to your function parameters using the following syntax:

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- no value is provided so x default value 10 is assigned to x in myFunc
console.log(myFunc(5)) // 5 -- a value is provided so x is equal to 5 in myFunc

console.log(myFunc(undefined)) // 10 -- undefined value is provided so default value is assigned to x
console.log(myFunc(null)) // null -- a value (null) is provided, see below for more details
```

The default parameter is applied in two and only two situations:

- No parameter provided
- *undefined* parameter provided

In other words, if you pass in *null* the default parameter **won't be applied**.

> **Note:** Default value assignment can be used with destructured parameters as well (see next notion to see an example)

#### External resource

- [Default parameter value - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Default parameters - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

### Destructuring objects and arrays

*Destructuring* is a convenient way of creating new variables by extracting some values from data stored in objects or arrays.

To name a few use cases, *destructuring* can be used to destructure function parameters or *this.props* in React projects for instance.

#### Explanation with sample code

- Object

Let's consider the following object for all the samples:

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

Without destructuring

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

With destructuring, all in one line:

```js
const { firstName: first, age, city = "Paris" } = person; // That's it !

console.log(age) // 35 -- A new variable age is created and is equal to person.age
console.log(first) // "Nick" -- A new variable first is created and is equal to person.firstName
console.log(firstName) // Undefined -- person.firstName exists BUT the new variable created is named first
console.log(city) // "Paris" -- A new variable city is created and since person.city is undefined, city is equal to the default value provided "Paris".
```

**Note :** In ```const { age } = person;```, the brackets after *const* keyword are not used to declare an object nor a block but is the *destructuring* syntax.

- Function parameters

*Destructuring* is often used to destructure objects parameters in functions.

Without destructuring

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

In destructuring the object parameter *person*, we get a more concise function:

```js
function joinFirstLastName({ firstName, lastName }) { // we create firstName and lastName variables by destructuring person parameter
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

Destructuring is even more pleasant to use with [arrow functions](#arrow_func_concept):

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```

- Array

Lets consider the following array:

```js
const myArray = ["a", "b", "c"];
```

Without destructuring

```js
const x = myArray[0];
const y = myArray[1];
```

With destructuring

```js
const [x, y] = myArray; // That's it !

console.log(x) // "a"
console.log(y) // "b"
```

#### Useful resources

- [ES6 Features - Destructuring Assignment](http://es6-features.org/#ArrayMatching)
- [Destructuring Objects - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destructuring](http://exploringjs.com/es6/ch_destructuring.html)

### Array methods - map / filter / reduce

*Map*, *filter* and *reduce* are array methods that are coming from a programming paradigm named [*functional programming*](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0).

To sum it up:

- **Array.prototype.map()** takes an array, does something on its elements and returns an array with the transformed elements.
- **Array.prototype.filter()** takes an array, decides element by element if it should keep it or not and returns an array with the kept elements only
- **Array.prototype.reduce()** takes an array and aggregates the elements into a single value (which is returned)

I recommend to use them as much as possible in following the principles of functional programming because they are composable, concise and elegant.

With those three methods, you can avoid the use of *for* and *forEach* loops in most situations. When you are tempted to do a *for* loop, try to do it with *map*, *filter* and *reduce* composed. You might struggle to do it at first because it requires you to learn a new way of thinking, but once you've got it things gets easier.

#### Sample code

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
const doubledNumbers = numbers.map(n => n * 2); // [0, 2, 4, 6, 8, 10, 12]
const evenNumbers = numbers.filter(n => n % 2 === 0); // [0, 2, 4, 6]
const sum = numbers.reduce((prev, next) => prev + next, 0); // 21
```

Compute total grade sum for students above 10 by composing map, filter and reduce:

```js
const students = [
  { name: "Nick", grade: 10 },
  { name: "John", grade: 15 },
  { name: "Julia", grade: 19 },
  { name: "Nathalie", grade: 9 },
];

const aboveTenSum = students
  .map(student => student.grade) // we map the students array to an array of their grades
  .filter(grade => grade >= 10) // we filter the grades array to keep those above 10
  .reduce((prev, next) => prev + next, 0); // we sum all the grades above 10 one by one

console.log(aboveTenSum) // 44 -- 10 (Nick) + 15 (John) + 19 (Julia), Nathalie below 10 is ignored
```

#### Explanation

Let's consider the following array of numbers for our examples:

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
```

##### Array.prototype.map()

```js
const doubledNumbers = numbers.map(function(n) {
  return n * 2;
});
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

What's happening here? We are using .map on the *numbers* array, the map is iterating on each element of the array and passes it to our function. The goal of the function is to produce and return a new value from the one passed so that map can replace it.

Lets extract this function to make it more clear, just for this once:

```js
const doubleN = function(n) { return n * 2; };
const doubledNumbers = numbers.map(doubleN);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

```numbers.map(doubleN)``` produces ```[doubleN(0), doubleN(1), doubleN(2), doubleN(3), doubleN(4), doubleN(5), doubleN(6)]``` which is equal to ```[0, 2, 4, 6, 8, 10, 12]```.

> **Note:** If you do not need to return a new array and just want to do a loop that has side effects, you might just want to use a for / forEach loop instead of a map.

##### Array.prototype.filter()

```js
const evenNumbers = numbers.filter(function(n) {
  return n % 2 === 0; // true if "n" is par, false if "n" isn't
});
console.log(evenNumbers); // [0, 2, 4, 6]
```

We are using .filter on the *numbers* array, filter is iterating on each element of the array and passes it to our function. The goal of the function is to return a boolean that will determine whether the current value will be kept or not. Filter then returns the array with only the kept values.

##### Array.prototype.reduce()

The reduce method goal is to *reduce* all elements of the array it iterates on into a single value. How it aggregates those elements is up to you.

```js
const sum = numbers.reduce(
  function(acc, n) {
    return acc + n;
  },
  0 // accumulator variable value at first iteration step
);

console.log(sum) //21
```

Just like for .map and .filter methods, .reduce is applied on an array and takes a function as the first parameter.

This time though, there are changes:

- .reduce takes two parameters

The first parameter is a function that will be called at each iteration step.

The second parameter is the value of the accumulator variable (*acc* here) at the first iteration step (read next point to understand).

- Function parameters

The function you pass as the first parameter of .reduce takes two parameters. The first one (*acc* here) is the accumulator variable, whereas the second parameter (*n*) is the current element.

The accumulator variable is equal to the return value of your function at the **previous** iteration step. At the first step of the iteration, *acc* is equal to the value you passed as .reduce second parameter.

###### At first iteration step

```acc = 0``` because we passed in 0 as the second parameter for reduce

```n = 0``` first element of the *number* array

Function returns *acc* + *n* --> 0 + 0 --> 0

###### At second iteration step

```acc = 0``` because its the value the function returned at the previous iteration step

```n = 1``` second element of the *number* array

Function returns *acc* + *n* --> 0 + 1 --> 1

###### At third iteration step

```acc = 1``` because its the value the function returned at the previous iteration step

```n = 2``` third element of the *number* array

Function returns *acc* + *n* --> 1 + 2 --> 3

###### At fourth iteration step

```acc = 3``` because it's the value the function returned at the previous iteration step

```n = 3``` fourth element of the *number* array

Function returns *acc* + *n* --> 3 + 3 --> 6

###### [...] At last iteration step

```acc = 15``` because it's the value the function returned at the previous iteration step

```n = 6``` last element of the *number* array

Function returns *acc* + *n* --> 15 + 6 --> 21

As it is the last iteration step, **.reduce** returns 21.

#### External Resource

- [Understanding map / filter / reduce in JS](https://hackernoon.com/understanding-map-filter-and-reduce-in-javascript-5df1c7eee464)

### Spread operator "..."

The spread operator ```...``` has been introduced with ES2015 and is used to expand elements of an iterable (like an array) into places where multiple elements can fit.

#### Sample code

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

```js
function myFunc(x, y, ...params) {
  console.log(x);
  console.log(y);
  console.log(params)
}

myFunc("a", "b", "c", "d", "e", "f")
// "a"
// "b"
// ["c", "d", "e", "f"]
```

```js
const { x, y, ...z } = { x: 1, y: 2, a: 3, b: 4 };
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }
```

#### Explanation

##### In iterables (like arrays)

If we have the two following arrays:

```js
const arr1 = ["a", "b", "c"];
const arr2 = [arr1, "d", "e", "f"]; // [["a", "b", "c"], "d", "e", "f"]
```

*arr2* the first element is an array because *arr1* is injected as is into *arr2*. But what we want is *arr2* to be an array of letters. To do so, we can *spread* the elements of *arr1* into *arr2*.

With spread operator

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

##### Function rest parameter

In function parameters, we can use the rest operator to inject parameters into an array we can loop in. There is already an **argument** object bound to every function that is equal to an array of all the parameters passed into the function.

```js
function myFunc() {
  for (var i = 0; i < arguments.length; i++) {
    console.log(arguments[i]);
  }
}

myFunc("Nick", "Anderson", 10, 12, 6);
// "Nick"
// "Anderson"
// 10
// 12
// 6
```

But let's say that we want this function to create a new student with its grades and with its average grade. Wouldn't it be more convenient to extract the first two parameters into two separate variables, and then have all the grades in an array we can iterate over?

That's exactly what the rest operator allows us to do!

```js
function createStudent(firstName, lastName, ...grades) {
  // firstName = "Nick"
  // lastName = "Anderson"
  // [10, 12, 6] -- "..." takes all other parameters passed and creates a "grades" array variable that contains them

  const avgGrade = grades.reduce((acc, curr) => acc + curr, 0) / grades.length; // computes average grade from grades

  return {
    firstName: firstName,
    lastName: lastName,
    grades: grades,
    avgGrade: avgGrade
  }
}

const student = createStudent("Nick", "Anderson", 10, 12, 6);
console.log(student);
// {
//   firstName: "Nick",
//   lastName: "Anderson",
//   grades: [10, 12, 6],
//   avgGrade: 9,33
// }
```

> **Note:** createStudent function is bad because we don't check if grades.length exists or is different from 0. But it's easier to read this way, so I didn't handle this case.

##### Object properties spreading

For this one, I recommend you read previous explanations about the rest operator on iterables and function parameters.

```js
const myObj = { x: 1, y: 2, a: 3, b: 4 };
const { x, y, ...z } = myObj; // object destructuring here
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

// z is the rest of the object destructured: myObj object minus x and y properties destructured

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }

// Here z object properties are spread into n
```

#### External resources

- [TC39 - Object rest/spread](https://github.com/tc39/proposal-object-rest-spread)
- [Spread operator introduction - WesBos](https://github.com/wesbos/es6-articles/blob/master/28%20-%20Spread%20Operator%20Introduction.md)
- [JavaScript & the spread operator](https://codeburst.io/javascript-the-spread-operator-a867a71668ca)
- [6 Great uses of the spread operator](https://davidwalsh.name/spread-operator)

### Object property shorthand

When assigning a variable to an object property, if the variable name is equal to the property name, you can do the following:

```js
const x = 10;
const myObj = { x };
console.log(myObj.x) // 10
```

#### Explanation

Usually (pre-ES2015) when you declare a new *object literal* and want to use variables as object properties values, you would write this kind of code:

```js
const x = 10;
const y = 20;

const myObj = {
  x: x, // assigning x variable value to myObj.x
  y: y // assigning y variable value to myObj.y
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```

As you can see, this is quite repetitive because the properties name of myObj are the same as the variable names you want to assign to those properties.

With ES2015, when the variable name is the same as the property name, you can do this shorthand:

```js
const x = 10;
const y = 20;

const myObj = {
  x,
  y
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```

#### External resources

- [Property shorthand - ES6 Features](http://es6-features.org/#PropertyShorthand)

### Promises

A promise is an object which can be returned synchronously from an asynchronous function ([ref](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261#3cd0)).

Promises can be used to avoid [callback hell](http://callbackhell.com/), and they are more and more frequently encountered in modern JavaScript projects.

#### Sample code

```js
const fetchingPosts = new Promise((res, rej) => {
  $.get("/posts")
    .done(posts => res(posts))
    .fail(err => rej(err));
});

fetchingPosts
  .then(posts => console.log(posts))
  .catch(err => console.log(err));
```

#### Explanation

When you do an *Ajax request* the response is not synchronous because you want a resource that takes some time to come. It even may never come if the resource you have requested is unavailable for some reason (404).

To handle that kind of situations, ES2015 has given us *promises*. Promises can have three different states:

- Pending
- Fulfilled
- Rejected

Let's say we want to use promises to handle an Ajax request to fetch the resource X.

##### Create the promise

We firstly are going to create a promise. We will use the jQuery get method to do our Ajax request to X.

```js
const xFetcherPromise = new Promise( // Create promise using "new" keyword and store it into a variable
  function(resolve, reject) { // Promise constructor takes a function parameter which has resolve and reject parameters itself
    $.get("X") // Launch the Ajax request
      .done(function(X) { // Once the request is done...
        resolve(X); // ... resolve the promise with the X value as parameter
      })
      .fail(function(error) { // If the request has failed...
        reject(error); // ... reject the promise with the error as parameter
      });
  }
)
```

As seen in the above sample, the Promise object takes a function which takes two parameters **resolve** and **reject**. Those parameters are functions which when called are going to move the promise *pending* state to respectively a *fulfilled* and *rejected* state.

But at the moment, the promise has not been used but only has been declared and stored into *xFetcherPromise* variable! So it doesn't have a current state.

##### Use the promise

To use the promise, we do the following:

```js
xFetcherPromise
  .then(function(X) {
    console.log(X);
  })
  .catch(function(err) {
    console.log(err)
  })
```

```.then``` is a method that once called will put the xFetcherPromise in **pending** state. When called, the promise body runs, and in this case, an Ajax call is being done.

If it succeeds, *resolve* is called and the function passed as ```.then``` parameter is executed.

If it fails, *reject* is called and the function passed as ```.catch``` parameter is executed.

#### External Resources

- [JavaScript Promises for dummies - Jecelyn Yeen](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [JavaScript Promise API - David Walsh](https://davidwalsh.name/promises)
- [Using promises - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [What is a promise - Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- [JavaScript Promises: an Introduction - Jake Archibald](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
- [Promise documentation - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

### Template literals

Template literals is an [*expression interpolation*](https://en.wikipedia.org/wiki/String_interpolation) for single and multiple-line strings.

In other words, it is a new string syntax in which you can conveniently use any JavaScript expressions (variables for instance).

#### Sample code

```js
const name = "Nick";
`Hello ${name}, the following expression is equal to four : ${2+2}`;

// Hello Nick, the following expression is equal to four: 4
```

#### External resources

- [String interpolation - ES6 Features](http://es6-features.org/#StringInterpolation)
- [ES6 Template Strings - Addy Osmani](https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

### Imports / Exports

ES6 modules are used to access variables or functions in a module explicitly exported by the modules it imports.

I highly recommend to take a look at MDN resources on import/export (see external resources below), it is both straightforward and complete.

#### Explanation with sample code

- Named exports

Named exports are used to export several values from a module. You can only name-export variables (not functions or class), so if you want to name-export a function, you have to store it in a variable before.

```js
// mathConstants.js
export const pi = 3.14;
export const exp = 2.7;
export const alpha = 0.35;

// -------------

// myFile.js
import { pi, exp } from './mathConstants.js'; // Destructuring import
console.log(pi) // 3.14
console.log(exp) // 2.7

// -------------

// mySecondFile.js
import * as constants from './mathConstants.js'; // Inject all exported values into constants variable
console.log(constants.pi) // 3.14
console.log(constants.exp) // 2.7
```

- Default import / export

Concerning the default export, there is only a single default export per module. A default export can be a function, a class, an object or anything else. This value is considered the "main" exported value since it will be the simplest to import. [Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description)

```js
// coolNumber.js
const ultimateNumber = 42;
export default ultimateNumber;

// ------------

// myFile.js
import number from './coolNumber.js';
// Default export, independently from its name, is automatically injected into number variable;
console.log(number) // 42
```

Function exporting:

```js
// sum.js
export default function sum(x, y) {
  return x + y;
}
// -------------

// myFile.js
import sum from './sum.js';
const result = sum(1, 2);
console.log(result) // 3
```

#### External resources

- [Export - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
- [Import - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Understanding ES6 Modules](https://www.sitepoint.com/understanding-es6-modules/)
- [Modules in JavaScript](http://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript)

### <a name="this_def"></a> JavaScript *this*

*this* operator behaves differently than in other languages and is in most cases determined by how a function is called. ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)).

This notion is having many subtleties and being quite hard, I highly suggest you to deep dive in the external resources below. Thus, I will provide what I personally have in mind to determine what *this* is equal to. I have learned this tip from [this article written by Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/).

```js
function myFunc() {
  ...
}

// After each statement, you find the value of *this* in myFunc

myFunc.call("myString", "hello") // "myString" -- first .call parameter value is injected into *this*

// In non-strict-mode
myFunc("hello") // window -- myFunc() is syntax sugar for myFunc.call(window, "hello")

// In strict-mode
myFunc("hello") // undefined -- myFunc() is syntax sugar for myFunc.call(undefined, "hello")
```

```js
var person = {
  myFunc: function() { ... }
}

person.myFunc.call(person, "test") // person Object -- first call parameter is injected into *this*
person.myFunc("test") // person Object -- person.myFunc() is syntax sugar for person.myFunc.call(person, "test")

var myBoundFunc = person.myFunc.bind("hello") // Creates a new function in which we inject "hello" in *this* value
person.myFunc("test") // person Object -- The bind method has no effect on the original method
myBoundFunc("test") // "hello" -- myBoundFunc is person.myFunc with "hello" bound to *this*
```

#### External resources

- [Understanding JavaScript Function Invocation and "this" - Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)
- [JavaScript this - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

### Class

JavaScript is a [prototype-based](https://en.wikipedia.org/wiki/Prototype-based_programming) language (whereas Java is [class-based](https://en.wikipedia.org/wiki/Class-based_programming) language, for instance). ES6 has introduced JavaScript classes which are meant to be a syntactic sugar for prototype-based inheritance and **not** a new class-based inheritance model ([ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)).

The word *class* is indeed error prone if you are familiar with classes in other languages. If you do, avoid assuming how JavaScript classes work on this basis and consider it an entirely different notion.

Since this document is not an attempt to teach you the language from the ground up, I will believe you know what prototypes are and how they behave. But here are some links I found great to understand this notion:

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Inheritance and the prototype chain - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

#### Samples

Before ES6, prototype syntax:

```js
var Person = function(name, age) {
  this.name = name;
  this.age = age;
}
Person.prototype.stringSentence = function() {
  return "Hello, my name is " + this.name + " and I'm " + this.age;
}
```

With ES6 class syntax:

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  stringSentence() {
    return "Hello, my name is " + this.name + " and I'm " + this.age;
  }
}

const myPerson = new Person("Manu", 23);
console.log(myPerson.age) // 23
console.log(myPerson.stringSentence()) // "Hello, my name is Manu and I'm 23
```

#### 外部資源

For prototype understanding:

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Inheritance and the prototype chain - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

For classes understanding:

- [ES6 Classes in Depth - Nicolas Bevacqua](https://ponyfoo.com/articles/es6-classes-in-depth)
- [ES6 Features - Classes](http://es6-features.org/#ClassDefinition)
- [JavaScript Classes - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

### Async Await

In addition to [Promises](#promises), there is a new syntax you might encounter to handle asynchronous code named *async / await*.

The purpose of async/await functions is to simplify the behavior of using promises synchronously and to perform some behavior on a group of Promises. Just as Promises are similar to structured callbacks, async/await is similar to combining generators and promises. ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function))

> **Note :** You must understand what are promises and how they work before trying to understand async / await since they rely on it.

> **Note 2:** [*await* must be used in an *async* function](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9#f3f0), which means that you can't use await in the top level of our code since that is not inside an async function.

#### Explanation with sample code

*Async / Await* is built on promises but they allow a more imperative style of code.

An `await` expression causes `async` function to pause the execution, wait for promise to resolve, and then resume the execution once the value is resolved. Any `async` function returns the `Promise`, and will be resolved to returned value.

```js
async function getGithubUser(handle) { // async keyword allows usage of await in the function and means function returns a promise 
  try { // this is how errors are handled with async / await
    const url = `https://api.github.com/users/${handle}`;
    const response = await fetch(url); // "synchronously" waiting fetch promise to resolve before going to next line
    return response.json();
  } catch (err) {
    alert(err);
  }
}

getGithubUser('mbeaudru').then(user => console.log(user)); // logging user response - cannot use await syntax since this code isn't in async function
```

#### 外部資源

- [Async/Await - JavaScript.Info](https://javascript.info/async-await)
- [ES7 Async/Await](http://rossboucher.com/await/#/)
- [6 Reasons Why JavaScript’s Async/Await Blows Promises Away](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9)
- [JavaScript awaits](https://dev.to/kayis/javascript-awaits)
- [Using Async Await in Express with Node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)
- [Async Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)

## 術語詞彙

### <a name="scope_def"></a> 作用域範圍 (scope)

The context in which values and expressions are "visible," or can be referenced. If a variable or other expression is not "in the current scope," then it is unavailable for use.

資料來源： [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

### <a name="mutation_def"></a> Variable mutation

一個變數在被宣告之後發生初始值變化的過程。

```js
var myArray = [];
myArray.push("firstEl") // myArray 正在變化
```

如果變數不能被改變的話，我們會說這個變數是 *不可變的 (immutable)* 。

[查看 MDN Mutable 文章](https://developer.mozilla.org/en-US/docs/Glossary/Mutable) 了解更多詳細資料。
