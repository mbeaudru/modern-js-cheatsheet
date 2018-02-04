<a name="#modern-javascript-cheatsheet"></a>
# Modern JavaScript Cheatsheet 繁體中文版

![Modern JavaScript cheatsheet](https://i.imgur.com/aexPxMb.png)
<small>圖片來源: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</small>

### 譯者的話
> 原標題：[mbeaudru/modern-js-cheatsheet](https://github.com/mbeaudru/modern-js-cheatsheet)
>
> 原作者：[BEAUDRU Manuel](https://github.com/mbeaudru)
> 
> 對於現代 JavaScript 開發而言，這篇文章整理了不少知識點，當作複習或是學習都很不錯。自己一直以來都是做為讀者的角色，很少主動為整個開源社群做些實際貢獻，這點一直感到蠻慚愧的，就像是 Sublime 是啟蒙你寫程式的第一個 editor，當你開始工作賺錢後卻遲遲不買 license 是類似的道理。趁著短暫的假日譯者盡可能的把翻譯做到盡善盡美，畢竟不是專業的，要做到信達雅的程度其實不太可能，但過程中確實查閱了不少相關資料，部分關鍵字因為怕超譯所以會在後頭括號保留原文。
>
> 另外也想藉著這回翻譯的經驗說點八股的，英文真的天殺的重要，能夠直接閱讀原文始終是最能理解原意的方式。整篇 cheatsheet 從意譯的角度出發，詞意有所疑問或是理解錯誤都煩請發個 Pull Request 謝謝。
>
> 2017/09/30 Update
>
> 昨天晚上收到簡體中文譯者的來信提醒，才發現原來 Issue 內早已有社群朋友 @BirkhoffLee 正在做繁體中文的翻譯 ([詳情可見此討論串](https://github.com/mbeaudru/modern-js-cheatsheet/issues/15))，真的很抱歉昨天才驚覺這件事，譯者在這裡推薦大家如果有空也可以多多瀏覽  @BirkhoffLee 翻譯過的 [機器學習動手玩](https://github.com/humphd/have-fun-with-machine-learning/blob/master/README_zh-tw.md) 以及相關專案，他也是位對於開源社群推廣非常積極的開發者。最後關於這份繁體中文文件，譯者會在這一兩天回顧下文件翻譯用詞有無需要調整的地方，確認過後便會 merge 回原作者的 repo，大概是醬。

<a name="introduction"></a>
## 介紹

<a name="motivation"></a>
### 動機

本文檔整理了各種現代化 JavaScript 開發過程中經常使用到的腳本。

該份指南的目標並不是放在幫助初學者從零基礎到入門，而是為了幫助那些因為 JavaScript 新式語法導致可能很難熟悉現代函數庫使用方式 (以 React 做為舉例) 的開發人員。

此外我也會偶爾提供一些個人主觀的建議和技巧，而這些建議可能會造成部分的爭議性，但請務必留意，當我做出這些舉例時這僅僅是出自於個人的推薦作法。

> **注意:** 此處介紹的大部分概念出自於 JavaScript 的語言更新 (ES2015，更多人稱其作 ES6)。你可以在[這個好地方](http://es6-features.org)找到更多添加的新功能。

<a name="complementary-resources"></a>
### 配套資源

當你在試圖理解一個新概念時，我建議你可以去瀏覽以下這些資源尋找解答：

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/fr/search?q=)
- [You don't know JS (book)](https://github.com/getify/You-Dont-Know-JS)
- [ES6 Features with examples](http://es6-features.org)
- [WesBos blog (ES6)](http://wesbos.com/category/es6/)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) 搜尋特定相關主題的部落格文章和資源

<a name="table-of-contents"></a>
## 目錄

- [Modern JavaScript cheatsheet 繁體中文版](#modern-javascript-cheatsheet)
  * [介紹](#introduction)
    + [動機](#motivation)
    + [配套資源](#complementary-resources)
  * [目錄](#table-of-contents)
  * [概念](#notions)
    + [變數聲明： var, const, let](#variable-declaration-var-const-let)
      - [簡短解釋](#short-explanation-1)
      - [範例程式碼](#sample-code-2)
      - [詳細說明](#detailed-explanation-3)
      - [外部資源](#external-resource-4)
    + [箭頭函數](#-arrow-function-4)
      - [範例程式碼](#sample-code-5)
      - [詳細說明](#detailed-explanation-6)
        * [簡潔性](#concision-7)
        * [*this* 關鍵字參照](#this-reference-8)
      - [有用資源](#useful-resources-9)
    + [函數預設值](#function-default-parameter-value-10)
      - [外部資源](#external-resource-11)
    + [objects 和 arrays 的解構](#destructuring-objects-and-arrays-12)
      - [說明和範例程式碼](#explanation-with-sample-code-13)
      - [有用資源](#useful-resources-14)
    + [Array 的操作方法 - map / filter / reduce](#array-methods---map--filter--reduce-15)
      - [範例程式碼](#sample-code-16)
      - [說明](#explanation-17)
        * [Array.prototype.map()](#arrayprototypemap-18)
        * [Array.prototype.filter()](#arrayprototypefilter-19)
        * [Array.prototype.reduce()](#arrayprototypereduce-20)
      - [外部資源](#external-resource-21)
    + [展開運算子 "..."](#spread-operator-22)
      - [範例程式碼](#sample-code-23)
      - [說明](#explanation-24)
        * [迭代用法 (如同 array)](#in-iterables-like-array-25)
        * [不定參數](#function-rest-parameter-26)
        * [Object 屬性擴展](#object-properties-spreading-27)
      - [外部資源](#external-resources-28)
    + [Object 屬性簡寫](#object-property-shorthand-29)
      - [說明](#explanation-30)
      - [外部資源](#external-resources-31)
    + [Promises](#promises-32)
      - [範例程式碼](#sample-code-33)
      - [說明](#explanation-34)
        * [創造 promise](#create-the-promise-35)
        * [使用 promise](#use-the-promise-36)
      - [外部資源](#external-resources-37)
    + [模板字符串](#template-literals-38)
      - [範例程式碼](#sample-code-39)
      - [外部資源](#external-resources-40)
    + [Imports / Exports](#imports--exports-41)
      - [說明與範例程式碼](#explanation-with-sample-code-42)
      - [外部資源](#external-resources-43)
    + [JavaScript *this*](#-javascript-this-44)
      - [外部資源](#external-resources-45)
    + [Class](#class-46)
      - [範例](#samples-47)
      - [外部資源](#external-resources-48)
    + [Async Await](#async-await-49)
      - [範例程式碼](#sample-code-50)
      - [說明](#explanation-51)
      - [外部資源](#external-resources-52)
  * [術語詞彙](#glossary-53)
    + [作用域範圍](#-scope-54)
    + [變數變異](#-variable-variance-55)

<a name="notions"></a>
## 概念

<a name="variable-declaration-var-const-let"></a>
### 變數聲明： var, const, let

在 JavaScript 中有三個不同關鍵字可用於宣告一個變數，分別是 ```var```， ```let``` 和 ```const```。

<a name="short-explanation-1"></a>
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

<a name="sample-code-2"></a>
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

<a name="detailed-explanation-3"></a>
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

```const``` 宣告出來的行為如同 *let* 變數，但它們同樣都不能被重新宣告。

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

<a name="const_mutable_sample"></a> 但有個精妙之處 : ```const``` 變數不是[**不可變的**](#mutation_def) ! 更具體而言，這代表著 *object* 和 *array* 中由 ```const``` 宣告出來的變數是 **可以** 被改變的。

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

<a name="external-resource-4"></a>
#### 外部資源

- [How let and const are scoped in JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Temporal Dead Zone (TDZ) Demystified](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="-arrow-function-4"></a> 箭頭函數

ES6 的更新正式引入了 *箭頭函數 (arrow functions)*，這是另外一種宣告和使用函數的方法。以下是它們所帶來的好處：

- 更為簡潔
- *this* 的值繼承自外圍作用域 (*this* is picked up from surroundings)
- 隱式回傳 (implicit return)

<a name="sample-code-5"></a>
#### 範例程式碼

- 簡潔性和隱式回傳 (implicit return)

```js
function double(x) { return x * 2; } // 傳統作法
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // 仍然是同樣的函數，寫成帶有隱式回傳的作法
console.log(double(2)) // 4
```

- *this* 關鍵字參照

在箭頭函數中， *this* 意味著封閉執行上下文的 *這個值*。基本上，透過使用箭頭函數，在函數中調用函數之前，你不需要去使用像是 "that = this" 這樣的用法。

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

<a name="detailed-explanation-6"></a>
#### 詳細說明

<a name="concision-7"></a>
##### 簡潔性

箭頭函數在諸多方面都較傳統函數來的更為簡潔。讓我們來看看所有可能的情況：

- 隱式回傳 VS 顯式回傳

 **顯式回傳 (explicit return)** 是指在函數中明確的使用 *return* 這個關鍵字。

```js
  function double(x) {
    return x * 2; // 這個函數顯式回傳了 x * 2，並且使用了 return 這個關鍵字
  }
```

以傳統的作法撰寫，return 永遠都會是顯式的。但是如果是使用箭頭函數，你可以執行隱式回傳，這同時代表著你不需要使用關鍵字 return 去取得回傳值。

要做隱式回傳，程式碼必須用一行句子撰寫。

```js
  const double = (x) => {
    return x * 2; // 此處顯示 return 值
  }
```

由於這裡只有一個回傳值，我們可以做一個隱式回傳。

```js
 const double = (x) => x * 2;
```

做到上述的轉換，我們只需要 **移除括號** 以及 **return** 這個關鍵字。這就是為什麼它會被稱為 *隱式* 回傳，*return* 關鍵字不在了，但是這個函數確實會回傳 ```x * 2```。

> **注意：** 如果你的函數沒有回傳一個值 (這種作法有 *副作用*)，那麼它將不屬於顯式或是隱式返回中的任一種。

- 只有一個參數

如果你的函數只接受一個參數，你可以省略它周圍的括號。如果我們拿上述的 *double* 程式碼做為舉例：

```js
 const double = (x) => x * 2; // 這個箭頭函數只接受一個參數
```

括號是可以被省略的：

```js
 const double = x => x * 2; // 這個箭頭函數只接受一個參數
```

- 沒有參數

當沒有為箭頭函數提供任何參數時，你就必須加上括號，否則語法將會出錯。

```js
  () => { // 有加上括號，一切都正常運作
    const x = 2;
    return x;
  }
```

```js
  => { // 沒有括號，這樣的語法是行不通的！
    const x = 2;
    return x;
  }
```

<a name="this-reference-8"></a>
##### *this* 關鍵字參照

要理解箭頭函數的精妙之處，你一定要清楚 [this](#this_def) 在 JavaScript 中是如何運作的。

在一個箭頭函數當中，*this* 等同於封閉執行上下文的 *這個值* 。意思就是說，一個箭頭函數並不會創造一個新的 *this*，而是從它的外圍作用域一併抓起。

沒有箭頭函數的這項功能，如果你想要取得位於函數的函數內部由 *this* 參照的變數，你就只能使用 *that = this* 或者是 *self = this* 這樣的技巧。

舉例來說，你在 myFunc 函數中使用 setTimeout 函數：

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // 使用 that = this 這個技巧
  setTimeout(
    function() { // 創造了一個新的 this 
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // undefined -- 詳見上述的函數宣告
    },
    0
  );
}
```

但如果你使用了箭頭函數，*this* 的範圍將會是它的外圍作用域：

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => { // this 的值來自於它的外圍作用域，也就是 myFunc 函數
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

<a name="useful-resources-9"></a>
#### 有用資源

- [Arrow functions introduction - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript arrow function - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

<a name="function-default-parameter-value-10"></a>
### 函數預設值

從 ES2015 JavaScript 更新之後，你可以透過下列的語法為函數中的參數設定預設值：

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- 沒有提供任何值，所以 10 在 myFunc 中做為預設值指派給 x
console.log(myFunc(5)) // 5 -- 有提供一個參數值，所以 x 在 myFunc 中等於 5   

console.log(myFunc(undefined)) // 10 -- 未定義的值，所以預設值被指派給 x
console.log(myFunc(null)) // null -- 提供一個值 (null)，詳細資料請見下文
```

預設值若且為若應用在兩種情況：

- 沒有傳入任何參數
- 傳入 *undefined* 這個參數

換句話說，如果你傳入的是 *null* ，那麼預設值的機制是不會被觸發的。

> **注意：** 預設值的指派可以搭配解構參數一同使用 (參照下一個概念的實際例子)

<a name="external-resource-11"></a>
#### 外部資源

- [Default parameter value - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Default parameters - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

<a name="destructuring-objects-and-arrays-12"></a>
### objects 和 arrays 的解構

*解構 (Destructuring)* 的概念是從 objects 或是 arrays 當中提取部分用值一種相當方便的方法。

舉個簡單的實例，*destructuring* 可以被用來解構函數中的參數或者像是 React 專案中 *this.props* 這樣的用法。

<a name="explanation-with-sample-code-13"></a>
#### 說明和範例程式碼

- Object

試著想想以下這個 object：

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

沒有解構的作法，你只能這樣做：

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

使用解構，你只需要一行：

```js
const { firstName: first, age, city = "Paris" } = person; // 這樣就搞定了！

console.log(age) // 35 -- 一個名為 age 的新變數被創建出來了，其值等同於 person.age
console.log(first) // "Nick" -- 一個名為 first 的新變數被創建出來了，其值等同於person.firstName
console.log(firstName) // ReferenceError -- person.firstName 雖然存在，但其值是存在名叫 first 的新變數
console.log(city) // "Paris" -- 一個名為 city 的新變數被創建出來了，同時因為 person.city 是未被定義的，所以 city 將等同於預設值也就是 "Paris"。
```

**注意：** 在 ```const { age } = person;```當中， *const* 後的括號並不是用來宣告 object 或者是區塊，僅僅是 *解構 (destructuring)* 的使用語法。

- 帶有參數的函數用法

*解構 (Destructuring)* 經常被用來解 objects 中的參數。

沒有解構的作法，你只能這樣做：

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

在解構 obejct 當中 *person* 這個參數時，我們可以得到一個更簡潔的函數：

```js
function joinFirstLastName({ firstName, lastName }) { 
  // 我們透過解構 person 分別創造了 firstName 和 lastName 這兩個變數
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

解構搭配[箭頭函數](#arrow_func_concept)使得開發過程更加愉快：

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```

- Array

讓我們來想想下列這個 array：

```js
const myArray = ["a", "b", "c"];
```

沒有解構的作法，你只能這樣做：

```js
const x = myArray[0];
const y = myArray[1];
```

使用解構的作法：

```js
const [x, y] = myArray; // 就是這麼簡單！

console.log(x) // "a"
console.log(y) // "b"
```

<a name="useful-resources-14"></a>
#### 有用資源

- [ES6 Features - Destructuring Assignment](http://es6-features.org/#ArrayMatching)
- [Destructuring Objects - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destructuring](http://exploringjs.com/es6/ch_destructuring.html)

<a name="array-methods---map--filter--reduce-1"></a>
### Array 的操作方法 - map / filter / reduce

*Map*，*filter* 和 *reduce* 都是 array 提供的方法，它們源自於 [*functional programming*](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0) 開發範式。

總結一下：

- **Array.prototype.map()** 接受一組 array，針對其中的元素進行某些操作和轉換的動作。
- **Array.prototype.filter()** 接受一組 array，依照元素本身決定是否保留，並且將會回傳一個僅含有保留元素的 array
- **Array.prototype.reduce()** 接受一組 array，將這些元素合併成一個值並回傳

我會建議在開發時盡可能的遵循函數式編程 (functional programming) 的原則，因為它們是可組合的，簡潔且優雅的。

透過這三種方法，你將可以避免在大多數情況下使用 *for* 和 *forEach*。當你想做一個 *for* 迴圈時，試著用 *map*，*filter* 和 *reduce* 組合看看。起初你可能會覺得窒礙難行，因為它需要你學習一種新的思維方式，但一旦你掌握它了，事情也將變得更加容易。

<a name="sample-code-16"></a>
#### 範例程式碼

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
const doubledNumbers = numbers.map(n => n * 2); // [0, 2, 4, 6, 8, 10, 12]
const evenNumbers = numbers.filter(n => n % 2 === 0); // [0, 2, 4, 6]
const sum = numbers.reduce((prev, next) => prev + next, 0); // 21
```

透過 map，filter 和 reduce 這幾種組合技去計算出學生成績 >= 10 的總和：

```js
const students = [
  { name: "Nick", grade: 10 },
  { name: "John", grade: 15 },
  { name: "Julia", grade: 19 },
  { name: "Nathalie", grade: 9 },
];

const aboveTenSum = students
  .map(student => student.grade) // map the students array to an array of their grades
  .filter(grade => grade >= 10) // we filter the grades array to keep those 10 or above
  .reduce((prev, next) => prev + next, 0); // we sum all the grades 10 or above one by one

console.log(aboveTenSum) // 44 -- 10 (Nick) + 15 (John) + 19 (Julia), Nathalie below 10 is ignored
```

<a name="explanation-17"></a>
#### 說明

讓我們來思考下列這個 array：

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
```

<a name="arrayprototypemap-18"></a>
##### Array.prototype.map()

```js
const doubledNumbers = numbers.map(function(n) {
  return n * 2;
});
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```
發生了什麼事？我們在 *numbers* 這個 array 中使用了 .map 方法，map 將會去迭代 array 中的每一個元素並且回傳給我們的函數。該函數的目標是生成並回傳一個新的值使得 map 可以替換掉原本的 array。

讓我們提取這個函數以便讓解釋更清楚：

```js
const doubleN = function(n) { return n * 2; };
const doubledNumbers = numbers.map(doubleN);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

```numbers.map(doubleN)``` 將會產生 ```[doubleN(0), doubleN(1), doubleN(2), doubleN(3), doubleN(4), doubleN(5), doubleN(6)]``` ，而它們分別等同於 ```[0, 2, 4, 6, 8, 10, 12]```。

> **注意：** 如果你不需要回傳一個新的 array 且只想實作一個帶有副作用的迴圈，使用 for / forEach 迴圈會更為符合你所需。

<a name="arrayprototypefilter-19"></a>
##### Array.prototype.filter()

```js
const evenNumbers = numbers.filter(function(n) {
  return n % 2 === 0; // true if "n" is par, false if "n" isn't
});
console.log(evenNumbers); // [0, 2, 4, 6]
```

我們在這個充滿 *numbers* 的 array 上使用 .filter 方法，過濾器將會遍歷當中的每一個元素並回傳給我們的函數。函數的目標是回傳一個布林值，它將會確定當前值是否被保留。過濾之後回傳的是一個僅保留所需值的 array。

<a name="arrayprototypereduce-20"></a>
##### Array.prototype.reduce()

reduce 方法的目標是將進行迭代的 array 中的所有元素 *減少* 到只留下單一值。計算這些元素的方式將取決於你的需求。

```js
const sum = numbers.reduce(
  function(acc, n) {
    return acc + n;
  },
  0 // 進行迭代計算的初始值
);

console.log(sum) //21
```

就像 .map 和 .filter 方法一樣， .reduce 方法被應用在 array 上並將函數做為第一個參數。


這次有些變化了：

- .reduce 接受兩個參數

第一個參數是在每個迭代步驟中調用的函數。

第二個參數是在第一個迭代步驟（讀取下一個之用）的累加器變數的值（此處是 *acc*）。

- 帶有參數的函數用法

做為 .reduce 的第一個參數所傳遞的函數需要兩個參數。第一個（此處是 *acc*）是累加器變數，而第二個參數（*n*）則是當前元素。

累加器變數的值等於 **上一次** 迭代步驟中函數的回傳值。在迭代過程的第一步，*acc* 等於你做為 .reduce 時第二個參數所傳遞的值。

###### 進行第一次迭代

```acc = 0``` 因為我們把 0 做為 reduce 的第二個參數

```n = 0```  *number* array 的第一個元素

函數回傳 *acc* + *n* --> 0 + 0 --> 0

###### 進行第二次迭代

```acc = 0``` 因為它是上次迭代所回傳的值 

```n = 1``` *number* array 的第二個元素

函數回傳 *acc* + *n* --> 0 + 1 --> 1

###### 進行第三次迭代

```acc = 1``` 因為它是上次迭代所回傳的值 

```n = 2``` *number* array 的第三個元素

函數回傳 *acc* + *n* --> 1 + 2 --> 3

###### 進行第四次迭代

```acc = 3``` 因為它是上次迭代所回傳的值

```n = 3``` *number* array 的第四個元素

函數回傳 *acc* + *n* --> 3 + 3 --> 6

###### [...] 進行最後一次迭代

```acc = 15``` 因為它是上次迭代所回傳的值

```n = 6``` *number* array 的最後一個元素

函數回傳 *acc* + *n* --> 15 + 6 --> 21

因為它是最後一個迭代步驟了， **.reduce** 將回傳 21。

<a name="external-resource-21"></a>
#### 外部資源

- [Understanding map / filter / reduce in JS](https://hackernoon.com/understanding-map-filter-and-reduce-in-javascript-5df1c7eee464)

<a name="spread-operator-22"></a>
### 展開運算子 "..."

展開運算子 ```...``` 的語法在 ES2015 之下已經支援了，而它將會被用於把可迭代的元素 (像是 array) 擴展到容納更多元素。

<a name="sample-code-23"></a>
#### 範例程式碼

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

<a name="explanation-24"></a>
#### 說明

<a name="in-iterables-like-array-25"></a>
##### 迭代用法 (如同 array)

如果我們有以下兩個 arrays：

```js
const arr1 = ["a", "b", "c"];
const arr2 = [arr1, "d", "e", "f"]; // [["a", "b", "c"], "d", "e", "f"]
```

*arr2* 中的第一個元素是 array ，因為 *arr1* 是被注入到 *arr2* 之中的。但我們真正想要得到的 *arr2* 是一個純字母的 array。為了做到這點，我們可以將 *arr1* *擴展 (spread)* 到 *arr2*。

透過展開運算子

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

<a name="function-rest-parameter-26"></a>
##### 不定參數

在有著不定參數的函數當中，我們可以使用 rest 運算子將參數注入到我們可以進行迴圈操作的 array。這裡已經有一個名為 **arguments** 的 object 被綁定在函數上，等同於把 array 中的所有參數都傳遞給函數。

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

但是如果說我們希望創造的是一個包含他的各科成績和平均成績的新學生，提取前兩個參數 (firstName 和 lastName)並把剩下的元素迭代生成一個 array 的作法是否會更有效率呢？

這正是 rest 運算子允許我們做的事！

```js
function createStudent(firstName, lastName, ...grades) {
  // firstName = "Nick"
  // lastName = "Anderson"
  // [10, 12, 6] -- "..." 運算子會把 firstName 和 lastName 以外的參數傳入，同時創造一個包含這些元素，叫做 "grades" 的 array

  const avgGrade = grades.reduce((acc, curr) => acc + curr, 0) / grades.length; // 計算平均成績

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

> **注意：** createStudent 這個函數的舉例其實並不太好，因為我們並沒有去檢查 grades.length 是否存在又或者它根本等於 0。但是這個例子的確能夠幫助我們更為容易理解其中運作，所以我並沒有花額外的時間處理這個情況，請見諒。

<a name="object-properties-spreading-27"></a>
##### Object 屬性擴展

關於這點，我建議你去閱讀先前有關 rest 運算子，迭代運作和帶有不定參數的函數等相關說明。

```js
const myObj = { x: 1, y: 2, a: 3, b: 4 };
const { x, y, ...z } = myObj; // object 在此處被解構
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

// 解構後剩餘的部分都放在 z : 也就是 myObj 這個物件經過解構後鎖剩下的東西

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }

// 把 z 所包含的屬性擴展到 n 當中
```

<a name="external-resources-28"></a>
#### 外部資源

- [TC39 - Object rest/spread](https://github.com/tc39/proposal-object-rest-spread)
- [Spread operator introduction - WesBos](https://github.com/wesbos/es6-articles/blob/master/28%20-%20Spread%20Operator%20Introduction.md)
- [JavaScript & the spread operator](https://codeburst.io/javascript-the-spread-operator-a867a71668ca)
- [6 Great uses of the spread operator](https://davidwalsh.name/spread-operator)

<a name="object-property-shorthand-29"></a>
### Object 屬性簡寫

當我們想要把某個物件屬性指派給變數，如果變數名稱等同於屬性名稱，你可以試著執行以下操作：

```js
const x = 10;
const myObj = { x };
console.log(myObj.x) // 10
```

<a name="explanation-30"></a>
#### 說明

通常 (pre-ES2015) 當你宣告一個新的 *物件實體語法 (object literal)* 並且想要使用變數做為物件屬性的值時，你可能會寫出以下類似的程式碼：

```js
const x = 10;
const y = 20;

const myObj = {
  x: x, // 將變數 x 賦值給 myObj.x
  y: y // 將變數 y 賦值給 myObj.y
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```

你可以發現，這樣的作法其實相當繁瑣，因為 myObj 的屬性名和要指派給這些屬性的變數名稱都是相同的。

透過使用 ES2015，當變數名稱和屬性名稱相同時，你可以把程式碼這樣簡寫：

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

<a name="external-resources-31"></a>
#### 外部資源

- [Property shorthand - ES6 Features](http://es6-features.org/#PropertyShorthand)

<a name="promises-32"></a>
### Promises

promise 是一個可以從異步函數 ([參考](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261#3cd0)) 同步回傳的函數。

Promises 可以被用來避開 [回調地獄 (callback hell)](http://callbackhell.com/)，而且它們在現代 JavaScript 專案中也越來越常被使用到。

<a name="sample-code-33"></a>
#### 範例程式碼

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

<a name="explanation-34"></a>
#### 說明

當你在進行 *Ajax 請求* 時，回傳絕對是非同步的，因為資源請求需要時間。如果你要的資源由於某些原因 (404) 而不能使用，請求的資源可能永遠都不會出現。

為了處理這類情況，ES2015 為我們提供了 *promises*。Promises 可以有三種不同的狀態：

- 等待中 (Pending)
- 達成 (Fulfilled)
- 拒絕 (Rejected)

假設我們希望使用 promises 去進行 Ajax 請求以獲取 X 這項資源。

<a name="create-the-promise-35"></a>
##### 創造 promise

首先要創造一個 promise。我們將會使用 jQuery 的 get 方法去進行資源 X 的 Ajax 請求。

```js
const xFetcherPromise = new Promise( // 使用 "new" 這個關鍵字並把它存至一個變數
  function(resolve, reject) { // Promise 建構子需要一個有著 resolve 和 reject 這兩個參數的函數作為參數
    $.get("X") // 執行 Ajax 請求
      .done(function(X) { // 一旦請求完成...
        resolve(X); // ... 把 X 做為參數去 resolve promise
      })
      .fail(function(error) { // 如果請求失敗...
        reject(error); // ... 把 error 做為參數去 reject promise
      });
  }
)
```

如上所示，Promise 物件需要一個帶有兩個參數 ( **resolve** 以及 **reject** ) 的函數。這兩個參數會把 *pending* 狀態的 promise 分別進行 *fulfilled* 和 *rejected* 的處理。

但在此時此刻，promise 尚未被使用，它僅僅是被宣告並且儲存到 *xFetcherPromise* 這個變數當中！所以它並不存在當前的狀態。

<a name="use-the-promise-36"></a>
##### 使用 promise

為了使用 promise，我們可以進行以下的實作：

```js
xFetcherPromise
  .then(function(X) {
    console.log(X);
  })
  .catch(function(err) {
    console.log(err)
  })
```

```.then``` 是一種方法，一旦被調用將會把 xFetcherPromise 調整至 **pending** 狀態。當被調用時，promise 本體會運行，在這個範例當中，Ajax 請求正在進行中。

如果成功，將會調用 *resolve*，並且 ```.then``` 將會執行做為參數傳遞的函數。

如果失敗，將會調用 *reject*，並且 ```.catch``` 將會執行做為參數傳遞的函數。

<a name="external-resources-37"></a>
#### 外部資源

- [JavaScript Promises for dummies - Jecelyn Yeen](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [JavaScript Promise API - David Walsh](https://davidwalsh.name/promises)
- [Using promises - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [What is a promise - Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- [JavaScript Promises: an Introduction - Jake Archibald](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
- [Promise documentation - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

<a name="template-literals-38"></a>
### 模板字符串

模板字符串是一種單行和多行字符串的 [*表達式差值 (expression interpolation)*](https://en.wikipedia.org/wiki/String_interpolation)。

換句話說，它是一種新的字符串語法，你可以更方便地在 JavaScript 表達式中使用 (例如變數)。

<a name="sample-code-39"></a>
#### 範例程式碼

```js
const name = "Nick";
`Hello ${name}, the following expression is equal to four : ${2+2}`;

// Hello Nick, the following expression is equal to four: 4
```

<a name="external-resources-40"></a>
#### 外部資源

- [String interpolation - ES6 Features](http://es6-features.org/#StringInterpolation)
- [ES6 Template Strings - Addy Osmani](https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

<a name="imports--exports-41"></a>
### Imports / Exports

ES6 模組被用來存取顯式輸出 (explicitly export)的變數或是函數。

我強烈建議你去瀏覽 MDN 上有關 import/export (請參考下面的外部資源) 的文章，它們寫的既簡潔又完整。

<a name="explanation-with-sample-code-42"></a>
#### 說明與範例程式碼

- Named exports

Named exports 被用於從模組中輸出多個值的情況。你只能命名將要輸出的變數 (不能是函數或是類別)，所以當你想要輸出一個函數時，你必須先把它儲存在一個變數中。

```js
// mathConstants.js
export const pi = 3.14;
export const exp = 2.7;
export const alpha = 0.35;

// -------------

// myFile.js
import { pi, exp } from './mathConstants.js'; // 對 import 進行解構
console.log(pi) // 3.14
console.log(exp) // 2.7

// -------------

// mySecondFile.js
import * as constants from './mathConstants.js'; // 把所有的值輸出到 constants 這個變數
console.log(constants.pi) // 3.14
console.log(constants.exp) // 2.7
```

- 預設 import / export

關於輸出，每個模組在預設下只能有一個輸出。一個預設的輸出可以是函數，類別，物件又或者是任何東西。這個值被認為是 "主要的" 輸出值，因為它將會是最簡單純粹的輸出。[參考： MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description)

```js
// coolNumber.js
const ultimateNumber = 42;
export default ultimateNumber;

// ------------

// myFile.js
import number from './coolNumber.js';
// 預設輸出將獨立於其名稱， 將被自動注入到 number 這個變數;
console.log(number) // 42
```

函數輸出：

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

<a name="external-resources-43"></a>
#### 外部資源

- [Export - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
- [Import - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Understanding ES6 Modules](https://www.sitepoint.com/understanding-es6-modules/)
- [Modules in JavaScript](http://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript)

### <a name="-javascript-this-44"></a> JavaScript *this*

*this* 這個運算子的行為和其他語言是不太一樣的，在大多數情況之下是由函數的調用方式決定。([參考： MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)).

這個概念有很多精妙之處，並不是那麼容易理解，我強烈建議你好好研讀下面的外部資源。因此，我將會提供我個人對於 *this* 的一點理解和想法。我是從 [Yehuda Katz 寫的這篇文章](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/) 學到了這個技巧。

```js
function myFunc() {
  ...
}

// 在每個述句後頭，你都可以在 myFunc 中找到 this 的值

myFunc.call("myString", "hello") // "myString" -- 首先， .call 參數的值被注入到 this

// 非嚴格模式下
myFunc("hello") // window -- myFunc() 是 myFunc.call(window, "hello") 的語法糖

// 嚴格模式下
myFunc("hello") // undefined -- myFunc() 是 myFunc.call(undefined, "hello") 的語法糖
```

```js
var person = {
  myFunc: function() { ... }
}

person.myFunc.call(person, "test") // person 物件 -- 調用參數注入 this
person.myFunc("test") // person Object -- person.myFunc() 是 person.myFunc.call(person, "test") 的語法糖

var myBoundFunc = person.myFunc.bind("hello") // 創造了一個函數，並且把 "hello" 注入到 this
person.myFunc("test") // person Object -- 綁定方法對原有方法並無造成影響
myBoundFunc("test") // "hello" -- myBoundFunc 是把帶有 "hello" 的 person.myFunc 綁定到 this
```

<a name="external-resources-45"></a>
#### 外部資源

- [Understanding JavaScript Function Invocation and "this" - Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)
- [JavaScript this - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

<a name="class-46"></a>
### Class

JavaScript 是一個 [基於原型](https://en.wikipedia.org/wiki/Prototype-based_programming) 的語言 (然而 Java 是 [基於類別](https://en.wikipedia.org/wiki/Class-based_programming) 的語言)。 ES6 引入了 JavaScript 類別，它們是基於原型繼承的語法糖，而 **不是** 真正意義上基於類別的繼承模型。([參考](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)).


*類別 (class)* 一詞的確容易出錯，尤其是你同時也熟悉其他語言的情況下。如果真的有此困擾，請避免在這樣的認知下思考 JavaScript 的類別行為，並把它當作一個完全不同的新概念。

由於此份文件的目標不在於從頭教會你 JavaScript，我相信你早已知道什麼是原型，以及它們的行為模式。不過這裡還是有一些參考連結，以方便你去理解這些概念：

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Inheritance and the prototype chain - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

<a name="samples-47"></a>
#### 範例

ES6 之前的原型語法：

```js
var Person = function(name, age) {
  this.name = name;
  this.age = age;
}
Person.prototype.stringSentence = function() {
  return "Hello, my name is " + this.name + " and I'm " + this.age;
}
```

ES6 之後的類型語法：

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

<a name="external-resources-48"></a>
#### 外部資源

更好的理解原型：

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Inheritance and the prototype chain - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

更好的理解類別：

- [ES6 Classes in Depth - Nicolas Bevacqua](https://ponyfoo.com/articles/es6-classes-in-depth)
- [ES6 Features - Classes](http://es6-features.org/#ClassDefinition)
- [JavaScript Classes - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

<a name="async-await-49"></a>
### Async Await

除了 [Promises](#promises) 以外，還有一種新語法你可能會遇到，那就是被稱作非同步的 *async / await*。

async/await 的目的在於簡化同步使用 promise 的行為，並對一組 promise 執行一些處理。正如同Promises 類似於結構化之後的回調 (callback)，async/await 同樣類似於組合生成器 (combining generators) 和 promises。 ([參考： MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function))

> **注意：** 你必須先行了解到什麼是 promises 和它們是如何運作的，然後再去嘗試理解 async / await 的概念，因為後者是基於前者的進一步延伸。

> **注意：** [*await* must be used in an *async* function](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9#f3f0) 意味著你不能程式碼的頂部使用 await，因為它並不在異步函數之內。

<a name="sample-code-50"></a>
#### 說明與範例程式碼

*Async / Await* 是基於 promises 之上的新概念，但它們更允許你使用命令式風格 (imperative style)去撰寫程式。


`await` 表達式使 `async` 函數暫停執行，直到 promise 被成功解析才會繼續執行。任何 `async` 函數堆將回傳 `Promise`，並將其解析為回傳值。

```js
async function getGithubUser(handle) { // async 這個關鍵字允許在函數中使用 await，並且意味著函數將回傳一個 promise 
  try { // 這是 async / await 使用的方式
    const url = `https://api.github.com/users/${handle}`;
    const response = await fetch(url); // "同步" 等待 fetch 去解析 promise，然後才會跳轉到下一行
    return response.json();
  } catch (err) {
    alert(err);
  }
}

getGithubUser('mbeaudru').then(user => console.log(user)); // 印出 user 的值 - 不能使用 await 語法，因為此段程式碼並不在 async 函數當中
```

<a name="external-resources-52"></a>
#### 外部資源

- [Async/Await - JavaScript.Info](https://javascript.info/async-await)
- [ES7 Async/Await](http://rossboucher.com/await/#/)
- [6 Reasons Why JavaScript’s Async/Await Blows Promises Away](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9)
- [JavaScript awaits](https://dev.to/kayis/javascript-awaits)
- [Using Async Await in Express with Node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)
- [Async Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)

<a name="glossary-53"></a>
## 術語詞彙

### <a name="-scope-54"></a> 作用域範圍 (scope)

在上下文之中有著 "明顯可見的 (visible)" 值和表達式，又或者是可以被參照的。如果變數或是表達式並不在 "當前作用域和範圍"，那麼它將會是不能用的。

資料來源： [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

### <a name="-variable-variance-55"></a> 變數變異 (Variable mutation)

一個變數在被宣告之後發生初始值變化的過程。

```js
var myArray = [];
myArray.push("firstEl") // myArray 正在變化
```

如果變數不能被改變的話，我們會說這個變數是 *不可變的 (immutable)* 。

[查看 MDN Mutable 文章](https://developer.mozilla.org/en-US/docs/Glossary/Mutable) 了解更多詳細資料。
