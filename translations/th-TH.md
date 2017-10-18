# Modern JavaScript Cheatsheet

![Modern JavaScript cheatsheet](https://i.imgur.com/aexPxMb.png)
<small>เครดิตรูปภาพ: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</small>

## คำนำ

### ที่มาที่ไป

This document is a cheatsheet for JavaScript you will frequently encounter in modern projects and most contemporary sample code.
เอกสารนี้เป็น cheatsheet สำหรับ JavaScript ที่เราน่าจะพบเจอบ่อยๆ ใน​โปรเจ็คใหม่ๆ หรือโค้ดตัวอย่างใหม่ๆ

This guide is not intended to teach you JavaScript from the ground up, but to help developers with basic knowledge who may struggle to get familiar with modern codebases (or let's say to learn React for instance) because of the JavaScript concepts used.
ซึ่งในบทความนี้จะไม่ได้สอน Javascript ตั้งแต่พื้นฐานให้ แต่จะช่วย Developer ที่มีพื้นฐานอยู่แล้วแต่ติดปัญหาได้เข้าใจและคุ้นเคยกับโค้ดหรือคอนเซปของ Javascript สมัยใหม่ (หรืออย่างเช่นว่ากำลังเรียนรู้ React แต่ไม่เข้าใจตัวโค้ด เป็นต้น)

Besides, I will sometimes provide personal tips that may be debatable but will take care to mention that it's a personal recommendation when I do so.
นอกจากนี้บทความนี้ได้มีแนะนำทิปส่วนตัวแนบไว้บางส่วนซึ่งสามารถมาดีเบทกันได้ ซึ่งส่วนไหนที่เป็นคำแนะนำส่วนตัวจะมีบอกเอาไว้

> **Note:** Most of the concepts introduced here are coming from a JavaScript language update (ES2015, often called ES6). You can find new features added by this update [here](http://es6-features.org); it's very well done.
> **หมายเหตุ:** คอนเซปส่วนใหญ่ในนี้จะมาจากอัปเดตใหม่ๆ ที่กำลังเป็นมาตรฐานของภาษา JavaScript (ES2015, หรือโดยทั่วไปเรียกว่า ES6). คุณสามารถดูฟีเจอร์ใหม่ๆ ที่เพิ่มเข้ามาโดยติดตามได้จากอัปเดต [ที่นี่](http://es6-features.org); ในนั้นได้มีครบทุกอย่าง

### แหล่งเรียนรู้เพิ่มเติม

ถ้าไม่เข้าใจหรือติดตรงไหน แนะนำให้ลองหาคำตอบจาก Link เหล่านี้ดูก่อน

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/search?q=)
- [You don't know JS (book)](https://github.com/getify/You-Dont-Know-JS)
- [ES6 Features with examples](http://es6-features.org)
- [WesBos blog (ES6)](http://wesbos.com/category/es6/)
- [Javascript Basics for Beginners](https://www.udacity.com/course/javascript-basics--ud804) - คอร์สฟรีจาก Udacity
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) to find specific blog and resources
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)

## สารบัญ

- [Modern JavaScript cheatsheet](#modern-javascript-cheatsheet)
  * [เกริ่นนำ](#introduction)
    + [ที่มาที่ไป](#motivation)
    + [แหล่งเรียนรู้เพิ่มเติม](#complementary-resources)
  * [สารบัญ](#table-of-contents)
  * [เนื้อหา](#notions)
    + [Variable declaration: var, const, let](#variable-declaration-var-const-let)
      - [Short explanation](#short-explanation)
      - [Sample code](#sample-code)
      - [Detailed explanation](#detailed-explanation)
      - [External resource](#external-resource)
    + [Arrow function](#-arrow-function)
      - [Sample code](#sample-code-1)
      - [Detailed explanation](#detailed-explanation-1)
        * [Concision](#concision)
        * [*this* reference](#this-reference)
      - [Useful resources](#useful-resources)
    + [Function default parameter value](#function-default-parameter-value)
      - [External resource](#external-resource-1)
    + [Destructuring objects and arrays](#destructuring-objects-and-arrays)
      - [Explanation with sample code](#explanation-with-sample-code)
      - [Useful resources](#useful-resources-1)
    + [Array methods - map / filter / reduce](#array-methods---map--filter--reduce)
      - [Sample code](#sample-code-2)
      - [Explanation](#explanation)
        * [Array.prototype.map()](#arrayprototypemap)
        * [Array.prototype.filter()](#arrayprototypefilter)
        * [Array.prototype.reduce()](#arrayprototypereduce)
      - [External Resource](#external-resource-2)
    + [Spread operator "..."](#spread-operator-)
      - [Sample code](#sample-code-3)
      - [Explanation](#explanation-1)
        * [In iterables (like arrays)](#in-iterables-like-arrays)
        * [Function rest parameter](#function-rest-parameter)
        * [Object properties spreading](#object-properties-spreading)
      - [External resources](#external-resources)
    + [Object property shorthand](#object-property-shorthand)
      - [Explanation](#explanation-2)
      - [External resources](#external-resources-1)
    + [Promises](#promises)
      - [Sample code](#sample-code-4)
      - [Explanation](#explanation-3)
        * [Create the promise](#create-the-promise)
        * [Promise handlers usage](#promise-handlers-usage)
      - [External Resources](#external-resources-2)
    + [Template literals](#template-literals)
      - [Sample code](#sample-code-5)
      - [External resources](#external-resources-3)
    + [Tagged Template Literals](#tagged-template-literals)
      - [External resources](#external-resources-4)
    + [Imports / Exports](#imports--exports)
      - [Explanation with sample code](#explanation-with-sample-code-1)
        * [Named exports](#named-exports)
        * [Default import / export](#default-import--export)
      - [External resources](#external-resources-5)
    + [JavaScript *this*](#-javascript-this)
      - [External resources](#external-resources-6)
    + [Class](#class)
      - [Samples](#samples)
      - [External resources](#external-resources-7)
    + [Async Await](#async-await)
      - [Sample code](#sample-code-6)
      - [Explanation with sample code](#explanation-with-sample-code-2)
      - [Error handling](#error-handling)
      - [External resources](#external-resources-8)
    + [Truthy / Falsy](#truthy--falsy)
    + [Static Methods](#static-methods)
      - [Short Explanation](#short-explanation-1)
      - [Sample Code](#sample-code-7)
      - [Detailed Explanation](#detailed-explanation-2)
        * [Calling other static methods from a static method](#calling-other-static-methods-from-a-static-method)
        * [Calling static methods from non-static methods](#calling-static-methods-from-non-static-methods)
      - [External resources](#external-resources-9)
  * [Glossary](#glossary)
    + [Scope](#-scope)
    + [Variable mutation](#-variable-mutation)

## เนื้อหา

### การประกาศตัวแปร: var, const, let

In JavaScript, there are three keywords available to declare a variable, and each has its differences. Those are ```var```, ```let``` and ```const```.
ใน JavaScript มีวิธีการประกาศตัวแปรได้ 3 แบบคือ ```var```, ```let``` และ ```const``` ซึ่งแต่ละแบบมีความแตกต่างกัน

#### คำอธิบายสั้นๆ

Variables declared with ```const``` keyword can't be reassigned, while ```let``` and ```var``` can.
ตัวแปรที่ประกาศโดยใช้ ```const``` จะไม่สามารถถูก assign ค่าให้กับตัวแปรใหม่ได้ ในขณะที่ ```let``` กับ ```var``` สามารถทำได้

I recommend always declaring your variables with ```const``` by default, and with ```let``` if you need to *mutate* it or reassign it later.
แนะนำให้ประกาศตัวแปรด้วย ```const``` เป็นปกติไปก่อน และค่อยเปลี่ยนเป็น ```let``` เมื่อพบว่าตัวแปรนั้นต้องการการ*เปลี่ยนแปลงค่า (mutate)* หรือว่ามีการ assign ค่าให้ตัวแปรในภายหลัง

<table>
  <tr>
    <th></th>
    <th>Scope</th>
    <th>Reassignable</th>
    <th>Mutable</th>
   <th><a href="#tdz_sample">Temporal Dead Zone</a></th>
  </tr>
  <tr>
    <th>const</th>
    <td>Block</td>
    <td>ไม่ใช่</td>
    <td><a href="#const_mutable_sample">ใช่</a></td>
    <td>ใช่</td>
  </tr>
  <tr>
    <th>let</th>
    <td>Block</td>
    <td>ใช่</td>
    <td>ใช่</td>
    <td>ใช่</td>
  </tr>
   <tr>
    <th>var</th>
    <td>Function</td>
    <td>ใช่</td>
    <td>ใช่</td>
    <td>ไม่ใช่</td>
  </tr>
</table>

#### ตัวอย่างโค้ด

```javascript
const person = "Nick";
person = "John" // จะเกิด error เพราะว่า person ไม่สามารถ assign ค่าใหม่ได้
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", let จะยอมให้สามารถ assign ค่าใหม่ได้
```

#### อธิบายเพิ่มเติม

[*scope*](#scope_def) ของตัวแปรคร่าวๆ แล้วหมายถึง "ขอบเขตที่ตัวแปรสามารถใช้งานได้ภายในโค้ด".

##### var

ตัวแปรที่ถูกประกาศด้วย ```var``` จะเป็น *function scoped* หมายถึงว่าเมื่อตัวแปรถูกสร้างภายใน function ทุกอย่างภายใน function นั้นสามารถเข้าถึงตัวแปรนั้นได้ นอกจากนี้ ตัวแปรที่ถูกสร้างเป็น *function scoped* ใน function จะไม่สามารถถูกเข้าถึงจากภายนอก function ได้

แนะนำให้ลองจินตนาการว่าถ้าตัวแปรเป้นตัวแปร *X scoped* หมายความว่าตัวแปรนี้เป็นทรัพย์สินของ X

```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - myVar จะสามารถเข้าถึงได้จากภายใน function
}
console.log(myVar); // จะเกิด ReferenceError, myVar จะไม่สามารถเข้าถึงได้จากภายนอก function
```

Still focusing on the variable scope, here is a more subtle example:
ตัวอย่างเพิ่มเติมสำหรับเรื่อง scope ของตัวแปร

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // จริงๆ แล้ว myvar เป็นตัวแปร function scoped นั่นหมายความว่าตอนนี้เราได้ลบค่าตัวแปร myVar ก่อนหน้าจาก "Nick" กลายเป็น "John"
  }
  console.log(myVar); // "John" - see how the instructions in the if block affected this value
  console.log(myVar); // "John" - จะเห้นว่าค่าได้ถูกเปลี่ยนไปแล้ว
}
console.log(myVar); // จะเกิด ReferenceError, myVar จะไม่สามารถเข้าถึงได้จากภายนอก function
```

นอกจากนี้ตัวแปรที่ประกาสด้วย *var* จะถูกย้ายไปอยู่ด้านบนสุดของ scope เมื่อมีการ execution นี่คือสิ่งที่เราเรียกว่า  [var hoisting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting).

โค้ดตัวอย่างกรณีนี้:

```js
console.log(myVar) // undefined -- ไม่มีการเกิด error
var myVar = 2;
```

is understood at execution like:
ความเข้าใจของ Execution จะเป็นแบบนี้:

```js
var myVar;
console.log(myVar) // undefined -- ไม่มีการเกิด error
myVar = 2;
```

##### let

```var``` and ```let ``` are about the same, but ```let``` declared variables
```var``` และ ```let ``` จะคล้ายกันแต่ตัวแปรที่ประกาศด้วย ```let``` จะ

- เป็น *block scoped*
- จะ**ไม่สามารถ**เข้าถึงก่อนที่มันจะถูก assign ค่าได้
- ไม่สามารถประกาศตัวแปรซ้ำใน scope เดียวกันได้

Let's see the impact of block-scoping taking our previous example:
ลองดูตัวอย่างเรื่องผลกระทบของ block-scoping จากตัวอย่างก่อนหน้า

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // actually, myVar being block scoped, we just created a new variable myVar.
    // this variable is not accessible outside this block and totally independent
    // from the first myVar created !
    // จริงๆ แล้ว myVar เป็น block scoped เราสามารถสร้างตัวแปร myVar ใหม่ได้
    // ตัวแปรนี้จะไม่สามารถเข้าถึงได้จากภายนอก block นี้และเป็นอิสระจากกัน
    // กับตัวแปร myVar ตัวแรกที่เราสร้าง !
  }
  console.log(myVar); // "Nick", จะเห็นตามที่อธิบายข้างต้นว่าภายใน block ไม่ส่งผลกระทบกับค่านี้
}
console.log(myVar); // จะเกิด ReferenceError, myVar จะไม่สามารถเข้าถึงได้จากภายนอก function
```

<a name="tdz_sample"></a> ตอนนี้น่าจะเข้าใจเหตุผลแล้วว่าทำไมตัวแปรที่ประกาศโดยใช้ *let* (และ *const*) ไม่สามารถเข้าถึงได้ก่อนจะถูก assign ค่า

```js
console.log(myVar) // เกิด ReferenceError !
let myVar = 2;
```

สิ่งนี้จะแตกต่างกับตัวแปรที่ประกาศโดยใช้ *var* ถ้าเราพยายามที่จะอ่านหรือเขียนตัวแปรที่ประกาศโดย *let* หรือ *const* ก่อนที่ทำการ assign ค่าจะเกิด Error ทันที ปรากฏการณ์นี้มักถูกเรียกว่า [*Temporal dead zone*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_Dead_Zone_and_errors_with_let) หรือ *TDZ*.

> **Note:** Technically, *let* and *const* variables declarations are being hoisted too, but not their assignation. Since they're made so that they can't be used before assignation, it intuitively feels like there is no hoisting, but there is. Find out more on this [very detailed explanation here](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified) if you want to know more.
> **หมายเหตุ:** ในทางเทคนิคแล้ว การประกาศตัวแปร *let* กับ *const* เป็น hoisted เหมือนกัน, แต่ไม่ใช่กับการ assign ค่า ดังนั้นเมื่อมันไม่สามารถใช้งานได้ก่อน assign ค่าได้ทำให้ดูเหมือนว่าไม่มี hoisting แต่จริงๆ แล้วมันมี อ่าน[คำอธิบายเพิ่มเติมแบบละเอียดที่นี่](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified) ถ้าคุณต้องการ

In addition, you can't re-declare a *let* variable:
เพิ่มเติม คุณไม่สามารถประกาศตัวแปรที่ประกาศด้วย *let* ซ้ำได้:

```js
let myVar = 2;
let myVar = 3; // เกิด SyntaxError
```

##### const

```const``` declared variables behave like *let* variables, but also they can't be reassigned.
การประกาศตัวแปรโดยใช้ ```const``` จะเหมือนกับ *let* แต่ต่างตรงที่พวกมันจะไม่สามารถ assign ซ้ำได้

สรุปสั้นๆ สำหรับตัวแปรที่ประกาศแบบ *const*:

- เป็น *block scoped*
- ไม่สามารถเข้าถึงได้ก่อนถูก assign ค่า
- ไม่สามารถประกาศซ้ำได้ใน scope เดียวกัน
- ไม่สามารถ assign ซ้ำได้

```js
const myVar = "Nick";
myVar = "John" // เกิด error เพราะไม่สามารถ assign ค่าซ้ำได้
```

```js
const myVar = "Nick";
const myVar = "John" // เกิด error เพราะไม่สามารถ assign ซ้ำได้
```

<a name="const_mutable_sample"></a> มีบางจุดที่ต้องระวัง: ตัวแปร ```const``` ไม่ใช่ [**immutable**](#mutation_def) ! Concretely, it means that *object* and *array* ```const``` declared variables **can** be mutated.
<a name="const_mutable_sample"></a> มีบางจุดที่ต้องระวัง: ตัวแปร ```const``` ไม่ใช่ [**immutable**](#mutation_def) ! อธิบายให้ชัดคือตัวแปรที่ประกาศโดย ```const``` ที่เป็น *object* และ *array* ค่าข้างใน**สามารถ**เปลี่ยนแปลงได้

สำหรับ objects:
```js
const person = {
  name: 'Nick'
};
person.name = 'John' // สามารถทำได้ ! ตัวแปร person ไม่ได้ถูก assign ใหม่ แต่ถูกแปลงค่าข้างใน
console.log(person.name) // "John"
person = "Sandra" // เกิด error เพราะว่าไม่สามารถ assign ค่าซ้ำได้สำหรับตัวแปรที่ประกาศด้วย const
```

สำหรับ arrays:
```js
const person = [];
person.push('John'); // สามารถทำได้ ! ตัวแปร person ไม่ได้ถูก assign ใหม่ แต่ถูกแปลงค่าข้างใน
console.log(person[0]) // "John"
person = ["Nick"] // เกิด error เพราะว่าไม่สามารถ assign ค่าซ้ำได้สำหรับตัวแปรที่ประกาศด้วย const
```

#### ข้อมูลเพิ่มเติมจากภายนอก

- [How let and const are scoped in JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Temporal Dead Zone (TDZ) Demystified](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="arrow_func_concept"></a> Arrow function

ใน JavaScript อัปเดต ES6 มี *arrow functions* ซึ่งเป็นการประกาศและใช้ function ในรูปแบบใหม่ และนี่คือประโยชน์ที่มาเพิ่มเติม

- สั้นกระชับมากขึ้น
- *this* อ้างอิงถึงภายนอกรอบๆ
- การ return ค่าทันที

#### โค้ดตัวอย่าง

- การ return ที่สั้นกระชัดและตรงไปตรงมามากขึ้น

```js
function double(x) { return x * 2; } // วิธีปกติ
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // function เดียวกันที่เปลี่ยนมาเขียนโดยใช้ arrow function และ return ทันที
console.log(double(2)) // 4
```

- การอ้างอิงเมื่อใช้ *this*

ใน arrow function *this* จะอ้างอิงถึงค่าของ *this* ที่อยู่บริบทที่ครอบอยู่ พูดง่ายๆ คือเมื่อใช้ arrow function คุณไม่จำเป็นต้องทำทริค "that = this" ก่อนเรียก function อื่นภายใน function อีกทีอีกต่อไป

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### อธิบายเพิ่มเติม

##### การย่อสั้น

Arrow function จะสั้นกระชับกว่า function แบบปกติทั่วไป ลองมาดูวิธีการเขียนแบบที่สามารถเขียนได้ดังนี้:

- Implicit VS Explicit return

An **explicit return** is a function where the *return* keyword is used in its body.
**explicit return** หมายถึง function ที่ต้องมีการใช้คีย์เวิร์ด *return* ข้างในตัวมัน

```js
  function double(x) {
    return x * 2; // function นี้เป็น explicitly returns x * 2, ดังนั้นต้องมีคีย์เวิร์ด *return*
  }
```

โดยวิธีเขียน function แบบปกติแล้ว การ return จะเป็น explicit จะเสมอ แต่สำหรับ arrow function คุณสามารถทำ *implicit return* ซึ่งหมายความว่าคุณไม่จำเป็นต้องใช้คีย์เวิร์ด *return* เพื่อ return ค่า

ในการเขียน implicit return จะต้องเขียนโค้ดให้เหลือเพียง 1 บรรทัด

```js
  const double = (x) => {
    return x * 2; // Explicit return ตรงนี้
  }
```

เมื่อมันทำแค่ return ค่าตรงนั้นทันที เราสามารถเขียนแบบ implicit return ได้ตามนี้

```js
  const double = (x) => x * 2;
```

และตามข้างบน ที่เราต้องทำมีแค่ **เอาวงเล็บออก** กับคีย์เวิร์ด **return** ออก นี่เลยเป็นสามารถว่าทำไมมันถึงเรียกว่า *implicit* return เพราะว่าไม่จำเป็นต้องใช้คีย์เวิร์ด return แต่ function ก็ยัง return ```x * 2``` อยู่

> **หมายเหตุ:** ถ้า function ของคุณไม่ได้ต้องการการ return ค่า (พร้อมกับ *side effects*) จะใช้แบบไหนก็ไม่ต่างกัน

นอกจากนี้ ถ้าคุณต้องการใช้ implicit return ค่าเป็น *object* คุณ**ต้องใช้วงเล็บครอบ** เพื่อป้องกัน conflict กับ block scope

```js
const getPerson = () => ({ name: "Nick", age: 24 })
console.log(getPerson()) // { name: "Nick", age: 24 } -- object implicitly return ค่าโดยใช้ arrow function
```

- มี argument แค่ตัวเดียว

If your function only takes one parameter, you can omit the parentheses around it. If we take back the above *double* code:
ถ้า function รับ parameter เพียงแค่ตัวเดียว สามารถเอาวงเล็บออกได้ ถ้าเราปรับปรุงจากโค้ด *double* ก่อนหน้าจะได้ดังนี้

```js
  const double = (x) => x * 2; // arrow function นี้รับเพียง 1 parameter
```

วงเล็บสามารถเอาออกได้ดังนี้:

```js
  const double = x => x * 2; // arrow function นี้รับเพียง 1 parameter
```

- ไม่มี argument

When there is no argument provided to an arrow function, you need to provide parentheses, or it won't be valid syntax.
เมื่อไม่ต้องการ argument ใดๆ เลยใน arrow function คุณจำเป็นต้องใส่วงเล็บ ไม่อย่างนั้นมันจะไม่ใช่ syntax ที่ถูกต้อง

```js
  () => { // ถ้ามีวงเล็บ ทุกอย่างจะปกติ
    const x = 2;
    return x;
  }
```

```js
  => { // ถ้าไม่มีวงเล็บ จะใช้งานไม่ได้!
    const x = 2;
    return x;
  }
```

##### การอ้างอิง *this*

To understand this subtlety introduced with arrow functions, you must know how [this](#this_def) behaves in JavaScript.
เพื่อที่จะเข้าใจเรื่อง this กับ arrow function คุณต้องเข้าใจก่อนว่า [this](#this_def) ทำงานยังไงใน JavaScript

ใน arrow function *tihs* มีค่าเท่าที่ค่าของ *this* ที่เป็นบริบทที่ครอบมันอยู่ นั่หมายถึงว่า arrow function ไม่สร้าง *this* ขึ้นมาใหม่ แต่ว่ามันเอาค่าที่อยู่รอบนอกของมันมาใช้แทน

Without arrow function, if you wanted to access a variable from *this* in a function inside a function, you had to use the *that = this* or *self = this* trick.
ถ้าไม่ใช่ arrow function ถ้าคุณต้องการใช้งานตัวแปร *this* ของ function เมื่ออยู่ภายใน function อีกที คุณจะต้องใช้ *that = this* หรือว่า *self = this* เป็นทริคเพื่ออ้างอิงถึง

ยกตัวอย่างเช่น เมื่อใช้ setTimeout function ภายใน myFunc:

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // ทริค that = this
  setTimeout(
    function() { // *this* ใหม่ถูกสร้างภายใน function scope นี้
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // undefined -- ไปหาที่การประกาศของ function นี้
    },
    0
  );
}
```

But with arrow function, *this* is taken from its surrounding:
แต่เมื่อใช้ arrow function *this* จะอ้างอิงถึงที่อยู่รอบๆ ตัวมัน:

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => { // this มาจากรอบๆ นั่นหมายถึง myFunc ในกรณีนี้
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

#### ข้อมูลเพิ่มเติม

- [Arrow functions introduction - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript arrow function - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

### ค่า Default parameter ของ function

ตั้งแต่อัปเดตของ ES2015 JavaScript คุณสามารถตั้งค่า default ในกับ parameter ของ function โดยใช้ syntax ตามข้างล่างนี้:

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- ไม่ได้มีค่าโยนเข้าไปใน parameter ดังนั้นค่า x จะถูก assign เป็นค่า default ของ myFunc นั่นก็คือ 10
console.log(myFunc(5)) // 5 -- มีค่าโยนเข้าไปใน paramter ดังนั้นค่า x จะมีค่าเท่ากับ 5 ใน myFunc

console.log(myFunc(undefined)) // 10 -- โยนค่าเป็น undefined ไป ดังนั้นจะนำค่า default มาใช้ซึ่งก็คือ 10
console.log(myFunc(null)) // null -- โยนค่า null เข้าไปจึงได้ค่า x เป็น null, ดูรายละเอียดเพิ่มเติมข้างล่าง
```

The default parameter is applied in two and only two situations:
ค่า default paramter จะถูกเรียกใช้ในสองกรณีนี้เท่านั้น:

- ไม่โย parameter มาให้
- รับค่า parameter เป็น *undefined*

In other words, if you pass in *null* the default parameter **won't be applied**.
หรือในอีกความหมายนึงคือ ถ้าคุณส่งค่าเป็น *null* จะไม่มีการใช้งาน default parameter

> **Note:** Default value assignment can be used with destructured parameters as well (see next notion to see an example)
> **หมายเหตุ:** ค่า Default สามารถใช้ร่วมกับ destructured parameters ได้ (ตัวเนื้อหาหัวข้อหน้าสำหรับตัวอย่าง)

#### ข้อมูลเพิ่มเติมภายนอก

- [Default parameter value - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Default parameters - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

### Destructuring objects และ arrays

*Destructuring* เป็นวิธีในการสร้างตัวแปรใหม่จากการแยกค่าบางค่าจากข้างในของ objects หรือ arrays ให้สะดวกมากยิ่งขึ้น

ยกตัวอย่างสำหรับการใช้งานเช่น *destructuring* สามารถใช้ในการแยกส่วน parameters ของฟังก์ชั่น หรือว่า *this.props* ในโปรเจ็คที่เป็น React

#### อธิบายเพิ่มเติมเกี่ยวกับตัวอย่าง

- Object

ลองพิจารณา object ข้างล่างเป็นตัวอย่าง:

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

เมื่อไม่ใช้ destructuring:

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

เมื่อใช้ destructuring สามารถเขียนในบรรทัดเดียวได้แบบนี้:

```js
const { firstName: first, age, city = "Paris" } = person; // แบบนี้ !

console.log(age) // 35 -- A new variable age is created and is equal to person.age
console.log(age) // 35 -- ตัวแปร age ถูกสร้างขึ้นมาใหม่และมีค่าเท่ากับ person.age
console.log(first) // "Nick" -- ตัวแปร first ถูกสร้างขึ้นมาใหม่และมีค่าเท่ากับ person.firstName
console.log(firstName) // Undefined -- person.firstName มีอยู่จริง แต่ตัวแปรที่ถูกสร้างขึ้นใหม่ถูกตั้งชื่อว่า first
console.log(city) // "Paris" -- ตัวแปร city ถูกสร้างขึ้นใหม่ และ person.city มีค่าเป็น undefined เพราะฉะนั้น city จะมีค่าเท่ากับ default ที่ระบุไว้คือ "Paris"
```

**หมายเหตุ :** ใน ```const { age } = person;```, ปีกกาหลังคีย์เวิร์ด *const* มีได้หมายถึงเป็นการประกาศ object หรือว่า block แต่มันหมายถึงเป็น *destructuring* syntax.

- Function parameters

*Destructuring* จะใช้บ่อยในการ destructure objects parameters ใน functions

ถ้าไม่มี destructuring

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

*person* สามารถทำ destructuring เพื่อให้สั้นกระชับขึ้นได้ดังนี้:

```js
function joinFirstLastName({ firstName, lastName }) { // สร้างตัวแปร firstName กับ lastName โดยการ destructuring ตัวแปร
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

Destructuring ยังถูกใช้บ่อยควบคู่กับ [arrow functions](#arrow_func_concept):

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```

- Array

จาก array ข้างล่างต่อไปนี้:

```js
const myArray = ["a", "b", "c"];
```

เมื่อไม่มี destructuring

```js
const x = myArray[0];
const y = myArray[1];
```

เมื่อมี destructuring

```js
const [x, y] = myArray; // แบบนี้ !

console.log(x) // "a"
console.log(y) // "b"
```

#### ข้อมูลที่เป็นประโยชน์

- [ES6 Features - Destructuring Assignment](http://es6-features.org/#ArrayMatching)
- [Destructuring Objects - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destructuring](http://exploringjs.com/es6/ch_destructuring.html)

### Array methods - map / filter / reduce

*Map*, *filter* และ *reduce* เป็น method ของ array ที่มาจาก programming paradigm ที่ชื่อว่า [*functional programming*](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0).

สรุปแบบสั้นๆ:

- **Array.prototype.map()** นำ array มาวนลูป ทำอะไรบางอย่างกับค่าของมันแต่ละค่าแล้ว return กลับกลายเป็น array ที่แปลงค่าแล้ว.
- **Array.prototype.filter()** นำ array มาวนลูป เลิอกว่าค่าไหนเก็บไว้และค่าไหนทิ้ง และ return กลับไปเป็น array ที่ถูกเลือกแล้ว
- **Array.prototype.reduce()** นำ array มาวนลูปและประกอบกันแต่ละค่าสนเหลือเพียงค่าเดียวเพื่อ return กลับไป

แนะนำให้ใช้พวกนี้มากที่สุดเท่าที่จะทำได้ตามทฤษฐีของ functional programming เพราะว่ามันสวยงามและสั้นกระชับกว่า

เมื่อมี 3 methods นี้ คุณสามารถละการใช้ *for* และ *forEach* ลูปในสถานการณ์ส่วนใหญ่ได้ เมื่อคุณจะใช้ *for* ลูป ลองเปลี่ยนมาใช้ *map*, *filter* และ *reduce* แทน แรกๆ อาจจะติดเพราะว่าต้องเปลี่ยนวิธีในการคิดแต่หลังจากเข้าใจและใช้ไปซักระยะจะสามารถใช้งานได้อย่างง่ายดาย

#### โค้ดตัวอย่าง

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
const doubledNumbers = numbers.map(n => n * 2); // [0, 2, 4, 6, 8, 10, 12]
const evenNumbers = numbers.filter(n => n % 2 === 0); // [0, 2, 4, 6]
const sum = numbers.reduce((prev, next) => prev + next, 0); // 21
```

คำนวณผลรวมเกรดทั้งหมดของนักเรียนโดยใช้ map, filter และ reduce:

```js
const students = [
  { name: "Nick", grade: 10 },
  { name: "John", grade: 15 },
  { name: "Julia", grade: 19 },
  { name: "Nathalie", grade: 9 },
];

const aboveTenSum = students
  .map(student => student.grade) // เรา map ข้อมูลนักเรียนให้กลายเป็น array ที่มีแต่เกรด
  .filter(grade => grade >= 10) // เรา filter เกรดให้เก็บไว้เฉพาะที่มีค่ามากกว่าเท่ากับ 10
  .reduce((prev, next) => prev + next, 0); // เรารวมผลรวมของทุกเกรดทีละคน

console.log(aboveTenSum) // 44 -- 10 (Nick) + 15 (John) + 19 (Julia), Nathalie ได้เกรดต่ำกว่า 10 จะถูกข้ามไป
```

#### อธิบายเพิ่มเติม

ลองดู array ของตัวเลขต่อไปนี้ที่จะใช้ในตัวอย่าง:


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

เกิดอะไรขึ้นในข้างบนบ้าง? เราใช้ .map กับ array ที่เก็บ *ตัวเลข* โดย map จะทำการวนรอบ (iterating) ทุกๆ ค่าที่อยู่ภายใน array และส่งค่าต่อเข้าไปใน function ของเรา เป้าหมายของ function คือต้องการสร้างค่าใหม่จากค่าเดิมที่ส่งเข้ามาและส่งกลับไป

ถ้ากระจาย function ให้อ่านง่ายขึ้นจะเป็นตามภาพดังนี้:

```js
const doubleN = function(n) { return n * 2; };
const doubledNumbers = numbers.map(doubleN);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

```numbers.map(doubleN)``` produces ```[doubleN(0), doubleN(1), doubleN(2), doubleN(3), doubleN(4), doubleN(5), doubleN(6)]``` จะเท่ากับ ```[0, 2, 4, 6, 8, 10, 12]```.

> **หมายเหตุ:** ถ้าคุณไม่ต้องการ return array ใหม่ แต่ต้องการทำลูปที่สร้าง side effects คุณอาจจะต้องการใช้ for / forEach ลูปมากกว่าใช้ map

##### Array.prototype.filter()

```js
const evenNumbers = numbers.filter(function(n) {
  return n % 2 === 0; // ถ้า n เป็นเลขคู่จะเป็น true, และ false ถ้า n ไม่ใช่
});
console.log(evenNumbers); // [0, 2, 4, 6]
```

เราใช้ .filter กับ array ที่เก็บ *ตัวเลข* ชุดเดิม, filter จะทำการวนรอบ (iterating) ทุกค่าใน array และส่งเข้าไปใน function ของเรา เป้าหมายของ function นี้คือการ return เป็น boolean ว่าค่านั้นๆ จะต้องการเก็บเอาไว้หรือทิ้ง ผลสุดท้ายของ filter จะ return array ที่เหลือแต่ค่าที่เลือกเก็บเท่านั้น

##### Array.prototype.reduce()

reduce method จะทำหน้าที่ *reduce* ทุกค่าใน array โดยมันจะวนรอบ (iterate) ค่าทั้งหมดให้กลายเหลือเป็นค่าเดียว โดยจะประกอบค่าต่างๆ ยังไงอยู่ที่เรากำหนด

```js
const sum = numbers.reduce(
  function(acc, n) {
    return acc + n;
  },
  0 // ตัวสะสมค่าตัวแปรสำหรับการวนรอบแรก
);

console.log(sum) //21
```

เหมือนกับ method ของ .map และ .filter เพียงแต่ว่า .reduce จะนำค่าที่ได้จากรอบก่อนหน้ามาส่งต่อเป็น parameter แรกของ function

มาดูความแตกต่าง:

- .reduce รับ parameter สองตัว

parameter แรกจะเป็น function สำหรับการวนรอบ (itelation)

parameter ที่สองจะเป็นค่าตัวแปรสะสม (ในที่นี้หมายถึง *acc*) สำหรับการวนรอบรอบแรก (อ่านหัวข้อถัดไปเพื่อทำความเข้าใจมากขึ้น)

- Function parameters

function ที่ส่งเข้าไปใน parameter แรกของ .reduce จะได้รับ parameter ทั้งหมด 2 ตัว ตัวแรก (ในที่นี้คือ *acc*) คือตัวแปรสะสม ในขณะที่ตัวแปรที่สอง (*n*) คือค่าปัจจุบัน

ตัวแปรสะสมจะเท่ากับค่าที่ return ใน function ของการวนรอบ (iteration) ก่อนหน้า ในการวนรอบแรก *acc* จะมีค่าเท่ากับค่าที่คุณส่งเป็น parameter ที่สองให้กับ .reduce

###### ในการวนรอบรอบแรก

```acc = 0``` เพราะเราส่งค่า 0 เป็น parameter ที่สองให้กับ reduce

```n = 0``` ค่าแรกของ array ที่เก็บ *ตัวเลข*

Function จะ returns *acc* + *n* --> 0 + 0 --> 0

###### ในการวนรอบรอบที่สอง

```acc = 0``` เพราะว่ามันคือค่าที่มาจากการ return ของ function ในการวนรอบก่อนหน้า

```n = 1``` second element of the *number* array
```n = 1``` ค่าที่สองของ array ที่เก็บ *ตัวเลข*

Function จะ returns *acc* + *n* --> 0 + 1 --> 1

###### ในการวนรอบรอบที่สาม

```acc = 1``` เพราะว่ามันคือค่าที่มาจากการ return ของ function ในการวนรอบก่อนหน้า

```n = 2``` ค่าที่สามของ array ที่เก็บ *ตัวเลข*

Function จะ returns *acc* + *n* --> 1 + 2 --> 3

###### ในการวนรอบรอบที่สี่

```acc = 3``` เพราะว่ามันคือค่าที่มาจากการ return ของ function ในการวนรอบก่อนหน้า

```n = 3``` ค่าที่สี่ของ array ที่เก็บ *ตัวเลข*

Function จะ returns *acc* + *n* --> 3 + 3 --> 6

###### [...] ในการวนรอบสุดท้าย

```acc = 15``` เพราะว่ามันคือค่าที่มาจากการ return ของ function ในการวนรอบก่อนหน้า

```n = 6``` ค่าสุดท้ายของ array ที่เก็บ *ตัวเลข*

Function จะ returns *acc* + *n* --> 15 + 6 --> 21

ในการวนรอบสุดท้าย **.reduce** จะคืนค่า 21 กลับไป

#### ข้อมูลเพิ่มเติมภายนอก

- [Understanding map / filter / reduce in JS](https://hackernoon.com/understanding-map-filter-and-reduce-in-javascript-5df1c7eee464)

### Spread operator "..."

spread operator ```...``` เป็นของใหม่ใน ES2015 และใช้สำหรับแผ่ขยายค่าของสิ่งที่สามารถนำมาวนรอบได้ (อย่างเช่น array) เข้าไปในที่ที่สามารถเก็บค่าหลายค่าได้

#### โค้ดตัวอย่าง

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

#### อธิบายเพิ่มเติม

##### ในสิ่งที่สามารถวนรอบได้ (ยกตัวอย่างเช่น array)

ถ้าเรามี array สองตัวดังนี้:

```js
const arr1 = ["a", "b", "c"];
const arr2 = [arr1, "d", "e", "f"]; // [["a", "b", "c"], "d", "e", "f"]
```

*arr2* the first element is an array because *arr1* is injected as is into *arr2*. But what we want is *arr2* to be an array of letters. To do so, we can *spread* the elements of *arr1* into *arr2*.
ใน *arr2* ค่าแรกจะเป็น array เพราะว่า *arr1* ถูกนำเข้าไปใส่ใน *arr2* แต่ถ้าเราต้องให้ *arr2* เป็น array ของตัวอักษรเพียงอย่างเดียว สิ่งที่เราต้องทำคือเราสามารถ *spread* ค่าต่างๆ ของ *arr1* เข้าไปสู่ *arr2* ได้

เมื่อใช้ spread operator

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

##### Function rest parameter

ใน parameter ของ function เราสามารถใช้ rest operator สำหรับรวม parameters เป็น array ที่เราสามารถนำไปวนลูปได้ มันเป็น **argument** object มีค่าเหมือนกับการรวมทุก parameter เป็น array และส่งเข้าไปใน function

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

แต่ถ้าเราต้องการให้ function นี้สร้างนักเรียนใหม่พร้อมกับ grade ทั้งหมดของนักเรียนและค่าเฉลี่ยเกรด จะง่ายกว่าถ้าเราแยกให้สอง parameter แรกเป็นตัวแปรแยก และที่เหลือจากนั้นเป็น grade ที่เราสามารถนำไปวนรอบได้มันน่าจะดีกว่ารึเปล่า?

และ rest operator ทำให้เราสามารถทำแบบนั้นได้!

```js
function createStudent(firstName, lastName, ...grades) {
  // firstName = "Nick"
  // lastName = "Anderson"
  // [10, 12, 6] -- "..." นำ paramters ที่รับเข้ามาที่เหลือสร้างเป็นตัวแปร array ชื่อ "grades"

  const avgGrade = grades.reduce((acc, curr) => acc + curr, 0) / grades.length; // คำนวณค่าเฉลี่ยของ grades

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

> **หมายเหตุ:** function createStudent ยังไม่ดีเท่าไหร่เพราะว่าเรายังไม่ได้เช็ก grades.length ในกรณีที่ไม่มีค่าอยู่จริงหรือไม่ใช่ 0 แต่มันง่ายกว่าถ้าเขียนแบบนี้ เพราะฉะนั้นในโค้ดตัวอย่างเลยจะไม่มีการจัดการกับเคสนี้

##### Object properties spreading

ก่อนจะเข้าเรื่องนี้ แนะนำให้อ่านคำอธิบายก่อนหน้าสำหรับ rest operator ที่นำ function parameters มาวนรอบก่อน

```js
const myObj = { x: 1, y: 2, a: 3, b: 4 };
const { x, y, ...z } = myObj; // object destructuring ตรงนี้
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

// z จะได้ค่าที่เหลือของ object ที่ถูก destructured แล้ว: myObj object เมื่อลบค่า x และ y properties ที่ถูก destructured ออกไปแล้ว

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }

// เมื่อนำ z object มา spread กลับเข้าไปให้กับตัวแปร n
```

#### ข้อมูลเพิ่มเติมภายนอก

- [TC39 - Object rest/spread](https://github.com/tc39/proposal-object-rest-spread)
- [Spread operator introduction - WesBos](https://github.com/wesbos/es6-articles/blob/master/28%20-%20Spread%20Operator%20Introduction.md)
- [JavaScript & the spread operator](https://codeburst.io/javascript-the-spread-operator-a867a71668ca)
- [6 Great uses of the spread operator](https://davidwalsh.name/spread-operator)

### Object property shorthand

เมื่อ assign ค่าใช้ตัวแปรเป็น object property ถ้าชื่อตัวแปรมีค่าเท่ากับชื่อ property คุณสามารถทำแบบนี้ได้:

```js
const x = 10;
const myObj = { x };
console.log(myObj.x) // 10
```

#### อธิบายเพิ่มเติม

ปกติแล้ว (pre-ES2015) เมื่อคุณประกาศ *object literal* ใหม่ และต้องการใช้ค่าของตัวแปรเป็น object properties ปกติแล้วต้องเขียนแบบนี้:

```js
const x = 10;
const y = 20;

const myObj = {
  x: x, // assign ค่าของตัวแปร x ให้เป็นค่าของ myObj.x
  y: y // assign ค่าของตัวแปร y ให้เป็นค่าของ myObj.y
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```

ตามที่คุณเห็น จะเห็นว่ามันซ้ำซ้อนกันเพราะว่าชื่อ properties ของ myObj เป็นชื่อเดียวกับตัวแปรที่ต้องการ assign ให้กับ properties เหล่านั้น

เมื่อเขียนด้วย ES2015 เมื่อชื่อตัวแปรเป็นชื่อเดียวกับชื่อ property คุณสามารถเขียนให้สั้นลงเป็นแบบนี้ได้:

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

#### ข้อมูลเพิ่มเติมภายนอก

- [Property shorthand - ES6 Features](http://es6-features.org/#PropertyShorthand)

### Promises

Promise เป็น object ที่สามารถ return ค่าแบบ synchronous จาก function asynchronous ได้ ([ref](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261#3cd0)).

Promise สามารถใช้เพื่อแก้ปัญหาของ [callback hell](http://callbackhell.com/) และมันมักนำไปใช้ในโค้ด Javascript โปรเจ็คใหม่ๆ ที่ทันสมัย

#### โค้ดตัวอย่าง

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

#### อธิบายเพิ่มเติม

เมื่อคุณสร้าง *Ajax request* จะได้รับ response ที่ไม่ synchronous เพราะว่ามันต้องใช้เวลาเพื่อจะได้ผลลัพธ์ที่กลับมา มันอาจจะไม่ได้ค่าที่ต้องการกลับมาถ้า request ที่ส่งไปไม่สามารถใช้งานได้ด้วยเหตุบางประการ (404)

เพื่อรับมือกับสถานการณ์แบบนั้น ES2015 ได้มี *promises* ซึ่ง promise มีทั้งหมด 3 states ด้วยกัน:

- Pending
- Fulfilled
- Rejected

หรือพูดอีกอย่างว่าเราต้องการใช้ promise ไปการจัดการกับพวก Ajax request เพื่อดึงข้อมูลจาก X

##### การสร้าง promise

ก่อนที่เราจะใช้ promise เราจะใช้ jQuery สำหรับการทำ Ajax request ไปหา X

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

```js
const xFetcherPromise = new Promise( // สร้าง promise โดยใช้คีย์เวิร์ด "new" และเก็บลงตัวแปร
  function(resolve, reject) { // constructor ของ promise รับ parameter เป็น function ที่มี parameter ชื่อ resolve และ reject ด้วยตัวมันเอง
    $.get("X") // ส่ง Ajax request
      .done(function(X) { // เมื่อ request เสร็จแล้ว ...
        resolve(X); // ... resolve promist ด้วยค่า X กลับไปเป็น parameter
      })
      .fail(function(error) { // ถ้า request เกิดผิดพลาด...
        reject(error); // ... reject promise แล้วส่ง error กลับไปเป็น parameter
      });
  }
)

จากที่เห็นในตัวอย่างข้างบน Promise object จะรับ *executor* function ที่รับ parameter สองตัวคือ **resolve** และ **reject**  ซึ่งสองตัวนี้ถ้ามีการเรียกใช้จะเป็นการย้าย state ของ promise จาก *pending* ไปสู่ *fulfilled* หรือ *rejected*

promise จะอยู่ใน pending state หลังสร้าง instance และ function *executor* ของมันจะทำงานทันที และเมื่อมีการเรียกใช้ function *resolve* หรือ *reject* ภายใน *executor* function ตัว promise จะเรียก handlers ที่เกี่ยวข้อง

##### การใช้งาน Promise handlers

เพื่อที่จะรับผลลัพธ์ของ promise (หรือว่า error) เราจะสามารถควบคุมด้วย handlers โดยทำได้ดังนี้:

```js
xFetcherPromise
  .then(function(X) {
    console.log(X);
  })
  .catch(function(err) {
    console.log(err)
  })
```

ถ้า promise สมบูรณ์ *resolve* จะ executed และ function จะส่งค่าไปเป็น parameter ```.then```

ถ้าเกิดข้อผิดพลาด *reject* จะถูกเรียกแล้วส่งค่าไปเป็น parameter ```.catch```

> **หมายเหตุ :** ถ้า promise เข้าไปสู่ state fulfilled หรือ rejected โดยที่มีการใช้ handler แล้ว handler จะถูกเรียกใช้ ทำให้ไม่เกิด race condition ระหว่างรอ asynchronous เสร็จสมบูรณ์กับ handlers [(Ref: MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise#Description)

#### External Resources

- [JavaScript Promises for dummies - Jecelyn Yeen](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [JavaScript Promise API - David Walsh](https://davidwalsh.name/promises)
- [Using promises - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [What is a promise - Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- [JavaScript Promises: an Introduction - Jake Archibald](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
- [Promise documentation - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

### Template literals

Template literals เป็น [*expression interpolation*](https://en.wikipedia.org/wiki/String_interpolation) สำหรับ strings ตั้งแต่บรรทัดเดียวถึงหลายบรรทัด

หรือในอีกกรณีนึงก็คือ มันเป็น syntax ของ string ที่คุณสามารถใช้ JavaScript expesssions ข้างในได้อย่างสะดวกมากขึ้น (ยกตัวอย่างเช่นแทรกตัวแปรภายใน string)

#### โค้ดตัวอย่าง

```js
const name = "Nick";
`Hello ${name}, the following expression is equal to four : ${2+2}`;

// Hello Nick, the following expression is equal to four: 4
```

#### ข้อมูลเพิ่มเติมภายนอก

- [String interpolation - ES6 Features](http://es6-features.org/#StringInterpolation)
- [ES6 Template Strings - Addy Osmani](https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

### Tagged template literals

Template tags are *functions that can be prefixed to a [template literal](#template-literals)*. When a function is called this way, the first parameter is an array of the *strings* that appear between the template's interpolated variables, and the subsequent parameters are the interpolated values. Use a spread operator `...` to capture all of them. [(Ref: MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#Tagged_template_literals).
Template tags คือ *functions ที่สามารถเป็น prefixed ให้กับ [template literal](#template-literals)*. เมื่อ function ถูกเรียกใช้แบบนี้ parameter แรกจะเป็น array ของ *strings* ที่แสดงระหว่างตัวแปรของ template's interpolated และ parameter อื่นที่ตามมาคือค่า interpolated ดังนั้นใช้ spread operator `...` เพื่อรวบรวม parameter ทั้งหมด [(Ref: MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#Tagged_template_literals).

> **หมายเหตุ :** Library ชื่อดังอย่าง [styled-components](https://www.styled-components.com/) ใช้ feature นี้อย่างเต็มรูปแบบ

ข้างล่างคือตัวอย่างของการนำไปใช้งาน
```js
function highlight(strings, ...values) {
  const interpolation = strings.reduce((prev, current) => {
    return prev + current + (values.length ? "<mark>" + values.shift() + "</mark>" : "");
  }, "");

  return interpolation;
}

const condiment = "jam";
const meal = "toast";

highlight`I like ${condiment} on ${meal}.`;
// "I like <mark>jam</mark> on <mark>toast</mark>."
```

ตัวอย่างที่น่าสนใจเพิ่มเติม:
```js
function comma(strings, ...values) {
  return strings.reduce((prev, next) => {
    let value = values.shift() || [];
    value = value.join(", ");
    return prev + next + value;
  }, "");
}

const snacks = ['apples', 'bananas', 'cherries'];
comma`I like ${snacks} to snack on.`;
// "I like apples, bananas, cherries to snack on."
```

#### ข้อมูลเพิ่มเติมภายนอก
- [Wes Bos on Tagged Template Literals](http://wesbos.com/tagged-template-literals/)
- [Library of common template tags](https://github.com/declandewet/common-tags)

### Imports / Exports

ES6 modules สามารถเข้าถึงตัวแปรต่างๆ ของ modules ที่ทำการแยก export ได้ด้วยการ imports

แนะนำเป็นอย่างมากให้ลองอ่านข้อมูลเพิ่มเติมใน MDN resources เกี่ยวกับเรื่อง import/export (ดูข้อมูลเพิ่มเติมภายนอกข้างล่าง) ตัวเนื้อหาค่อนข้างอธิบายได้ตรงไปตรงมาและสมบูรณ์

#### อธิบายเพิ่มเติมเกี่ยวกับโค้ดตัวอย่าง

##### Named exports

Named exports ใช้สำหรับการ export หลายๆ ค่าของ module

> **หมายเหตุ :** คุณสามารถ export แบบ name-export [first-class citizens](https://en.wikipedia.org/wiki/First-class_citizen) ได้เฉพาะสิ่งที่มีชื่อ.

```js
// mathConstants.js
export const pi = 3.14;
export const exp = 2.7;
export const alpha = 0.35;

// -------------

// myFile.js
import { pi, exp } from './mathConstants.js'; // Named import -- คล้ายๆ กับ syntax destructuring
console.log(pi) // 3.14
console.log(exp) // 2.7

// -------------

// mySecondFile.js
import * as constants from './mathConstants.js'; // ทำค่าทั้งหมดที่มีการ exports มาเป็นตัวแปร
console.log(constants.pi) // 3.14
console.log(constants.exp) // 2.7
```

named imports จะคล้ายกับ *destructuring* แต่ว่าจริงๆ แล้วมีความต่างและไม่เหมือนกัน มันไม่รองรับการใช้ default value หรือว่า *deep* destructuring

นอกจากนี้คุณสามารถทำ alias ได้อยู่ เพียงแต่ว่า syntax จะแตกต่างกับ destructuring

```js
import { foo as bar } from 'myFile.js'; // foo ถูก import เข้ามาและเอาไปเป็นค่าตัวแปรใหม่ที่ชื่อว่า bar
```

##### Default import / export

สำหรับ default export เราจะสามารถ export default ได้แค่ตัวเดียวต่อ module และค่า default ที่ export สามารถเป็นได้ทั้ง function, class, object หรืออะไรก็ตาม ค่านี้เป็นเหมือนค่า "หลัก" ในการ export และมันจะง่ายต่อการ import [Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description)

```js
// coolNumber.js
const ultimateNumber = 42;
export default ultimateNumber;

// ------------

// myFile.js
import number from './coolNumber.js';
// Default export จะอิสระในการตั้งชื่อ อย่างข้างบนจะถูกเก็บลงตัวแปรชื่อ number
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

#### ข้อมูลเพิ่มเติมภายนอก

- [ES6 Modules in bulletpoints](https://ponyfoo.com/articles/es6#modules)
- [Export - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
- [Import - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Understanding ES6 Modules](https://www.sitepoint.com/understanding-es6-modules/)
- [Destructuring special case - import statements](https://ponyfoo.com/articles/es6-destructuring-in-depth#special-case-import-statements)
- [Misunderstanding ES6 Modules - Kent C. Dodds](https://medium.com/@kentcdodds/misunderstanding-es6-modules-upgrading-babel-tears-and-a-solution-ad2d5ab93ce0)
- [Modules in JavaScript](http://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript)

### <a name="this_def"></a> JavaScript *this*

*this* operator จะแตกต่างกับาภาษาอื่นๆ และโดยกรณีส่วนมากเป็นตัวกำหนดว่า function จะเรียกใช้ยังไง ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)).

เนื้อนี้จะมีรายละเอียดที่ค่อนข้างอ่อนไหวและยาก แนะนำให้ลองอ่านข้อมูลภายนอกเพิ่มเติมข้างล่าง ดังนั้นจะแนะนำโดยใช้จากความคิดส่วนตัวในการอธิบายว่า *this* มีค่าเป็นอะไรจากที่เรียนรู้จาก[บทความที่เขียนโดย Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)

```js
function myFunc() {
  ...
}

// ข้างล่างจะแสดงให้เห็นค่าของ *this* ใน myFunc

myFunc.call("myString", "hello") // "myString" -- ค่า parameter แรกใน .call จะถูกกำหนดเป็น *this*

// ในโหมด non-strict-mode
myFunc("hello") // window -- myFunc() เป็น syntax เหมือนกับเรียก myFunc.call(window, "hello")

// ในโหมด strict-mode
myFunc("hello") // undefined -- myFunc() เป็น syntax เหมือนกับเรียก myFunc.call(undefined, "hello")
```

```js
var person = {
  myFunc: function() { ... }
}

person.myFunc.call(person, "test") // person Object -- ค่า parameter แรกใน .call จะถูกกำหนดเป็น *this*
person.myFunc("test") // person Object -- person.myFunc() เป็น syntax เหมือนกับเรียก person.myFunc.call(person, "test")

var myBoundFunc = person.myFunc.bind("hello") // สร้าง function ใหม่ที่ผูก "hello" เป็นค่าของ *this*
person.myFunc("test") // person Object -- bind method ไม่มีผลใดๆ กับ method ดั้งเดิม
myBoundFunc("test") // "hello" -- myBoundFunc เป็น person.myFunc ที่มี "hello" เป็น *this*
```

#### ข้อมูลเพิ่มเติมภายนอก

- [Understanding JavaScript Function Invocation and "this" - Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)
- [JavaScript this - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

### Class

JavaScript เป็นภาษาที่เป็น [prototype-based](https://en.wikipedia.org/wiki/Prototype-based_programming) (ยกตัวอย่างเช่นในขณะที่ว่า Java เป็นภาษาที่เป็น [class-based](https://en.wikipedia.org/wiki/Class-based_programming)). ES6 ได้ทำให้ JavaScript เสมือนมี class ขึ้นมาโดยสืบทอดจาก prototype-based และ **ไม่ใช่** class-based ([ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)).

คำว่า *class* จะไม่เหมือนกับ class ในภาษาอื่นๆ ถ้าทำตามภาษาอื่นๆ อาจจะมีโอกาสที่จะ error เพราะงั้นไม่ควรคิดเอาเองว่า class ของ JavaScript สามารถทำได้ตามที่ปกติทำ และลองพิจารณาเนื้อทั้งหมดนี้ก่อน

ตั้งแต่บทความนี้ไม่ได้สอนเรื่องภาษาตั้งแต่เริ่มต้น เราเชื่อคุณรู้อยู่แล้วว่า prototypes คืออะไรและทำหน้าที่อะไร แต่เรามี link บางส่วนที่จะช่วยอธิบายเพื่อให้เข้าใจเนื้อหาในนี้ได้ดีขึ้น

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Inheritance and the prototype chain - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

#### ตัวอย่าง

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

เมื่อใช้ Syntax แบบ ES6:

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

#### ข้อมูลภายนอกเพิ่มเติม

สำหรับทำความเข้าใจ prototype:

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Inheritance and the prototype chain - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

สำหรับทำความเข้าใจ classes:

- [ES6 Classes in Depth - Nicolas Bevacqua](https://ponyfoo.com/articles/es6-classes-in-depth)
- [ES6 Features - Classes](http://es6-features.org/#ClassDefinition)
- [JavaScript Classes - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

### Async Await

เพิ่มเติมจาก [Promises](#promises) จะมี syntax รูปแบบให้สำหรับจัดการกับ asynchronous ชื่อว่า *async / await*

จุดประสงค์ของ async/await function คือทำให้สามารถจัดการกับการใช้ promise synchronous ได้ง่ายขึ้น และทำพฤติกรรมคล้ายๆ กับ Promises ถ้า Promises มีโครงสร้างคล้ายคลึงกับ callback สำหรับ async/await จะมีโครงสร้างคล้าย generators ผสมกับ promises โดย async function จะ return เป็น Promise *เสมอ* ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function))

> **หมายเหตุ :** คุณต้องเข้าใจก่อนว่า promise คืออะไร และทำงานยังไง ก่อนที่จะพยายามทำความเข้าใจ async / await

> **หมายเหตุ 2:** [*await* จะต้องใช้ใน *async* function](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9#f3f0), นั่นหมายความว่าคุณไม่สามารถใช้ await ใน top level ของโค้ดได้ ถ้ามันไม่ได้อยู่ใน async function.

#### โค้ดตัวอย่าง

```js
async function getGithubUser(username) { // คีย์เวิร์ด async ทำให้สามารถใช้ await ภายใน function ได้ นั่นหมายถึง function นี้ return เป็น promise
  const response = await fetch(`https://api.github.com/users/${username}`); // Execution จะหยุดที่ตรงนี้จนกว่า promise จะ return หลังจาก fetch แล้ว resolved
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user)) // log ข้อมูล response ของ user - ไม่สามารถใช้ syntax await ได้เพราะโค้ดไม่ได้เป็น async function
  .catch(err => console.log(err)); // ถ้า error มีการ thrown ใน async function จะสามารถ catch ได้ที่นี่
```

#### อธิบายเพิ่มเติมเกี่ยวกับโค้ดตัวอย่าง

*Async / Await* สร้างมาจาก promise แต่ว่าไม่ได้อนุญาตให้เขียนแบบโค้ดแบบ imperative style มากไปกว่านี้

*async* operator จะเปลี่ยน function เป็น asynchronous และจะ return เป็น *Promise* คุณสามารถใช้ *await* operator ใน *async* function เพื่อหยุดการ execution ที่บรรทัดนั้นๆ จนกว่า Promise จะ return ค่ากลับมาโดย resolves หรือ rejects

```js
async function myFunc() {
  // เราสามารถใช้ await operator เพราะ function นี้กำหนดเป็น async
  return "hello world";
}

myFunc().then(msg => console.log(msg)) // "hello world" -- ค่าที่คืนจาก function myFunc ถูกเปลี่ยนไปเป็น promise เพราะว่า async operator
```

เมื่อถึงบรรทัด *return* ของ async function ตัว Promise ที่ได้รับค่าแล้วจะ return กลับไป ถ้าเกิด error และมีการ thrown ข้างใน async function ตัว promise state จะถูกเปลี่ยนเป็น *rejected* และถ้าไม่มีค่า return จาก async function ตัว promise จะยังคง return และ resolve แบบไม่มีค่ากลับไปเมื่อ async function ทำงานเสร็จสมบูรณ์

*await* operator จะใช้สำหรับรอ *Promise* จนกว่าจะได้รับค่า และสามารถใช้ได้เฉพาะใน function ที่เป็น *async* เท่านั้น เมื่อโค้ด execution มาถึงจะหยุดจนกว่า promise จะได้รับการเติมเต็มข้อมูล

> **หมายเหตุ :** *fetch* เป็น function ที่ return เป็น Promise ที่สามารถทำ AJAX request

มาดูกันว่าเราสามารถใช้ fetch ข้อมูล github user ด้วย promises ยังไงได้บ้าง:

```js
function getGithubUser(username) {
  return fetch(`https://api.github.com/users/${username}`).then(response => response.json());
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

และอันนี้คือถ้ากรณีใช้ *async / await* จะเป็นยังไง:

```js
async function getGithubUser(username) { // ใช้งาน promise + await ร่วมกัน
  const response = await fetch(`https://api.github.com/users/${username}`); // Execution จะหยุดที่นี่จนกว่าข้อมูลใน Promise จะได้รับการเติมเต็ม
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

*async / await* syntax ทำให้เราสามารถเขียน promise แบบ chain ได้สะดวกสบายมากขึ้น

ยกตัวอย่างเช่น ถ้าเราต้องการ token เพื่อที่จะสามารถ fetch ข้อมูล blog post ที่อยู่ใน database เพื่อเอาข้อมูลคนเขียน เราจะสามารถให้มันทำตามลำดับได้:

> **หมายเหตุ :** *await* ต้องครอบด้วยวงเล็บเพื่อรอให้เรียก resolve และได้รับค่าก่อน ถึงจะนำไปใช้ต่อได้ถ้าเขียนในบรรทัดเดียวกัน

```js
async function fetchPostById(postId) {
  const token = (await fetch('token_url')).json().token;
  const post = (await fetch(`/posts/${postId}?token=${token}`)).json();
  const author = (await fetch(`/users/${post.authorId}`)).json();

  post.author = author;
  return post;
}

fetchPostById('gzIrzeo64')
  .then(post => console.log(post))
  .catch(err => console.log(err));
```

##### การจัดการกับ Error

ถ้าเราเพิ่ม *try / catch* blocks ครอบ *await* expressions, uncaught exceptions – ไม่ว่าอะไรก็ตามที่ thrown ภายใน *async* function หรือว่ามันโดนยกเลิกระหว่าง *await* – จะ reject ตัว promise return โดย *async* function. ใช้ `throw` statement ใน async function จะเหมือนกับ return ตัว Promise ที่ reject [(Ref: PonyFoo)](https://ponyfoo.com/articles/understanding-javascript-async-await#error-handling).

> **หมายเหตุ :** Promises เป็นแบบเดียวกัน!

เมื่อใช้ Promises เราจะสามารถจัดการกับ error chain ได้แบบนี้:

```js
function getUser() { // Promise อันนี้จะโดน rejected!
  return new Promise((res, rej) => rej("User not found !"));
}

function getAvatarByUsername(userId) {
  return getUser(userId).then(user => user.avatar);
}

function getUserAvatar(username) {
  return getAvatarByUsername(username).then(avatar => ({ username, avatar }));
}

getUserAvatar('mbeaudru')
  .then(res => console.log(res))
  .catch(err => console.log(err)); // "User not found !"
```

กรณีถ้าใช้ *async / await*:

```js
async function getUser() { // Promise ที่จะ return กลับไปจะ rejected!
  throw "User not found !";
}

async function getAvatarByUsername(userId) => {
  const user = await getUser(userId);
  return user.avatar;
}

async function getUserAvatar(username) {
  var avatar = await getAvatarByUsername(username);
  return { username, avatar };
}

getUserAvatar('mbeaudru')
  .then(res => console.log(res))
  .catch(err => console.log(err)); // "User not found !"
```

#### ข้อมูลเพิ่มเติมภายนอก

- [Async/Await - JavaScript.Info](https://javascript.info/async-await)
- [ES7 Async/Await](http://rossboucher.com/await/#/)
- [6 Reasons Why JavaScript’s Async/Await Blows Promises Away](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9)
- [JavaScript awaits](https://dev.to/kayis/javascript-awaits)
- [Using Async Await in Express with Node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)
- [Async Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
- [Using async / await in express with node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)

### Truthy / Falsy

ใน JavaScript ค่า truthy หรือ falsy เป็นค่าที่สามารถถูก casted ไปเป็น boolean เมื่ออยู่ในบริบทที่ต้องวัดเป็น boolean ยกตัวอย่างบริบทของ boolean เมื่อถูกนำไปใช้ใน ```if``` condition:

ค่าทั้งหมดสามารถแปลงเป็น ```true``` ยกเว้นแต่ว่ามันจะเป็นค่าเหล่านี้:

- false
- 0
- "" (empty string)
- null
- undefined
- NaN

นี่คือตัวอย่างของ *บริบทของ boolean*:

- การวัดค่าใน ```if``` condition

```js
if (myVar) {}
```

```myVar``` สามารถเป็นอะไรก็ได้ [first-class citizen](https://en.wikipedia.org/wiki/First-class_citizen) (ตัวแปร, function, boolean) แต่มันจะถูก casted ไปเป็น boolean เพราะว่ามันกำลังถูกว่าในบริบทของ boolean

- After logical **NOT** ```!``` operator

operator นี้จะ return false ถ้า operand สามารถถูก convert ไปเป็น true ได้ หรืออีกความหมายนึงคือ return true

```js
!0 // true -- 0 เป็น falsy ดังนั้นมันจะ returns true
!!0 // false -- 0 เป็น falsy ดังนั้น !0 จะ returns true และดังนั้น !(!0) จะ returns false
!!"" // false -- string ว่างเป็น falsy ดังนั้น NOT (NOT false) จะเท่ากับ false
```

- เมื่อใช้ *Boolean* object constructor

```js
new Boolean(0) // false
new Boolean(1) // true
```

- ในกรณีใช้ ternary evaluation

```js
myVar ? "truthy" : "falsy"
```

myVar ถูกวัดให้อยู่ในบริบทของ boolean

### Static Methods

#### อธิบายแบบสั้นๆ

คีย์เวิร์ด `static` สามารถใช้ใน class เพื่อประกาศเป็น static method ได้ ตัว static method เป็น function ใน class ที่เป็นของ class object จะไม่ใช่ของตัว instance ของ class นั้นๆ

#### โค้ดตัวอย่าง

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }
}

//หมายเหตุ เราไม่ได้มีการสร้าง instance จาก Repo class
console.log(Repo.getName()) //Repo name คือ modern-js-cheatsheet

let r = new Repo();
console.log(r.getName()) //Uncaught TypeError: repo.getName is not a function
```

#### อธิบายเพิ่มเติมโดยละเอียด

Static methods can be called within another static method by using the `this` keyword, this doesn't work for non-static methods though. Non-static methods cannot directly access static methods using the `this` keyword.
Static method สามารถเรียก static method ตัวอื่นโดยใช้คีย์เวิร์ด `this` ได้ซึ่งจะไม่สามารถทำได้สำหรับ non-static methods และ non-static methods จะไม่สามารถเข้าถึง static method โดยใช้คีย์เวิร์ด `this`

##### เรียก static methods อื่นจาก static method

To call a static method from another static method, the `this` keyword can be used like so;
เพื่อจะเรียก static method จาก static method อื่น ใช้คีย์เวิร์ด `this` แบบนี้ได้:

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  static modifyName(){
    return this.getName() + '-added-this'
  }
}

console.log(Repo.modifyName()) //Repo name คือ modern-js-cheatsheet-added-this
```

##### เรียก static methods อื่นจาก non-static method

Non-static methods สามารถเรียก static methods ได้ใน 2 ทาง;
1. ###### ใช้ชื่อ class.

เพื่อที่จะใช้ static method จาก non-static method เราใช้ชื่อ class และเรียก static method เหมือนเป็น property ตัวอย่างเช่น `ClassName.StaticMethodName`

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName(){
    return Repo.getName() + ' and it contains some really important stuff'
  }
}

// เราต้องสร้าง instance จาก class ขึ้นมาก่อนเพื่อใช้เป็น non-static methods
let r = new Repo()
console.log(r.useName()) //Repo name คือ modern-js-cheatsheet and it contains some really important stuff
```

2. ###### ใช้ constructor

Static methods สามารถเรียกเหมือนเป็น properties ได้ใน constructor object

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName(){
    //เรียก static method เหมือนเป็น property ของ constructor
    return this.constructor.getName() + ' and it contains some really important stuff'
  }
}

// เราต้องสร้าง instance จาก class ขึ้นมาก่อนเพื่อใช้เป็น non-static methods
let r = new Repo()
console.log(r.useName()) //Repo name คือ modern-js-cheatsheet and it contains some really important stuff
```

#### ข้อมูลเพิ่มเติมภายนอก
- [static keyword- MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static)
- [Static Methods- Javascript.info](https://javascript.info/class#static-methods)
- [Static Members in ES6- OdeToCode](http://odetocode.com/blogs/scott/archive/2015/02/02/static-members-in-es6.aspx)

## คำศัพธ์

### <a name="scope_def"></a> Scope

บริบทที่ค่าหรือ expression นั้น "มีตัวตน" หรือว่าสามารถอ้างอิงถึงได้ ถ้าตัวแปรหรือ expression ไม่ได้เป็น "อยู่ใน scope นั้นๆ" จะไม่สามารถใช้ได้

แหล่งอ้างอิง: [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

### <a name="mutation_def"></a> Variable mutation

หมายถึงตัวแปรที่ถูกการแปลงค่า (mutated) จากค่าตั้งต้นและถูกเปลี่ยนในภายหลัง

```js
var myArray = [];
myArray.push("firstEl") // myArray กำลังถูกแปลงค่า (mutated)
```

ตัวแปรจะถูกเรียกว่า *immutable* ถ้ามันไม่สามารถแปลงค่า (mutated) ได้

[อ่านบทความ MDN Mutable](https://developer.mozilla.org/en-US/docs/Glossary/Mutable) สำหรับข้อมูลเพิ่มเติม
