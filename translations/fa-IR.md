# برگه تقلب جاوااسکریپت مدرن

_توضیح مترجم: اگر این سند را روی گیت‌هاب می‌بینید قطعا با مشکل نمایش چپ‌به‌راست شما را آزار می‌دهد. به منظور عدم ایجاد مشکل در ساختار پرونده مارک‌داون، از وارد کردن برچسب‌های html در این سند خودداری کرده‌ام. برای نمایش در جهت صحیح، می‌توانید این سند را روی نمونه‌های گیت‌لب مشاهده کنید. بد نیست بدانید نزدیک به ۵ سال است افراد مختلفی درخواست افزودن پشتیبانی از متن راست‌به‌چپ را به گیت‌هاب داده‌اند که با بی‌محلی کامل توسعه‌دهندگان این بستر انحصاری مواجه شده است. می‌توانید شما هم در این درخواست بی نتیجه ادامه دهید و یا این که به یک بستر آزاد انتشار کد مانند گیت‌لب مهاجرت کنید._

## مقدمه

### انگیزه

این سند، یک برگه تقلب برای مسائلی در جاوااسکپت است که به دفعات در کار با پروژه‌های مدرن و جدیدترین نمونه‌های کد با آن‌ها مواجه خواهید شد.

این راهنما قصد ندارد جاوااسکریپت را از بیخ آموزش بدهد بلکه می‌خواهد کمکی باشد برای دانش مقدماتی توسعه‌دهندگانی که ممکن است به واسطه مفاهیم جاوااسکریپت به کار برده شده در کدهای مدرن (مثلا در یادگیری ری‌اکت) با آن‌ها دست و پنجه نرم کنند.

در کنار این، تلاش می‌کنم گاهی نکاتی شخصی را ارائه دهم که ممکن است بحث برانگیز باشند اما هر کجا به آن‌ها اشاره کنم، بیان خواهم کرد که آن موارد، پیشنهادهای شخصی‌ام هستند.

> **نکته:** بیشتر مفاهمیمی که اینجا معرفی می‌شوند از به‌روزرسانی زبان جاوااسکریپت (ES2015 یا آن‌طور که معمولا گفته می‌شود ES6) می‌آیند. می‌توانید ویژگی‌های جدیدی که در این به‌روزرسانی اضافه شده‌اند را [این‌ جا](http://es6-features.org/) پیدا کنید که بسیار خوب ارائه شده‌اند.

## منابع مکمل

پیشنهاد می‌کنم وقتی در درک یک مفهوم دچار مشکل می‌شوید، در منابع زیر دنبال پاسخ بگردید:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/search?q=)
- [You don't know JS (book)](https://github.com/getify/You-Dont-Know-JS)
- [Eloquent JavaScript (book)](https://eloquentjavascript.net)
- [Douglas Crockford's blog](https://www.crockford.com/javascript/)
- [ES6 Features with examples](http://es6-features.org)
- [Wes Bos blog (ES6)](http://wesbos.com/category/es6/)
- [Javascript Basics for Beginners](https://www.udacity.com/course/javascript-basics--ud804) - a free Udacity course
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) to find specific blog and resources
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)

## فهرست مطالب

- [برگه تقلب جاوااسکریپت مدرن](#برگه-تقلب-جاوااسکریپت-مدرن)
  - [مقدمه](#مقدمه)
    - [انگیزه](#انگیزه)
    - [منابع مکمل](#منابع-مکمل)
  - [فهرست مطالب](#فهرست-مطالب)
  - [مفاهیم](#notions)
    - [اعلان متغیر: var، const، let](#اعلان-متغیر-var-const-let)
      - [توضیح کوتاه](#توضیح-کوتاه)
      - [نمونه کد](#نمونه-کد)
      - [توضیح مبسوط](#توضیح-مبسوط)
      - [منابع خارجی](#منابع-خارجی)
    - [تابع پیکانی](#تابع-پیکانی)
      - [نمونه کد](#نمونه-کد-1)
      - [توضیح مبسوط](#توضیح-مبسوط-1)
        - [اختصار](#اختصار)
        - [ارجاع this](#ارجاع-this)
      - [منابع مفید](#منابع-مفید)
    - [مقدار پیش‌فرض پارامتر تابع](#مقدار-پیشفرض-پارامتر-تابع)
      - [منابع خارجی](#منابع-خارجی-1)
    - [تجزیه اشیاء و آرایه‌ها](#تجزیه-اشیاء-و-آرایهها)
      - [توضیح با مثال](#توضیح-با-مثال)
      - [منابع مفید](#منابع-مفید-1)
    - [متدهای آرایه - map / filter / reduce / find](#متدهای-آرایه-map-filter-reduce-find)
      - [نمونه کد](#نمونه-کد-2)
      - [توضیح](#توضیح)
        - [متد ‪Array.prototype.map()‬](#متد-arrayprototypemap)
        - [متد ‪Array.prototype.filter()‬](#متد-arrayprototypefilter)
        - [متد ‪Array.prototype.reduce()‬](#متد-arrayprototypereduce)
        - [متد ‪Array.prototype.find()‬](#متد-arrayprototypefind)
      - [منبع خارجی](#منبع-خارجی)
    - [عملگر گسترش «...»](#عملگر-گسترش-)
      - [نمونه کد](#نمونه-کد-3)
      - [توضیح](#توضیح-1)
        - [در شمارش‌پذیرها (مانند آرایه)](#در-شمارشپذیرها-مانند-آرایه)
        - [پارامتر باقی (rest) تابع](#پارامتر-باقی-rest-تابع)
        - [گسترش خاصیت‌های شیء](#گسترش-خاصیتهای-شیء)
      - [منابع خارجی](#منابع-خارجی-2)
    - [میان‌بر خاصیت شیء](#میانبر-خاصیت-شیء)
      - [توضیح](#توضیح-2)
      - [منابع خارجی](#منابع-خارجی-3)
    - [وعده‌ها (Promises)](#وعدهها-promises)
      - [نمونه کد](#نمونه-کد-4)
      - [توضیح](#توضیح-3)
        - [ساخت یک وعده](#ساخت-یک-وعده)
        - [به‌کارگیری گرداننده وعده](#بهکارگیری-گرداننده-وعده)
      - [منابع خارجی](#منابع-خارجی-4)
    - [قالب لفظی (Template literals)](#قالب-لفظی-template-literals)
      - [نمونه کد](#نمونه-کد-5)
      - [منابع خارجی](#منابع-خارجی-5)
    - [قالب لفظی برچسب‌دار](#قالب-لفظی-برچسبدار)
      - [منابع خارجی](#منابع-خارجی-6)
    - [درون‌ریزی / برون‌ریزی](#درونریزی-برونریزی)
      - [توضیح به همراه نمونه کد](#توضیح-به-همراه-نمونه-کد)
        - [برون‌ریزی بانام](#برونریزی-بانام)
        - [درون‌ریزی / برون‌ریزی پیش‌فرض](#درونریزی-برونریزی-پیشفرض)
      - [منابع خارجی](#منابع-خارجی-7)

## مفاهیم

### اعلان متغیر: var، const، let

در جاوااسکریپت سه کلیدواژه برای اعلان یک متغیر وجود دارند که هر یک دارای ویژگی‌های خاص خود هستند. این کلیدواژه‌ها عبارت‌اند از `var` و `let` و `const`.

#### توضیح کوتاه

متغیرهایی که با `const` اعلان می‌شوند را نمی‌توان دوباره مقداردهی کرد در حالی که اگر همان متغیر با `var` یا `let` تعریف می‌شد، امکان این کار فراهم می‌بود.

پیشنهاد می‌کنم همیشه متغیرهای خود را به طور پیش‌فرض با `const` تعریف کنید مگر این که بخواهید آن را بعدا تغییر داده یا مقداردهی کنید که در این حالت پیشنهادم استفاده از `let` است.

|     |قلمرو|قابل مقداردهی|قابل تغییر|محدوده مرگ زمانی|
| --- | --- | --- | --- | --- |
|const|بلوک|خیر|بله|بله|
|let|بلوک|بله|بله|بله|
|var|تابع|بله|بله|خیر|

#### نمونه کد
```javascript
const person = "Nick";
person = "John" // خطایی اعلام می‌شود که مقدار متغییر نمی‌تواند تغییر کند
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", بازمقداردهی مجاز است
```

#### توضیح مبسوط
[قلمرو]() یک متغیر تقریبا به این معناست که «این متغیر در کجای کد قابل دسترس است».

##### استفاده از var
متغیرهایی که با `var` اعلان می‌شوند *در قلمروی تابع* دردسترس‌اند به این معنا که وقتی متغیری در یک تابع تعریف شود، هر چیزی در آن تابع می‌توان به آن متغیر دسترسی داشه باشد. در کنار این، یک متغیر *در قلمروی تابع* که داخل یک تابع تعریف شده است نمی‌تواند خارج از آن تابع در دسترس باشد.

پیشنهاد می‌کنم تصور کنید که یک متغیر *در قلمروی X* مانند آن است که آن متغیر، یکی خصوصیت (property) X باشد.


```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - متغیر داخل تابع در دسترس است
}
console.log(myVar); // ReferenceError - متغیر خارج از تابع در دسترس نیست
```
و این مثال:

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // چون متغیر در قلروی تابع است، مقدارش با مقدار جدید جایگزین می‌شود.
  }
  console.log(myVar); // "John" - ببینید که دستورات داخل شرط چه طور روی مقدار این متغیر اثر می‌گذارد
}
console.log(myVar); // ReferenceError - متغیر خارج از تابع در دسترس نیست
```

افزون بر این، متغییرهایی که توسط `var` اعلان می‌شوند به بالای قلمرو در زمان اجرا منتقل می‌گردند.این چیزی است که آن را [var hoisting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting) می‌خوانیم.

این بخش از کد:

```js
console.log(myVar) // undefined -- no error raised
var myVar = 2;
```

در زمان اجرا به این شکل فهمیده می‌شود:

```js
var myVar;
console.log(myVar) // undefined -- no error raised
myVar = 2;
```

##### استفاده از let
شباهت‌هایی زیادی میان `let` و `var` وجود دارد اما متغیرهایی که با `let` تعریف می‌شوند:

- *در قلمروی بلوک* هستند
- پیش از مقداردهی قابل دسترسی **نیستند**
- نمی‌توانند در همان قلمرو بازاعلان شوند

بگذارید اثر تعریف متغیر در قلمروی بلوک را در همان مثال‌های پیشین ببینیم:

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // چون myVar یک متغیر در قلمروی بلوک است، در واقع یک متغیر جدید اعلان کرده‌ایم.
    // این متغیر خارج از این بلوک قابل دسترس نیست و در حقیقت، کاملا مستقل
    // از آن متغیر myVar است که اول تعریف شده بود.
  }
  console.log(myVar); // "Nick", ببینید که چه طور دستورات داخل شرط، تاثیری روی متغیر بیرون شرط ندارد
}
console.log(myVar); // ReferenceError - متغیر خارج از تابع قابل دسترس نیست
```

حال ببینیم که یعنی چه که متغیرهای `let` (و `const`) پیش از مقداردهی دسترسی نیستند:

```js
console.log(myVar) // ReferenceError !
let myVar = 2;
```

بر خلاف متغیرهای `var`، اگر تلاش کنید یک متغیر `let` یا `const` را پیش از مقداردهی بخوانید یا رویش بنویسید، خطا دریافت خواهید کرد. این پدیده معمولا با نام *محدوده مرگ زمانی* یا [*Temporal dead zone*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_Dead_Zone_and_errors_with_let) یا به اختصار *TDZ* خوانده می‌شود.

> **نکته:** از منظر فنی، اعلان‌های متغیر با `let` و `const` نیز بالاتر اجرا می‌شوند (hoist) اما مقداردهی‌شان نه. از همین رو که این گونه ساخته شده‌اند که تا پیش از مقداردهی، قابل استفاده نباشند این حس ایجاد می‌شود که گویی مورد hoist قرار نگرده‌اند در حالی که قرار گرفته‌اند. اگر می‌خواهید بیشتر بدانید، به [این توضیح بسیار مبسوط](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified) مراجعه کنید.

به علاوه، نمی‌توانید متغیرهای `let` را مجددا اعلان کنید:

```js
let myVar = 2;
let myVar = 3; // SyntaxError
```

##### استفاده از const

متغیرهای اعلان شده با `const` مشابه متغیرهای `let` رفتار می‌کنند با این تفاوت که قابل مقداردهی مجدد نیستند. به طور خلاصه، متغیرهای `const`:

- *در قلمروی بلوک* هستند
- پیش از مقداردهی قابل دسترسی نیستند
- نمی‌توانند در همان قلمرو بازاعلان شوند
- نمی‌توانند مقداردهی مجدد شوند

```js
const myVar = "Nick";
myVar = "John" // خطایی می‌بینید که مقداردهی مجدد ممکن نیست
```

```js
const myVar = "Nick";
const myVar = "John" // خطایی می‌بینید که اعلان مجدد ممکن نیست
```

اما یک نکته ظریف در این جا وجود دارد: متغیرهای `const` تغییرناپذیر یا immutable نیستند! به معنای دقیق‌تر، آرایه‌ها و شیءهایی که با `const` اعلان شده‌اند **می‌توانند** تغییر کنند.

برای شی‌ءها:

```js
const person = {
  name: 'Nick'
};
person.name = 'John' // کار می‌کند چون این متغیر کاملا مقداردهی نشده، می‌تواند تغییر کند
console.log(person.name) // "John"
person = "Sandra" // خطا دریافت خواهید کرد چون قابل مقداردهی مجدد نیست
```

برای آرایه‌ها:

```js
const person = [];
person.push('John'); // کار می‌کند چون این متغیر کاملا مقداردهی نشده، می‌تواند تغییر کند
console.log(person[0]) // "John"
person = ["Nick"] // خطا دریافت خواهید کرد چون قابل مقداردهی مجدد نیست
```

#### منابع خارجی


- [How let and const are scoped in JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Temporal Dead Zone (TDZ) Demystified](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### تابع پیکانی

در به‌روزرسانی ES6 جاوااسکریپت، *توابع پیکانی* یا Arrow Function معرفی شدند که روشی دیگری برای اعلان و استفاده از توابع هستند. برخی از فواید این نوع توابع عبارت‌اند از:

- مختصرتر هستند
- مقدار *this* از محیط برداشته می‌شود
- بازگشت تلویحی

#### نمونه کد

- اختصار و بازگشت تلویحی

```js
function double(x) { return x * 2; } // روش سنتی
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // همان تابع به صورت تابع پیکانی با مقدار بازگشتی تلویحی
console.log(double(2)) // 4
```

- ارجاع *this*

در تابع پیکانی، *this* معادل مقدار *this* در بافتار اجرای محاط بر تابع است. اساسا با توابع پیکانی شما نیازی به ترفند `that = this` پیش از فراخوانی تابع دیگری داخل یک تابع ندارید.

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### توضیح مبسوط

##### اختصار

توابع پیکانی در قیاس با توابع سندی به روش‌های زیادی مختصرتر هستند. بگذارید همه حالت‌های ممکن را مرور کنیم:

- بازگشت تصریحی در مقابل تلویحی

**بازگشت تصریحی** تابعی است که در آن کلیدواژه *return* در بدنه تابع استفاده شده باشد.

```js
  function double(x) {
    return x * 2; // صریحا از کلیدواژه بازگشت استفاده شده است
  }
```

در روش سنتی نوشتن تابع، بازگشت همیشه صریح بوده است. اما با توابع پیکانی، می‌توانید *بازگشت تلویحی* داشه باشید که یعنی برای بازگرداندن یک مقدار، نیازی به استفاده از کلیدواژه *return* ندارید.

```js
  const double = (x) => {
    return x * 2; // بازگشت صریح
  }
```

از آن جایی که این تابع فقط چیزی را بر می‌گرداند (فاقد هر گونه دستورالعملی پیش از کلیدواژه *return* است) می‌توانیم از بازگشت تلویحی استفاده کنیم.

```js
  const double = (x) => x * 2;
```

برای این منظور کافی است که کلیدواژه **return** و **گیومه‌ها را برداریم**. به همین دلیل است که این روش، بازگشت *تلویجی* خوانده می‌شود. کلیدواژه *return* وجود ندارد اما این تابع در واقع مقدار `x * 2` را برمی‌گرداند.

> **توجه:** اگر تابع شما مقداری (با *اثر جانبی*) بر نمی‌گرداند، در حقیقت بازگشت تلویحی یا تصریحی انجام نمی‌دهد.

در کنار این، اگر شما بخواهید تلویحا یک *شیء* را برگردانید **لازم است که آن را در پرانتز قرار دهید** چون در غیر این صورت، با آکولادهای بلوک دچار تداخل می‌شود.

```js
const getPerson = () => ({ name: "Nick", age: 24 })
console.log(getPerson()) // { name: "Nick", age: 24 } -- شیء به صورت تلویحی با کمک تابع پیکانی بازگشت داده شده است
```

- تنها یک آرگومان

اگر تابع شما تنها یک پارامتر دریافت می‌کند می‌توانید پرانتز را از اطراف آن بردارید. اگر کد **double** بالایی را در نظر بگیریم:

```js
  const double = (x) => x * 2; // این تابع پیکانی تنها یک پارامتر دریافت می‌کند
```

پرانتزهای اطراف پارامتر می‌توانند برداشته شوند.

```js
  const double = x => x * 2; // این تابع پیکانی تنها یک پارامتر دریافت می‌کند
```

- بدون آرگومان

وقتی ورودی‌ای به تابع پیکانی وجود ندارد باید یک جفت پرانتز وارد کنید مگر نه خطای نحوی دریافت خواهید کرد.

```js 
  () => {
   // پرانتز درج شده و همه چیز درست کار می‌کند
    const x = 2;
    return x;
  }
```

```js
  => {
   // پرانتز درج نشده و کد اجرا نخواهد شد
    const x = 2;
    return x;
  }
```

##### ارجاع *this*

برای درک این ویژگی تازه معرفی شده همراه توابع پیکانی لازم است بدانید که **this** چگونه در جاوااسکریپت رفتار می‌کند.

در یک تابع پیکانی، *this* معادل *this* در بافتار اجرایی محاط بر تابع است. این یعنی که تابع پیکانی به جای ایجاد یک *this* جدید، آن را از محیطی که در آن احاطه شده می‌قاپد.

بدون تابع پیکانی اگر شما بخواهید از طریق *this* به یک متغیر در تابعی داخل یک تابع دسترسی پیدا کنید لازم است که از ترفند *that = this* یا *self = this* استفاده کنید.

به عنوان مثال، استفاده کردن از تابع setTimeout داخل تابع myFunc:

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // that = this trick
  setTimeout(
    function() { // یک‫ this جدید در قلمروی این تابع ساخته می‌شود
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // undefined -- اعلان تابع را ببینید
    },
    0
  );
}
```

اما با تابع پیکانی، *this* از محیط پیرامونی‌اش گرفته می‌شود:

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => {
    // اینجا this از محیط پیرامونی‌اش یعنی تابع myFunc گرفته می‌شود
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

#### منابع مفید

- [Arrow functions introduction - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript arrow function - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)


### مقدار پیش‌فرض پارامتر تابع

از به‌روزرسانی ES2015 جاوااسکریپت می‌توانید با نحو زیر، مقدار پیش‌فرض برای پارامترهای تابع تنظیم کنید:

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10
console.log(myFunc(5)) // 5

console.log(myFunc(undefined)) // 10
console.log(myFunc(null)) // null
```

پارامتر پیش‌فرض تنها در دو و فقط دو موقعیت اعمال می‌شود:

- پارامتری ارائه نشده باشد
- پارامتر *undefined* ارائه شده باشد

به بیان دیگر، اگر مقدار *null* را به پارامتر پیش‌فرض بدهید، این مقدار **اعمال نخواهد شد**.

> **نکته:** تخصیص مقدار پیش‌فرض می‌تواند با پارامترهای destructured هم استفاده شود (مفهوم بعدی را برای مثال ببینید)

#### منابع خارجی

- [Default parameter value - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Default parameters - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

### تجزیه اشیاء و آرایه‌ها

*تجزیه* (destructuring) روشی آسان برای ساخت متغیرهای جدید از راه استخراج مقادیر از داده‌های ذخیره شده در اشیاء یا آرایه‌هاست.

به عنوان مثال، *تجزیه کردن* می‌تواند به منظور تجزیه پارامترهای تابع و یا *this.props* در پروژه‌های ری‌اکت مورد استفاده قرار گیرد.

#### توضیح با مثال

- شیء

بگذارید شیء زیر را برای تمام مثال‌ها در نظر بگیریم:

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

بدون تجزیه کردن:

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

با تجزیه کردن، تماما در یک خط:

```js
const { firstName: first, age, city = "Paris" } = person; // همین و بس

console.log(age) // 35 -- ‫متغیر جدید age ساخته شده و معادل است با person.age 
console.log(first) // "Nick" -- ‫متغیر جدید first ساخته شده و معادل است با person.firstName
console.log(firstName) // ReferenceError -- ‫در واقع person.firstName وجود دارد اما نام متغیر جدیدی که ساخته شده،first است
console.log(city) // "Paris" -- ‫متغیر جدیدی به نام city ساخته شده است اما چون person.city تغیرنشده است، مقدار موجود در city برابر است با مقدار پیش‌فرض ارائه شده یعنی Paris
```

**نکته:** آکولادهای استفاده شده در `const { age } = person` بعد از *const* نه برای اعلان شیء یا بلوک بلکه به عنوان نحو تجزیه نوشته شده است.

- پارامترهای تابع

*تجزیه کردن* معمولا برای تجزیه پارامترهای شیء در توابع استفاده می‌شود.

بدون تجزیه کردن

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

با تجزیه کردن پارامتر *person* شیء، ما به یک تابع جمع و جورتر دست پیدا می‌کنیم:

```js
function joinFirstLastName({ firstName, lastName }) { // ‫ما متغیرهای firstName و lastName را با تجزیه پارامترهای شیء person به دست می‌آوریم
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

استفاده از تجزیه به خصوص در زمان استفاده از توابع پیکانی، شیرین‌تر هم می‌شود:

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```


- آرایه

آرایه زیر را در نظر بگیریم:

```js
const myArray = ["a", "b", "c"];
```

بدون تجزیه کردن

```js
const x = myArray[0];
const y = myArray[1];
```

با تجزیه کردن

```js
const [x, y] = myArray; // همین و پس

console.log(x) // "a"
console.log(y) // "b"
```

#### منابع مفید

- [ES6 Features - Destructuring Assignment](http://es6-features.org/#ArrayMatching)
- [Destructuring Objects - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destructuring](http://exploringjs.com/es6/ch_destructuring.html)

### متدهای آرایه - map / filter / reduce / find

خواستگاه متدهای *Map*، *filter*، *reduce* و *find* برای آرایه، یک پارادایم برنامه‌نویسی به نام برنامه‌نویسی تابعی یا [*functional programming*](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0) است.

به طور خلاصه:

- متد ‪**Array.prototype.map()** ‬ یک آرایه دریافت می‌کند، کاری روی تک تک اعضای آن انجام می‌دهد و آرایه‌ای حاوی اعضای تغییریافته باز می‌گرداند.
- متد ‪**Array.prototype.filter()** ‬ یک آرایه دریافت می‌کند، عضو به عضو پیش می‌رود و تصمیم می‌گیرد که آیا آن عضو در آرایه‌ای که بازگشت داده خواهد شد باقی بماند یا خیر. نهایتا هم یک آرایه از اعضای تایید شده را باز می‌گرداند.
- متد ‪**Array.prototype.reduce()** ‬ یک آرایه دریافت ی‌کند اعضای آن را روی هم ریخته و به صورت یک مقدار واحد باز می‌گرداند.
- متد ‪**Array.prototype.find()** ‬ یک آرایه دریافت می‌کند و اولین عضوی را که شرط اعلام شده را داشته باشد باز می‌گرداند.

پیشنهاد می‌کنم که تا می‌توانید از اصول برنامه‌نویسی تابعی بهره ببرید زیرا قابل ترکیب، موجز و زیبا هستند.

با این چهار متدی که اشاره شد، می‌توانید در موارد بسیاری از به کار بردن حلقه *for* و *forEach* اجتناب کنید. به جای حلقه *for* سعی کنید از ترکیب این چهار متد استفاده کنید. شاید در نگاه اول قدری چالش برانگیز باشد. طبیعی است چون لازم است روش جدیدی برای اندیشیدن را فرابگیرید. اما وقتی این مهارت را فرابگیرید، کارها آسان‌تر می‌شوند.

#### نمونه کد

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
const doubledNumbers = numbers.map(n => n * 2); // [0, 2, 4, 6, 8, 10, 12]
const evenNumbers = numbers.filter(n => n % 2 === 0); // [0, 2, 4, 6]
const sum = numbers.reduce((prev, next) => prev + next, 0); // 21
const greaterThanFour = numbers.find((n) => n>4); // 5
```
محاسبه مجموع نمرات دانش‌آموزانی که نمره ۱۰ یا بالاتر گرفته‌اند با کمک ترکیب متدهای map و filter و reduce:

```js
const students = [
  { name: "Nick", grade: 10 },
  { name: "John", grade: 15 },
  { name: "Julia", grade: 19 },
  { name: "Nathalie", grade: 9 },
];

const aboveTenSum = students
  .map(student => student.grade) // ‫ما آرایه student را روی آرایه‌ای از نمره‌های‌شان نگاشت (map) کردیم
  .filter(grade => grade >= 10) // ‫ما آرایه grades را به منظور نگه‌داشتن نمره‌های ۱۰ و بالاتر مورد پالایش (filter) قرار دادیم
  .reduce((prev, next) => prev + next, 0); // همه نمره‌های ۱۰ و بالاتر را یک به یک با هم جمع کردیم 

console.log(aboveTenSum) // 44 -- 10 (Nick) + 15 (John) + 19 (Julia), Nathalie below 10 is ignored
```

#### توضیح

بیایید آرایه اعداد زیر را به عنوان مثلا در نظر بگیریم:

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
```

##### متد ‪Array.prototype.map()

```js
const doubledNumbers = numbers.map(function(n) {
  return n * 2;
});
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

چه شد؟ ما از متد ‪.map‬ روی آرایه *numbers* استفاده می‌کنیم. این متد می‌آید و روی یکایک اعضای آرایه حرکت می‌کند و مقدار آن‌ها را به تابع ما می‌دهد. هدف این تابع، تولید و بازگرداندن مقداری جدید بر اساس مقداری است که به آن داده شده و در نتیجه متد نگاشت (map)‌ می‌تواند مقدار جدید را جایگزین کند.

بگذارید فقط برای این مثال، این تابع را باز کرده و واضح‌ترش کنیم:

```js
const doubleN = function(n) { return n * 2; };
const doubledNumbers = numbers.map(doubleN);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

**نکته:** شما به دفعات خواهید دید که این متد در ترکیب با توابع پیکانی استفاده می‌شود.

```js
const doubledNumbers = numbers.map(n => n * 2);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

در این جا، ```numbers.map(doubleN)``` آرایهٔ ```[doubleN(0), doubleN(1), doubleN(2), doubleN(3), doubleN(4), doubleN(5), doubleN(6)]``` تولید می‌کند که معادل است با ```[0, 2, 4, 6, 8, 10, 12]```.

> **نکته:** اگر به جای بازگرداندن آرایه جدید فقط به دنبال ایجاد یک حلقهٔ دارای اثر جانبی هستید احتمالا باید به سراغ همان for یا forEach بروید نه map.

##### متد ‪Array.prototype.filter()

```js
const evenNumbers = numbers.filter(function(n) {
  return n % 2 === 0; // ‫اگر n زوج باشد مقدار true و در غیر این صورت false
});
console.log(evenNumbers); // [0, 2, 4, 6]
```

**نکته:** شما به دفعات خواهید دید که این متد در ترکیب با توابع پیکانی استفاده می‌شود.

```js
const evenNumbers = numbers.filter(n => n % 2 === 0);
console.log(evenNumbers); // [0, 2, 4, 6]
```

ما از متد ‪.filter‬ روی آرایه *numbers* استفاده می‌کنیم. این متد روی یکایک اعضای آرایه حرکت کرده و آن‌ها را به تابع ما می‌دهد. هدف تابع این است که یک مقدار بولی بازگرداند که مبنای تصمیم ما برای نگه داشتن آن عضو است. نهایتا filter آرایه‌ای از مقادیری را که نگه‌داشته است باز می‌گرداند.

##### متد ‪Array.prototype.reduce()

هدف متد کاهش (reduce) حرکت روی یکایک اعضای یک آرایه و کاستن آن‌ها به یک مقدار واحد است. این که چه طور این اعضا روی هم ریخته شوند به شما بستگی دارد.

```js
const sum = numbers.reduce(
  function(acc, n) {
    return acc + n;
  },
‪  0 // این، مقدار متغیر انباشت‌گر در نخستین گام محاسبه است
);

console.log(sum) // 21
```

**نکته:** شما به دفعات خواهید دید که این متد در ترکیب با توابع پیکانی استفاده می‌شود.

```js
const sum = numbers.reduce((acc, n) => acc + n, 0);
console.log(sum) // 21
```

درست هماهنند متدهای map و filter، متد reduce روی یک آرایه اعمال شده و یک تابع را به عنوان اولین پارامتر دریافت می‌کند.

این بار اما تفاوت‌هایی وجود دارد:

- متد ‪.reduce‬ دو پارامتر دریافت می‌کند

اولی پارامتر یک تابع است که در هر گام از حرکت روی اعضای آرایه فراخوانده می‌شود.

پارامتر دوم، مقدار متغیر انباشت‌گر (در این جا *acc*) در نخستین گام محاسبه است (برای فهمیدن، مورد بعدی را بخوانید).

- پارامترهای تابع

تابعی که به عنوان اولین پارامتر به ‪.reduce‬ می‌دهید دو پارامتر می‌خواهد. اولی (در این جا *acc*) متغیر انباشت‌گر و دومین پارامتر (*n*) عضو جاری آرایه است.

متغیر انباشت‌گر برابر است با مقدار بازگشت داده شده از تابع در گام **قبلی** محاسبه. در اولین گام از محاسبه، *acc* برابر است با مقداری که در دومین پارامتر ‪.reduce‬ وارد شده است.

###### در گام نخست

مقدار acc برابر صفر است زیرا در دومین پارامتر reduce مقدار صفر وارد شده است.

مقدار n هم صفر است چون اولین عضو آرایه *number* چنین مقداری دارد.

تابع، مقدار ‪*acc* + *n* --> 0 + 0 --> 0‬ را برمی‌گرداند.

###### در گام دوم

مقدار acc برابر صفر است چون تابع ما در مرحله قبل این مقدار را بازگردانده بود.

این بار n برابر یک است که دومین عضو آرایه *number* است.

این بار تابع مقدار ‪*acc* + *n* --> 0 + 1 --> 1‬ را بازمی‌گرداند.

###### در گام سوم

مقدار acc برابر یک است زیرا تابع ما در مرحله قبل این مقدار را بازگردانده بود.

این بار n برابر با ۲ است که سومین عضو آرایه *number* است.

تابع، مقدار ‪*acc* + *n* --> 1 + 2 --> 3‬ را باز می‌گرداند.


###### در چهارمین گام

مقدار acc برابر ۳ است زیرا تابع ما در مرحله قبل این مقدار را بازگردانده بود.

این بار n برابر با ۳ است که چهارمین عضو آرایه *number* است.

تابع، مقدار ‪*acc* + *n* --> 3 + 3 --> 6‬ را باز می‌گرداند.


###### نهایتا در آخرین گام

مقدار acc برابر ۱۵ است زیرا تابع ما در مرحله قبل این مقدار را بازگردانده بود.

مقدار n برابر با ۶ است که آخرین عضو آرایه *number* است.

تابع، مقدار ‪*acc* + *n* --> 15 + 6 --> 21‬ را باز می‌گرداند.

از آن جایی که این، آخرین گام محاسبه است، متد **‪.reduce‬** مقدار ۲۱ را باز می‌گرداند.

##### متد ‪Array.prototype.find()

```js
const greaterThanZero = numbers.find(function(n) {
  return n > 0; // return number just greater than 0 is present
});
console.log(greaterThanZero); // 1
```

**نکته:** شما به دفعات خواهید دید که این متد در ترکیب با توابع پیکانی استفاده می‌شود.

اینجا از متد یافتن یا find روی آرایه *numner* استفاده می‌کنیم. این متد روی یکایک اعضای آرایه حرکت کرده و تا زمانی که شرط تعیین شده برقرار شود آن‌ها را به تابع ما می‌دهد. هدف تابع، بازگرداندن عنصری است که روی آن، شرط موجود در تابع آزمون جاری محقق شود. متد find یک تابع callback را به ازای هر اندیس از آرایه و تا زمانی که آن تابع یک مقدار درست یا true را باز گرداند اجرا می‌کند.

**نکته:** این متد به محض پیدا کردن عضوی از آرایه که شرط مشخص شده را محقق می‌کند، مقدارش را باز می‌گرداند. در غیر این صورت مقدار undefined را باز خواهد گرداند.

#### منبع خارجی

- [Understanding map / filter / reduce in JS](https://hackernoon.com/understanding-map-filter-and-reduce-in-javascript-5df1c7eee464)

### عملگر گسترش «...»

عملگر گسترش `...` (spread) با ES2015 معرفی شد و برای گستردن عناصر یک متغیر قابل شمارش یا iterable (مانند یک آرایه) به مکان‌هایی است که چندین عنصر قابل جای‌گذاری هستند.

#### نمونه کد

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

#### توضیح

##### در شمارش‌پذیرها (مانند آرایه)

اگر دو آرایه زیر را داشته باشیم:

```js
const arr1 = ["a", "b", "c"];
const arr2 = [arr1, "d", "e", "f"]; // [["a", "b", "c"], "d", "e", "f"]
```

در آرایه *arr2*، اولین عضو ما یک آرایه است چرا که *arr1* همان‌گونه که هست در *arr2* تزریق شده است. اما چیزی که می‌خواهیم این است که *arr2*، آرایه‌ای از حروف باشد. برای این منظور می‌توانید عناصر *arr1* را در *arr2* *گسترش* دهیم.

با عملگر گسترش

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

##### پارامتر باقی (rest) تابع

در پارامترهای تابع می‌توانیم از عملگر باقی (rest) به منظور تزریق پارامترها به آرایه‌ای که رویش بتوانیم حلقه اجرا کنیم بهره می‌بریم. همواره یک شیء **arguments** همراه با هر تابعی وجود دارد که برابر است با آرایه‌ای از تمام پارامترهایی که به آن تابع حواله شده‌اند.

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

اما حالتی را در نظر بگیرید که بخواهیم این تابع یک دانشجوی جدید همراه با معدل نمره‌هایش بسازد. آیا راحت‌تر نیست که که فقط دو پارامتر اول را استخراج کنیم و در دو متغیر مجزا قرار داده و سپس تمام نمره‌ها را آرایه‌ای بریزیم که بشود روی آن شمارش انجام داد؟

این دقیقا همان کاری است که عملگر باقی به ما اجازهٔ انجامش را می‌دهد!

```js
function createStudent(firstName, lastName, ...grades) {
  // firstName = "Nick"
  // lastName = "Anderson"
‪  // [10, 12, 6]
  // به کمک «...» تمام دیگر پارامترهای را دریافت و در آرایه «grades» ذخیره می‌کنیم

  const avgGrade = grades.reduce((acc, curr) => acc + curr, 0) / grades.length; //‫ معدل نمره‌های موجود در آرایه grades را محاسبه می‌کند

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

> **نکته:** تابع createStudent تابع بدی است زیرا بررسی نمی‌کنیم که اساسا grades.length وجود دارد یا خیر و یا متفاوت از صفر است یا نه. اما چون خوانایی آن به این شکل بهتر بود، آن را این گونه نوشتم.

##### گسترش خاصیت‌های شیء

برای این مورد پیشنهاد می‌کنم توضیحات قبلی را درباره عملگر باقی بر روی پارامترهای تابع و عناصر شمارش‌پذیر (iterables) بخوانید.

```js
const myObj = { x: 1, y: 2, a: 3, b: 4 };
const { x, y, ...z } = myObj; // تجزیه شیء
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

// متغیر z حاوی باقی مقادیر حاصل از تجزیهٔ شیء است: شیء myObj منهای مقادیر تجزیه شدهٔ x و y

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }

// اینجا z حاوی خاصیت‌های شیء است که در n گسترانده می‌شود.
```

#### منابع خارجی

- [TC39 - Object rest/spread](https://github.com/tc39/proposal-object-rest-spread)
- [Spread operator introduction - WesBos](https://github.com/wesbos/es6-articles/blob/master/28%20-%20Spread%20Operator%20Introduction.md)
- [JavaScript & the spread operator](https://codeburst.io/javascript-the-spread-operator-a867a71668ca)
- [6 Great uses of the spread operator](https://davidwalsh.name/spread-operator)

### میان‌بر خاصیت شیء

در زمان نسبت دادن یک متغیری به یک خاصیت شیء، اگر هر دو دارای نام یک‌سان باشند می‌توانیم این کار را انجام دهیم:

```js
const x = 10;
const myObj = { x };
console.log(myObj.x) // 10
```

#### توضیح

معمولا (پیش از ES2015) زمانی که یک *object literal* جدید تعریف می‌کنیم و بخواهیم متغیرها را به عنوان مقادیر خاصیت‌های شیء استفاده کنیم، باید چنین کدی بنویسیم:

```js
const x = 10;
const y = 20;

const myObj = {
  x: x, // ‫نسبت دادن مقدار متغیر x به myObj.x
  y: y // ‫نسبت دادن مقدار متغیر y به myObj.y
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```
همان‌طور که می‌بینید، این کار خیلی تکراری است زیرا نام خاصیت‌های myObj دقیقا همان نام‌های متغیرهایی است که می‌خواهیم نسبت دهیم.

با معرفی ES2015، اگر نام متغیر همان نامی خاصیت باشد می‌توانیم از این روش میان‌بر استفاده کنیم:

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

#### منابع خارجی

- [Property shorthand - ES6 Features](http://es6-features.org/#PropertyShorthand)

### وعده‌ها (Promises)

وعده یا promise یک شیء است که می‌تواند به صورت هم‌گام از یک تابع ناهم‌گام بازگردانده شود. ([ارجاع](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261#3cd0)).

وعده‌ها می‌توانند برای پرهیز از دوزخ callback یا [callback hell](http://callbackhell.com/) استفاده شوند که در پروژه‌های مدرن جاوااسکریپت به کرات بروز می‌کنند.


#### نمونه کد

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

#### توضیح

وقتی که یک *درخواست ای‌جکس* می‌فرستید، پاسخ به‌هنگام یا هم‌گام نیست زیرا زمانی طول می‌کشد تا پاسخ این درخواست دریافت شود. حتی ممکن است به به دلیل دردسترس نبودن خدمت مورد نظر، این پاسخ هرگز به دست ما نرسد.

برای مدیریت چنین شرایطی، ES2015 *وعده‌ها* یا Promises را به ما هدیه داده است. وعده‌ها می‌توانند یکی از سه حالت وضعیت را داشته باشند:

- معلق (Pending)
- محقق شده (Fulfilled)
- رد شده (Rejected)

در نظر بگیرید که می‌خواهیم از وعده‌ها برای مدیریت یک درخواست ای‌جکس برای واکشی منبع X استفاده کنیم.

##### ساخت یک وعده

ابتدا یک وعده را می‌سازیم. از متد get جی‌کوئری برای فرستادن درخواست ای‌جکش به X استفاده خواهیم کرد.

```js
const xFetcherPromise = new Promise( // ‫با کلیدواژه new یک وعده می‌سازیم و آن را در یک متغیر ذخیره می‌کنیم
  function(resolve, reject) { //‫ سازنده وعده یک پارامتر تابع دریافت می‌کند که خودش دو پارامتر resolve و reject دارد
    $.get("X") // درخواست ای‌جکس را می‌فرستیم
      .done(function(X) { //‫ وقتی درخواست فرستاده شد...
        resolve(X); //‫ ...وعده با مقدار X به عنوان پارامتر رفع می‌شود
      })
      .fail(function(error) { //‫ اگر درخواست با شکست مواجه شود...
        reject(error); //‫ ...وعده با خطایی به عنوان پارامتر رد می‌شود
      });
  }
)
```

همان طور که در مثال بالا دیده می‌شود، شیء Promise یک تابع *اجراکننده* (executor) دریافت می‌کند که خودش دو پارامتر **resolve** و **reject** می‌گیرد. این پارامترها توابعی هستند که وقتی صدا زده شوند، متناسب با شرایطی که حادث می‌شود وضعیت وعده را به *محقق شده* یا *رد شده* تغییر می‌دهند.

وعده بعد از این جا ساخته می‌شود وارد وضعیت معلق می‌شود و تابع *اجرا کننده* بلادرنگ اجرا می‌شود. به محض صدا زده شدن *resolve* یا *reject* در تابع اجرا کننده، وعده اقدام به فراخوانی گرداننده (handler) مرتبط می‌کند.

##### به‌کارگیری گرداننده وعده

برای دریافت نتیجه (یا خطای) وعده بایستی به این شکل گرداننده‌ای به آن الصاق کنیم:

```js
xFetcherPromise
  .then(function(X) {
    console.log(X);
  })
  .catch(function(err) {
    console.log(err)
  })
```

اگر وعده با موفقیت انجام شود، *resolve* اجرا شده و تابعی به صورت پارامتر ‪`.then`‬ وارد شده است اجرا خواهد شد.

اگر به شکست بخورد، *reject* اجرا شده و تابعی که به صورت پارامتر به ‪`.catch`‬ وارد شده است اجرا خواهد شد.

> **نکته:** اگر وعده پیش از الصاق گرداننده، محقق یا رد شده باشد، گرداننده فراخوانده خواهد شد. مسابقه‌ای بین کامل شدن عملیات ناهم‌گام و الصاق شدن گرداننده‌های آن نیست. [ارجاع](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise#Description)

#### منابع خارجی

- [JavaScript Promises for dummies - Jecelyn Yeen](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [JavaScript Promise API - David Walsh](https://davidwalsh.name/promises)
- [Using promises - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [What is a promise - Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- [JavaScript Promises: an Introduction - Jake Archibald](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
- [Promise documentation - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

### قالب لفظی (Template literals)

قالب لفظی یک «درج عبارت» یا [*expression interpolation*](https://en.wikipedia.org/wiki/String_interpolation) برای رشته‌های تک یا چندخطی است.

به عبارت دیگر، یک نحو جدید رشته است که در آن می‌توانید به راحتی هر گونه عبارت (مثلا متغیرها) جاوااسکریپتی را استفاده کنید.

#### نمونه کد

```js
const name = "Nick";
`Hello ${name}, the following expression is equal to four : ${2+2}`;

// Hello Nick, the following expression is equal to four: 4
```

#### منابع خارجی

- [String interpolation - ES6 Features](http://es6-features.org/#StringInterpolation)
- [ES6 Template Strings - Addy Osmani](https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

### قالب لفظی برچسب‌دار

برچسب‌های قالب *توابعی هستند که می‌توانند به صورت پیش‌وند به [قالب‌های لفظی](#قالب-لفظی-template-literals) متصل شوند*. وقتی یک تابع به این روش صدا زده می‌شود اولین پارامتر، یک آرایه از *رشته‌ها* است که بین متغیرهای درج قالب ظاهرا می‌شوند و پارامتر بعدی مقادری است که باید درج شوند. از یک عملگر گسترش `...` برای دستیابی به همه آن‌ها بهره ببرید. [(مرجع)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#Tagged_template_literals).

> **نکته:** کتابخانه معروفی به نام [styled-components](https://www.styled-components.com/) به شدت به این ویژگی متکی است.

این مثالی است از این که این قابلیت چگونه کار می‌کند:

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

مثالی جالب‌تر:

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

#### منابع خارجی
- [Wes Bos on Tagged Template Literals](http://wesbos.com/tagged-template-literals/)
- [Library of common template tags](https://github.com/declandewet/common-tags)

### درون‌ریزی / برون‌ریزی

پیمانه‌ها (modules) در ES6 این امکان را فراهم می‌آورند که بتوان به متغیرها و توابعی که توسط یک پیمانه صریحا برون‌ریزی شده‌اند از پیمانه‌ای دیگر که آن پیمانه را درون‌ریزی می‌کنند دسترسی داشت.

قویا پیشنهاد می‌کنم به منابع موجود روی MDN درباره درون‌ریزی/برون‌ریزی یا import/export (به منابع خارجی این بخش رجوع کنید) نگاهی داشته باشید که هم سرراست است و هم کامل.

#### توضیح به همراه نمونه کد

##### برون‌ریزی بانام

برون‌ریزی بانام برای برون ریزی مقادیر از یک پیمانه مورد استفاده قرار می‌گیرد.

> **نکته:** فقط می‌توانید [first-class citizens](https://en.wikipedia.org/wiki/First-class_citizen) که دارای نام هستند را به صورت بانام برون‌ریزی کنید.

```js
// mathConstants.js
export const pi = 3.14;
export const exp = 2.7;
export const alpha = 0.35;

// -------------

// myFile.js
import { pi, exp } from './mathConstants.js'; // درون‌ریزی نام‌دار -- با نحوی مشابه تجزیه کردن
console.log(pi) // 3.14
console.log(exp) // 2.7

// -------------

// mySecondFile.js
import * as constants from './mathConstants.js';
// تزریق همه مقادیر برون‌ریزی شده به متغیر constants
console.log(constants.pi) // 3.14
console.log(constants.exp) // 2.7
```

در حالی که درون‌ریزی‌های نام‌دار شبیه به *تجزیه کردن* به نظر می‌رسند، اما دارای نحوی متفاوت بوده و مشابه آن نیستند. آن‌ها نه از مقادیر پیش‌فرض پشتیبانی مي‌کنند و نه از تجزیه کردن *عمیق*.

در کنار این، شما می‌توانید از مترادف‌ها (alias) استفاده کنید اما قواعد نحوی با آن چه که در تجزیه کردن وجود دارد متفاوت است.

```js
import { foo as bar } from 'myFile.js';
// در این جا foo درون‌ریزی شده و در متغیر جدیدی به نام bar تزریق شده است.
```

##### درون‌ریزی / برون‌ریزی پیش‌فرض

نظر به برون‌ریزی پیش‌فرض، هر پیمانه تنها می‌تواند یک برون‌ریزی پیش‌فرض داشته باشد. این برون‌ریزی پیش‌فرض می‌تواند یک تابع، یک کلاس، یک شیء و یا هر چیز دیگری باشد. این مقدار مقدار برون‌ریزی اصلی (main) شناخته می‌شود چرا که راحت‌ترین روش برای درون‌ریزی است. [مرجع: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description)

```js
// coolNumber.js
const ultimateNumber = 42;
export default ultimateNumber;

// ------------

// myFile.js
import number from './coolNumber.js';
// برون‌ریزی پیش‌فرض، مستقل از این که چه نامی داشته باشد به طور خودکار متغیر number درون‌ریزی شده است.
console.log(number) // 42
```

برون‌ریزی تابع

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

#### منابع خارجی

- [ES6 Modules in bulletpoints](https://ponyfoo.com/articles/es6#modules)
- [Export - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
- [Import - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Understanding ES6 Modules](https://www.sitepoint.com/understanding-es6-modules/)
- [Destructuring special case - import statements](https://ponyfoo.com/articles/es6-destructuring-in-depth#special-case-import-statements)
- [Misunderstanding ES6 Modules - Kent C. Dodds](https://medium.com/@kentcdodds/misunderstanding-es6-modules-upgrading-babel-tears-and-a-solution-ad2d5ab93ce0)
- [Modules in JavaScript](http://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript)
