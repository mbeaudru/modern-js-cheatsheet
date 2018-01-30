# <a name="modern-javascript-cheatsheet"></a> モダン JavaScript チートシート

![モダン JavaScript チートシート](https://i.imgur.com/aexPxMb.png)
<small>画像クレジット: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</small>

## <a name="introduction"></a> イントロダクション

### <a name="motivation"></a> 動機

このドキュメントはモダンなプロジェクトでよく見られる JavaScript のチートシートと最新のサンプルコードです。

このガイドは読者に JavaScript をゼロから教えるものではありません。
基礎知識は持っていて、モダンなコードベースに慣れる（例えば React を学ぶ）のに苦労している開発者を助けるためのものです。
説明の中で JavaScript の諸概念が使われています。

また、議論の余地のあるポイントについてときどき個人的な tips を載せますが、その際はあくまでも個人的なおすすめであることを述べるように気をつけます。

> **メモ:** ここで紹介されている概念のほとんどは JavaScript 言語のアップデート（ ES2015 、しばしば ES6 と呼ばれるもの）によるものです。そのアップデートで追加された新しい機能の説明は[こちらのページ](http://es6-features.org)で見つけることができます。このページはとてもわかりやすく書かれています。

### <a name="complementary-resources"></a> 補完的なリソース

概念がうまく理解できない場合は、以下のリソースで答えを探すことをおすすめします:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/search?q=)
- [You don't know JS (book)](https://github.com/getify/You-Dont-Know-JS)
- [ES6 Features with examples](http://es6-features.org)
- [WesBos blog (ES6)](http://wesbos.com/category/es6/)
- [Javascript Basics for Beginners](https://www.udacity.com/course/javascript-basics--ud804) - Udacity の無料コース
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) （ブログとリソースを見つけるために）
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)

## <a name="table-of-contents"></a> 目次

- [モダン JavaScript チートシート](#modern-javascript-cheatsheet)
  * [イントロダクション](#introduction)
    + [動機](#motivation)
    + [補完的なリソース](#complementary-resources)
  * [目次](#table-of-contents)
  * [各種概念](#notions)
    + [変数宣言: `var` / `const` / `let`](#variable-declaration-var-const-let)
      - [短い説明](#short-explanation)
      - [サンプルコード](#sample-code)
      - [詳細な説明](#detailed-explanation)
      - [外部のリソース](#external-resource)
    + [アロー関数](#-arrow-function)
      - [サンプルコード](#sample-code-1)
      - [詳細な説明](#detailed-explanation-1)
        * [簡潔さ](#concision)
        * [*`this`* 参照](#this-reference)
      - [有用なリソース](#useful-resources)
    + [関数の引数のデフォルト値](#function-default-parameter-value)
      - [外部のリソース](#external-resource-1)
    + [オブジェクトや配列の分割](#destructuring-objects-and-arrays)
      - [サンプルコード付きの説明](#explanation-with-sample-code)
      - [有用なリソース](#useful-resources-1)
    + [配列のメソッド - `map` / `filter` / `reduce`](#array-methods---map--filter--reduce)
      - [サンプルコード](#sample-code-2)
      - [説明](#explanation)
        * [`Array.prototype.map()`](#arrayprototypemap)
        * [`Array.prototype.filter()`](#arrayprototypefilter)
        * [`Array.prototype.reduce()`](#arrayprototypereduce)
      - [外部のリソース](#external-resource-2)
    + [スプレッド演算子「 `...` 」](#spread-operator-)
      - [サンプルコード](#sample-code-3)
      - [説明](#explanation-1)
        * [イテラブル（配列など）の中での使用](#in-iterables-like-arrays)
        * [関数のレスト引数](#function-rest-parameter)
        * [オブジェクトプロパティのスプレッディング](#object-properties-spreading)
      - [外部のリソース](#external-resources)
    + [オブジェクトプロパティの省略形](#object-property-shorthand)
      - [説明](#explanation-2)
      - [外部のリソース](#external-resources-1)
    + [プロミス](#promises)
      - [サンプルコード](#sample-code-4)
      - [説明](#explanation-3)
        * [プロミスの作成](#create-the-promise)
        * [プロミスハンドラーの使用](#promise-handlers-usage)
      - [外部のリソース](#external-resources-2)
    + [テンプレートリテラル](#template-literals)
      - [サンプルコード](#sample-code-5)
      - [外部のリソース](#external-resources-3)
    + [タグ付きテンプレートリテラル](#tagged-template-literals)
      - [外部のリソース](#external-resources-4)
    + [インポート / エクスポート](#imports--exports)
      - [サンプルコード付きの説明](#explanation-with-sample-code-1)
        * [名前付きエクスポート](#named-exports)
        * [デフォルトインポート / エクスポート](#default-import--export)
      - [外部のリソース](#external-resources-5)
    + [JavaScript の *`this`*](#-javascript-this)
      - [外部のリソース](#external-resources-6)
    + [クラス](#class)
      - [サンプルコード](#samples)
      - [外部のリソース](#external-resources-7)
    + [`extends` キーワードと `super` キーワード](#extends-and-super-keywords)
      - [サンプルコード](#sample-code-6)
      - [外部のリソース](#external-resources-8)
    + [Async Await](#async-await)
      - [サンプルコード](#sample-code-7)
      - [サンプルコード付きの説明](#explanation-with-sample-code-2)
      - [エラーハンドリング](#error-handling)
      - [外部のリソース](#external-resources-9)
    + [True になるもの / False になるもの](#truthy--falsy)
      - [外部のリソース](#external-resources-10)
    + [アナモルフィズム / カタモルフィズム](#anamorphisms-and-catamorphisms)
      - [アナモルフィズム](#anamorphisms)
      - [カタモルフィズム](#catamorphisms)
      - [外部のリソース](#external-resources-11)
    + [ジェネレーター](#generators)
      - [外部のリソース](#external-resources-12)
    + [スタティックメソッド](#static-methods)
      - [短い説明](#short-explanation-1)
      - [サンプルコード](#sample-code-8)
      - [詳細な説明](#detailed-explanation-2)
        * [スタティックメソッドから別のスタティックメソッドを呼ぶ](#calling-other-static-methods-from-a-static-method)
        * [スタティックでないメソッドからスタティックメソッドを呼ぶ](#calling-static-methods-from-non-static-methods)
      - [外部のリソース](#external-resources-13)
  * [用語集](#glossary)
    + [スコープ](#-scope)
    + [変数ミューテーション](#-variable-mutation)

## <a name="notions"></a> 各種概念

### <a name="variable-declaration-var-const-let"></a> 変数宣言: `var` / `const` / `let`

JavaScript には、変数の宣言に利用できるキーワードが 3 つあり、それぞれ違いがあります。
その 3 つのキーワードとは、 ```var``` と ```let``` と ```const``` です。

#### <a name="short-explanation"></a> 短い説明

```const``` キーワードで宣言された変数は再代入ができません。
```let``` と ```var``` は再代入ができます。

基本的に、変数はいつも ```const``` で宣言するようにして、変数を *変更* したり（訳注: 原文では「 mutate 」です）後から再代入したりする必要がある場合に ```let``` を使うことをおすすめします。

<table>
  <tr>
    <th></th>
    <th>スコープ</th>
    <th>再代入可能</th>
    <th>ミュータブル</th>
   <th><a href="#tdz_sample">テンポラルデッドゾーン</a></th>
  </tr>
  <tr>
    <th>`const`</th>
    <td>ブロック</td>
    <td>×</td>
    <td><a href="#const_mutable_sample">○</a></td>
    <td>○</td>
  </tr>
  <tr>
    <th>`let`</th>
    <td>ブロック</td>
    <td>○</td>
    <td>○</td>
    <td>○</td>
  </tr>
   <tr>
    <th>`var`</th>
    <td>関数</td>
    <td>○</td>
    <td>○</td>
    <td>×</td>
  </tr>
</table>

#### <a name="sample-code"></a> サンプルコード

```javascript
const person = "Nick";
person = "John" // Will raise an error, person can't be reassigned
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", reassignment is allowed with let
```

#### <a name="detailed-explanation"></a> 詳細な説明

変数の [*スコープ*](#scope_def) とは、ざっくり言うと、「コードの中でその変数が利用できる範囲」のことです。

##### <a name=""></a> `var`

```var``` で宣言された変数のスコープは *関数スコープ* になります。
これは、ある変数が関数の中で作成されているとき、その関数の中のすべてのパーツがその変数にアクセスできることを意味します。
加えて、ある関数の中で作成された *関数スコープ* の変数はその関数の外側ではアクセスすることができません。

*X スコープ* 変数ということばの意味は、その変数が X のプロパティであるような感じでイメージすることをおすすめします。

```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - myVar is accessible inside the function
}
console.log(myVar); // Throws a ReferenceError, myVar is not accessible outside the function.
```

変数のスコープに引き続き着目し、もう少しわかりづらい例を見てみましょう:

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // actually, myVar being function scoped, we just erased the previous myVar value "Nick" for "John"
  }
  console.log(myVar); // "John" - see how the instructions in the if block affected this value
}
console.log(myVar); // Throws a ReferenceError, myVar is not accessible outside the function.
```

加えて、 *`var`* で宣言された変数は実行時にスコープの一番上に移動されます。
この処理のことを [`var` ホイスティング](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting) と呼びます。

次のコードは

```js
console.log(myVar) // undefined -- no error raised
var myVar = 2;
```

実行時に次のように解釈されます。

```js
var myVar;
console.log(myVar) // undefined -- no error raised
myVar = 2;
```

##### <a name=""></a> `let`

```var``` と ```let``` は大体同じですが、 ```let``` で宣言された変数には次の特徴があります。

- *ブロックスコープ* である
- 代入の前にアクセスすることが *できない*
- 同じスコープの中で再宣言できない

上の例を使ってブロックスコープのインパクトを見てみましょう:

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // actually, myVar being block scoped, we just created a new variable myVar.
    // this variable is not accessible outside this block and totally independent
    // from the first myVar created !
  }
  console.log(myVar); // "Nick", see how the instructions in the if block DID NOT affect this value
}
console.log(myVar); // Throws a ReferenceError, myVar is not accessible outside the function.
```

<a name="tdz_sample"></a> ここで、 *`let`* （と *`const`* ）で宣言された変数に関して、代入前にアクセスできないというのは次のコードに示すとおりの意味です:

```js
console.log(myVar) // raises a ReferenceError !
let myVar = 2;
```

*`var`* とは対照的に、 *`let`* や *`const`* の変数では代入前に読み込みあるいは書き込みをしようとするとエラーが上がります。
この現象はしばしば [*テンポラルデッドゾーン*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_Dead_Zone_and_errors_with_let) あるいは *TDZ* と呼ばれます。

> **メモ:** 技術的には、 *`let`* と *`const`* の変数宣言もホイストされています。
これらは代入前に使用されないように作られているため、直感的にはホスティングが起こっていないように感じられますが、実際には起こっています。
詳しく知りたい場合は[こちらの非常に詳しい説明](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)をご覧ください。

加えて、 *`let`* 変数は再宣言することができません:

```js
let myVar = 2;
let myVar = 3; // Raises a SyntaxError
```

##### <a name=""></a> `const`

```const``` で宣言された変数は *`let`* 変数のように振る舞いますが、再代入ができません。

まとめると、 *`const`* 変数には次の特徴があります:

- *ブロックスコープ* である
- 代入前にアクセスすることができない
- 同じスコープの中で再宣言できない
- 再代入できない

```js
const myVar = "Nick";
myVar = "John" // raises an error, reassignment is not allowed
```

```js
const myVar = "Nick";
const myVar = "John" // raises an error, re-declaration is not allowed
```

<a name="const_mutable_sample"></a> しかし、微妙なポイントがあります: ```const``` 変数は [**イミュータブル**](#mutation_def) ではありません！
具体的に言うと、 ```const``` で宣言された *オブジェクト* と *配列* は変更することが **できます** 。

オブジェクトの場合:

```js
const person = {
  name: 'Nick'
};
person.name = 'John' // this will work ! person variable is not completely reassigned, but mutated
console.log(person.name) // "John"
person = "Sandra" // raises an error, because reassignment is not allowed with const declared variables
```

配列の場合:

```js
const person = [];
person.push('John'); // this will work ! person variable is not completely reassigned, but mutated
console.log(person[0]) // "John"
person = ["Nick"] // raises an error, because reassignment is not allowed with const declared variables
```

#### <a name="external-resource"></a> 外部のリソース

- [How let and const are scoped in JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Temporal Dead Zone (TDZ) Demystified](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="-arrow-function"></a> <a name="arrow_func_concept"></a> アロー関数

ES6 JavaScript のアップデートで *アロー関数* が導入されました。
これは、変数を宣言し利用するもうひとつの方法です。
アロー関数がもたらすメリットは次のとおりです:

- より簡潔である
- *`this`* が周辺のスコープからピックアップされる
- 暗黙的な `return`

#### <a name="sample-code-1"></a> サンプルコード

- 簡潔さと暗黙的な `return`

```js
function double(x) { return x * 2; } // Traditional way
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // Same function written as an arrow function with implicit return
console.log(double(2)) // 4
```

- *`this`* 参照

アロー関数の中では、 *`this`* はその周りにある実行コンテキストの *`this`* と同じものになります。
アロー関数を使えば、基本的に、関数の中で関数を呼び出す前に `that = this` とするトリックを使う必要がありません。

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### <a name="detailed-explanation-1"></a> 詳細な説明

##### <a name="concision"></a> 簡潔さ

アロー関数は、従来の関数よりも多くの点において簡潔です。
すべての起こりうるケースを見てみましょう:

- 暗黙的な `return`  vs. 明示的な `return`

**明示的な `return`** は、 *`return`* キーワードがボディの中で使われている関数のことです。

```js
  function double(x) {
    return x * 2; // this function explicitly returns x * 2, *return* keyword is used
  }
```

関数を書く従来の方法では、 `return` は常に明示的に書く形になります。
しかし、アロー関数では、 *暗黙的な `return`* を使うことができます。
これは、値を返すのに *`return`* キーワードを使う必要がないという意味です。

```js
  const double = (x) => {
    return x * 2; // Explicit return here
  }
```

この関数は何かを返すだけのものなので（ *`return`* キーワードの前に他の処理が無いので）、暗黙的な `return` を使うことができます。

```js
  const double = (x) => x * 2; // Correct, returns x*2
```

こうするためには、 **かっこと `return` キーワードを削除** しさえすれば OK です。
そのため、これは *暗黙的な* `return` と呼ばれています。
*`return`* キーワードは書かれていませんが、この関数は実際には ```x * 2``` を返します。

> **メモ:** もしある関数が値を返さなければ、それは暗黙的な `return` も明示的な `return` も行っていません。

加えて、 *オブジェクト* を暗黙的に返したい場合は、ブロックのかっことの衝突を防ぐために **その周りにかっこを付ける必要があります**:

```js
const getPerson = () => ({ name: "Nick", age: 24 })
console.log(getPerson()) // { name: "Nick", age: 24 } -- object implicitly returned by arrow function
```

- 引数が 1 つだけの場合

引数を 1 つだけ受け取る関数の場合は、引数の周りのかっこを省略することができます
上の *`double`* のコードをもう一度取り上げましょう:

```js
  const double = (x) => x * 2; // this arrow function only takes one parameter
```

引数のかっこは省略できます:

```js
  const double = x => x * 2; // this arrow function only takes one parameter
```

- 引数が無い場合

アロー関数が引数を取らない場合、かっこを付ける必要があります。
かっこをつけないと正しいシンタックスではなくなります。

```js
  () => { // parentheses are provided, everything is fine
    const x = 2;
    return x;
  }
```

```js
  => { // No parentheses, this won't work!
    const x = 2;
    return x;
  }
```

##### <a name="this-reference"></a> *`this`* 参照

アロー関数といっしょに導入されたこの微妙なポイントを理解するためには、 JavaScript における [`this`](#this_def) の振る舞いを知っておく必要があります。

アロー関数では、 *`this`* はひとつ外側にある実行コンテキストの *`this`* の値に等しくなります。
これはつまり、アロー関数は新しい *`this`* を作成せず代わりに周囲の環境から *`this`* を取得します。

アロー関数がなかった頃は、関数内の関数で *`this`* の値にアクセスしたい場合は、 *`that = this`* または *`self = this`* のトリックを使う必要がありました。

例えば、 `setTimeout` 関数を `myFunc` の中で利用する場合は次のようにする必要がありました:

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

アロー関数があれば、 *`this`* はその外部の環境から取得されます:

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

#### <a name="useful-resources"></a> 有用なリソース

- [Arrow functions introduction - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript arrow function - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

### <a name="function-default-parameter-value"></a> 関数の引数のデフォルト値

ES2015 の JavaScript アップデート以降、関数の引数のデフォルト値を次のシンタックスでセットできます:

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- no value is provided so x default value 10 is assigned to x in myFunc
console.log(myFunc(5)) // 5 -- a value is provided so x is equal to 5 in myFunc

console.log(myFunc(undefined)) // 10 -- undefined value is provided so default value is assigned to x
console.log(myFunc(null)) // null -- a value (null) is provided, see below for more details
```

デフォルト引数は次の 2 つの状況でのみ適用されます:

- 引数が渡されなかった
- *`undefined`* 引数が渡された

言い換えると、 *`null`* を渡した場合はデフォルト引数は **適用されません** 。

> **メモ:** デフォルト値の代入は、分割引数（訳注: 原文では「 destructured parameters 」です）でも使用することができます（例は、次の概念をご覧ください）

#### <a name="external-resource-1"></a> 外部のリソース

- [Default parameter value - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Default parameters - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

### <a name="destructuring-objects-and-arrays"></a> オブジェクトや配列の分割

*分割* （訳注: 原文では「 destructuring 」です）はオブジェクトまたは配列に格納されたデータから値を抽出して新しい変数を作成する便利な方法です。

いくつかユースケースをあげるなら、 *分割* は関数の引数を分割するために使用することもできますし、 React プロジェクトの *`this.props`* で使用することもできます。

#### <a name="explanation-with-sample-code"></a> サンプルコード付きの説明

- オブジェクト

以下すべてのサンプルに対して次のオブジェクトについて考えてみましょう:

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

分割がない場合、次のようになります。

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

分割がある場合は、ワンラインで書くことができます:

```js
const { firstName: first, age, city = "Paris" } = person; // That's it !

console.log(age) // 35 -- A new variable age is created and is equal to person.age
console.log(first) // "Nick" -- A new variable first is created and is equal to person.firstName
console.log(firstName) // ReferenceError -- person.firstName exists BUT the new variable created is named first
console.log(city) // "Paris" -- A new variable city is created and since person.city is undefined, city is equal to the default value provided "Paris".
```

**メモ:** ```const { age } = person;``` において、 *`const`* キーワードの後のかっこは、オブジェクトやブロックの宣言として使用されるのではなく、 *分割* のシンタックスとなります。

- 関数の引数

*分割* は関数のオブジェクト引数を分割するためにしばしば使用されます。

分割を使わない場合、次のようになります。

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

オブジェクト引数 *`person`* を分割すれば、より簡潔な関数を書くことができます:

```js
function joinFirstLastName({ firstName, lastName }) { // we create firstName and lastName variables by destructuring person parameter
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

分割は[アロー関数](#arrow_func_concept)といっしょに使うとぐっといい感じになります:

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```

- 配列

次の配列について考えてみましょう:

```js
const myArray = ["a", "b", "c"];
```

分割を使わない場合、次のようになります。

```js
const x = myArray[0];
const y = myArray[1];
```

分割を使うと、次のように書けます。

```js
const [x, y] = myArray; // That's it !

console.log(x) // "a"
console.log(y) // "b"
```

#### <a name="useful-resources-1"></a> 有用なリソース

- [ES6 Features - Destructuring Assignment](http://es6-features.org/#ArrayMatching)
- [Destructuring Objects - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destructuring](http://exploringjs.com/es6/ch_destructuring.html)

### <a name="array-methods---map--filter--reduce"></a> 配列のメソッド - `map` / `filter` / `reduce`

*`map`* 、 *`filter`* 、 *`reduce`* は [*関数プログラミング*](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0) という名前のプログラミングパラダイムに由来する配列のメソッドです。

まとめ:

- **Array.prototype.map()** 配列を受け取り、各要素に対して何かをして、変更された要素を持つ配列を返す。
- **Array.prototype.filter()** 配列を受け取り、要素ごとに保持するかどうかを決めて、保持する要素のみからなる配列を返す。
- **Array.prototype.reduce()** 配列を受け取り、要素を 1 つの値に集約する（その値が返される）。

これらは組み合わせ可能で、簡潔でエレガントなので、関数プログラミングは原則に則ってできるかぎりこれらを使用することをおすすめします。

これら 3 つのメソッドを使えば、ほとんどの状況で *`for`* ループと *`forEach`* ループを使用しなくてよくなります。
*`for`* ループが使いたい場合は、 *`map`* と *`filter`* と *`reduce`* を組み合わせて処理を実現することを試みてください。
新しい考え方を身につける必要があるので最初は苦労するかもしれませんが、一度馴れればものごとはよりかんたんになります。

#### <a name="sample-code-2"></a> サンプルコード

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
const doubledNumbers = numbers.map(n => n * 2); // [0, 2, 4, 6, 8, 10, 12]
const evenNumbers = numbers.filter(n => n % 2 === 0); // [0, 2, 4, 6]
const sum = numbers.reduce((prev, next) => prev + next, 0); // 21
```

`map` 、 `filter` 、 `reduce` を使って、グレードが 10 以上の学生のグレードの合計値を計算してみます:

```js
const students = [
  { name: "Nick", grade: 10 },
  { name: "John", grade: 15 },
  { name: "Julia", grade: 19 },
  { name: "Nathalie", grade: 9 },
];

const aboveTenSum = students
  .map(student => student.grade) // we map the students array to an array of their grades
  .filter(grade => grade >= 10) // we filter the grades array to keep those 10 or above
  .reduce((prev, next) => prev + next, 0); // we sum all the grades 10 or above one by one

console.log(aboveTenSum) // 44 -- 10 (Nick) + 15 (John) + 19 (Julia), Nathalie below 10 is ignored
```

#### <a name="explanation"></a> 説明

例として、数値からなる次の配列について考えてみましょう:

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
```

##### <a name="arrayprototypemap"></a> `Array.prototype.map()`

```js
const doubledNumbers = numbers.map(function(n) {
  return n * 2;
});
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

ここでは何が起こっているのでしょうか。
`.map` を配列 *`numbers`* に対して使用しています。
`map` は渡された関数を配列の各要素に適用します。
この関数のゴールは、 `map` が利用できるように、渡された値から新しい値を生成して返すことです。

わかりやすくするために、今回は特別にこの関数を抽出しましょう:

```js
const doubleN = function(n) { return n * 2; };
const doubledNumbers = numbers.map(doubleN);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

```numbers.map(doubleN)``` は ```[doubleN(0), doubleN(1), doubleN(2), doubleN(3), doubleN(4), doubleN(5), doubleN(6)]``` を生成します。
そしてこれは ```[0, 2, 4, 6, 8, 10, 12]``` になります。

> **メモ:** 新しい配列を返すのではなく副作用のあるループを回したいだけの場合は、 `map` の代わりの `for` / `forEach` ループを使いたくなるかもしれません。

##### <a name="arrayprototypefilter"></a> `Array.prototype.filter()`

```js
const evenNumbers = numbers.filter(function(n) {
  return n % 2 === 0; // true if "n" is par, false if "n" isn't
});
console.log(evenNumbers); // [0, 2, 4, 6]
```

配列 *`numbers`* に対して `.filter()` を使用しています。
`filter` は指定された関数に配列の各要素を渡します。
この関数のゴールは、現在の値を保持すべきかどうかを決める真偽値を返すことです。
`filter` は保持すべき値のみを格納した配列を返します。

##### <a name="arrayprototypereduce"></a> `Array.prototype.reduce()`

`reduce` メソッドのゴールは、配列のすべての要素を走査してひとつの値に *縮減* することです。
どのように集約するかのロジックはあなた次第です。

```js
const sum = numbers.reduce(
  function(acc, n) {
    return acc + n;
  },
  0 // accumulator variable value at first iteration step
);

console.log(sum) //21
```

`.map` メソッドと `.filter` メソッドのように、 `.reduce` は配列に対して適用されるもので、第 1 引数に関数を受け取ります。

ただしこの場合は違いがあります:

- `.reduce` は 2 つの引数を受け取ります

第 1 引数は、ループの各ステップで呼び出される関数です。

第 2 引数は、ループの最初のステップにおける蓄積用の変数（訳注: 原文では「 accumulator variable 」です）の値です（これを理解するには次のポイントを読んでください）。

- 関数引数

`.reduce` の第 1 引数として渡す関数は、 2 つの引数を受け取ります。
1 つめの引数（ここでは *`acc`* ）は、蓄積用の変数で、 2 つめの引数（ *`n`* ）は現在の要素です。

蓄積用の変数は、 **ひとつ前の** ループのステップにおける関数の戻り値と等しいものです。
ループの最初のステップでは *`acc`* は `.reduce` の第 2 引数に渡された値に等しくなります。

###### <a name=""></a> ループの最初のステップ

`reduce` の第 2 引数に `0` を渡しているので、 ```acc = 0``` となります。

*`numbers`* 配列の最初の要素を取るので、 ```n = 0``` となります。

関数は *`acc + n`* を返すので、これは `0 + 0` で `0` になります。

###### <a name=""></a> ループの第 2 ステップ

ひとつ前のループのステップで関数が返した値が使われるので、 ```acc = 0``` となります。

*`numbers`* 配列の 2 番目の要素を取るので、 ```n = 1``` となります。

関数は *`acc + n`* を返すので、これは `0 + 1` で `1` になります。

###### <a name=""></a> ループの第 3 ステップ

ひとつ前のループのステップで関数が返した値が使われるので、 ```acc = 1``` となります。

*`numbers`* 配列の 2 番目の要素を取るので、 ```n = 2``` となります。

関数は *`acc + n`* を返すので、これは `1 + 2` で `3` になります。

###### <a name=""></a> ループの第 4 ステップ

ひとつ前のループのステップで関数が返した値が使われるので、 ```acc = 3``` となります。

*`numbers`* 配列の 2 番目の要素を取るので、 ```n = 3``` となります。

関数は *`acc + n`* を返すので、これは `3 + 3` で `6` になります。

###### <a name=""></a> ループの最後のステップ

ひとつ前のループのステップで関数が返した値が使われるので、 ```acc = 15``` となります。

*`numbers`* 配列の最後の要素を取るので、 ```n = 6``` となります。

関数は *`acc + n`* を返すので、これは `15 + 6` で `21` になります。

これがループの最後のステップなので、 **`.reduce`** は `21` を返します。

#### <a name="external-resource-2"></a> 外部のリソース

- [Understanding map / filter / reduce in JS](https://hackernoon.com/understanding-map-filter-and-reduce-in-javascript-5df1c7eee464)

### <a name="spread-operator-"></a> スプレッド演算子「 `...` 」

スプレッド演算子（訳注: 原文では「 spread operator 」です）は ES2015 で導入されました。
イテラブルなオブジェクト（訳注: 原文では「 iterable 」です）（配列など）の要素を、複数の要素が来るべきところに展開するために使用されます。

#### <a name="sample-code-3"></a> サンプルコード

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

#### <a name="explanation-1"></a> 説明

##### <a name="in-iterables-like-arrays"></a> イテラブル（配列など）の中での使用

次の 2 つの配列があるものとします:

```js
const arr1 = ["a", "b", "c"];
const arr2 = [arr1, "d", "e", "f"]; // [["a", "b", "c"], "d", "e", "f"]
```

*`arr1`* がそのまま *`arr2`* にインジェクトされたので、 *`arr2`* の第 1 要素は配列です。
しかし、実際は *`arr2`* をすべて文字からなる配列にしたいものとしましょう。
そうしたい場合は、 *`arr1`* の要素を *スプレッド* して *`arr2`* に入れることができます。

スプレッド演算子を使うと、次のように書けます。

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

##### <a name="function-rest-parameter"></a> 関数のレスト引数

関数の引数において、レスト演算子（訳注: 原文では「 rest operator 」です）を使って引数をまとめて、ループ可能なひとつの配列に入れ込むことができます。
すでに、関数に渡されたすべての引数を格納した配列に等しい **`arguments`** オブジェクトが関数にはバインドされています。

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

しかし、仮に、この関数に、グレードと平均グレードを持つ新しい学生のオブジェクトを作成させたい場合を考えましょう。
最初の 2 つの引数を個別の 2 つの変数に抽出しておいて、すべてのグレードを格納したループ可能な配列が取得できるなら、便利ですよね。

まさにこれがレスト演算子でできることなのです！

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

> **メモ:** `grades.length` が存在するかどうか、あるいは `0` と異なるかどうかをチェックしていないので、 `createStudent` 関数はよくありません。
しかし、この形だと読みやすいので、そのケースは処理していません。

##### <a name="object-properties-spreading"></a> オブジェクトプロパティのスプレッディング

ここを読む場合は、イテラブルオブジェクトに対するレスト演算子と関数の引数に関するひとつ前の説明を先に読むことをおすすめします。

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

#### <a name="external-resources"></a> 外部のリソース

- [TC39 - Object rest/spread](https://github.com/tc39/proposal-object-rest-spread)
- [Spread operator introduction - WesBos](https://github.com/wesbos/es6-articles/blob/master/28%20-%20Spread%20Operator%20Introduction.md)
- [JavaScript & the spread operator](https://codeburst.io/javascript-the-spread-operator-a867a71668ca)
- [6 Great uses of the spread operator](https://davidwalsh.name/spread-operator)

### <a name="object-property-shorthand"></a> オブジェクトプロパティの省略形

変数をオブジェクトのプロパティに代入するとき、変数名がプロパティ名と同じ場合は、次の形で書くことができます:

```js
const x = 10;
const myObj = { x };
console.log(myObj.x) // 10
```

#### <a name="explanation-2"></a> 説明

新しい *オブジェクトリテラル* を宣言して、プロパティの値として変数を使用したい場合は、（ ES2015 以前は）たいてい次のようなコードを書いたことでしょう:

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

ご覧のとおり、 `myObj` のプロパティ名はそこに値を割り当てたい変数の名前と同じなので、非常にくどい感じになります。

ES2015 では、変数名がプロパティ名と同じ場合は、次の省略形を使うことができます:

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

#### <a name="external-resources-1"></a> 外部のリソース

- [Property shorthand - ES6 Features](http://es6-features.org/#PropertyShorthand)

### <a name="promises"></a> プロミス

プロミスとは、非同期的な関数（訳注: 原文では「 asynchronous function 」です）から同期的に（訳注: 原文では「 synchronously 」です）返すことができるオブジェクトです（[参考](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261#3cd0))）。

プロミスは[コールバック地獄](http://callbackhell.com/)（訳注: 原文では「 callback hell 」です）を避けるために使用することができます。
モダンな JavaScript プロジェクトで出会うますます頻繁に使われるようになっています。

#### <a name="sample-code-4"></a> サンプルコード

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

#### <a name="explanation-3"></a> 説明

*Ajax リクエスト* を行う場合は、時間のかかるリソースが求められることもあるので、レスポンスは同期的ではありません。
リクエストされたリソースが何らかの理由で利用不可の場合（ 404 の場合）、レスポンスが戻ってこないこともあります。

このような状況を扱うために、 ES2015 は *プロミス* を提供しました。
プロミスは異なる 3 つの状態を持つことができます:

- ペンディング（訳注: 原文では「 Pending 」です）
- フルフィルド（訳注: 原文では「 Fulfilled 」です）
- リジェクテッド（訳注: 原文では「 Rejected 」です）

プロミスを使って、リソース X をフェッチするために Ajax リクエストを扱う場合を考えてみましょう。

##### <a name="create-the-promise"></a> プロミスの作成

最初にプロミスを作成します。
X への Ajax リクエストを行うために jQuery の `get` メソッドを使います。

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

上の例のとおり、プロミスオブジェクトは、 2 つの引数 **`resolve`** と **`reject`** を受け取る *エクセキューター* 関数（訳注: 原文では「 executor function 」です）を受け取ります。
これらの引数は、プロミスの *ペンディング* ステートを *フルフィルド* ステートと *リジェクテッド* ステートのそれぞれに移行させるときに呼び出されます。

プロミスはインスタンスが作成された後はペンディングステートになっており、 *エクセキューター* 関数が即座に実行されます。
*エクセキューター* 関数の中で *`resolve`* か *`reject`* の一方が呼び出されたら、プロミスは関連づけられたハンドラーを呼び出します。

##### <a name="promise-handlers-usage"></a> プロミスハンドラーの使用

プロミスの結果（もしくはエラー）を取得するには、次のようにしてハンドラーをアタッチする必要があります:

```js
xFetcherPromise
  .then(function(X) {
    console.log(X);
  })
  .catch(function(err) {
    console.log(err)
  })
```

プロミスが成功すれば、 *`resolve`* が実行され ```.then``` の引数として渡された関数が実行されます。

プロミスが失敗すれば、 *`reject`* が実行され、 ```.catch``` の引数として渡された関数が実行されます。

> **メモ:** もし、対応するハンドラーがアタッチされたときにプロミスがすでにフルフィルドやリジェクテッドの状態になっていれば、そのハンドラーは呼び出されます。非同期の操作の完了とアタッチされるハンドラの間で競合状態は発生しません。（[参考: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise#Description)）

#### <a name="external-resources-2"></a> 外部のリソース

- [JavaScript Promises for dummies - Jecelyn Yeen](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [JavaScript Promise API - David Walsh](https://davidwalsh.name/promises)
- [Using promises - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [What is a promise - Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- [JavaScript Promises: an Introduction - Jake Archibald](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
- [Promise documentation - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

### <a name="template-literals"></a> テンプレートリテラル

テンプレートリテラルとは、単一行・複数行の文字列に対する [*式補完*](https://en.wikipedia.org/wiki/String_interpolation) （訳注: 原文は「 expression interpolation 」です）です。

言い換えると、テンプレートリテラルは、 JavaScript の式（例えば変数）をその中で使える新しい文字列シンタックスです。

#### <a name="sample-code-5"></a> サンプルコード

```js
const name = "Nick";
`Hello ${name}, the following expression is equal to four : ${2+2}`;

// Hello Nick, the following expression is equal to four: 4
```

#### <a name="external-resources-3"></a> 外部のリソース

- [String interpolation - ES6 Features](http://es6-features.org/#StringInterpolation)
- [ES6 Template Strings - Addy Osmani](https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

### <a name="tagged-template-literals"></a> タグ付きテンプレートリテラル

テンプレートタグは *[テンプレートリテラル](#template-literals)にプリフィックスされる関数* です。
関数がこの形で呼び出されたとき、第 1 引数はテンプレートの補完を行う変数と変数の間に現れる *文字列* からなる配列で、その後の引数は補完に使われる値です。
これをすべて捉えるにはスプレッド演算子を使用します。
（[参考: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#Tagged_template_literals)）

> **メモ:** [styled-components](https://www.styled-components.com/) という有名なライブラリはこの機能を多用しています。

次のコードは、タグ付きテンプレートリテラルがどのように動作するかを示す遊びのサンプルです。

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

次はもっとおもしろいサンプルです:

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

#### <a name="external-resources-4"></a> 外部のリソース

- [Wes Bos on Tagged Template Literals](http://wesbos.com/tagged-template-literals/)
- [Library of common template tags](https://github.com/declandewet/common-tags)

### <a name="imports--exports"></a> インポート / エクスポート

ES6 モジュールは、他のモジュールが明示的にエクスポートした変数や関数にモジュールがアクセスするために使用するための方法です。

インポート / エクスポートに関する MDN のリソース（下の外部のリソースのところをご覧ください）を見ることを強くおすすめします。
そのリソースはわかりやすいと同時に、ポイントが網羅されています。

#### <a name="explanation-with-sample-code-1"></a> サンプルコード付きの説明

##### <a name="named-exports"></a> 名前付きエクスポート

名前付きエクスポート（訳注: 原文では「 named exports 」です）は、モジュールから複数の値をエクスポートするための方法です。

> **メモ:** 名前付きエクスポートは、名前の付いた[第一級オブジェクト](https://en.wikipedia.org/wiki/First-class_citizen)に対してのみ可能です。

```js
// mathConstants.js
export const pi = 3.14;
export const exp = 2.7;
export const alpha = 0.35;

// -------------

// myFile.js
import { pi, exp } from './mathConstants.js'; // Named import -- destructuring-like syntax
console.log(pi) // 3.14
console.log(exp) // 2.7

// -------------

// mySecondFile.js
import * as constants from './mathConstants.js'; // Inject all exported values into constants variable
console.log(constants.pi) // 3.14
console.log(constants.exp) // 2.7
```

名前付きインポートは *分割* に似ていますが、シンタックスが異なり、分割と同じものではありません。
名前付きインポートは、デフォルト値や *深い* （訳注: 原文では「 deep 」です）分割をサポートしていません。

加えて、エイリアスを使うことができますが、そのシンタックスは分割のものとは異なります:

```js
import { foo as bar } from 'myFile.js'; // foo is imported and injected into a new bar variable
```

##### <a name="default-import--export"></a> デフォルトインポート / エクスポート

デフォルトエクスポートに関しては、モジュールごとにひとつだけデフォルトエクスポートがあります。
デフォルトエクスポートは、関数、クラス、オブジェクトその他どんなものにもすることができます。
デフォルトエクスポートはインポートするときの最もシンプルな形なので、その値は「メイン」のエクスポート値とみなされます。
（[参考: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description)）

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

関数のエクスポート:

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

#### <a name="external-resources-5"></a> 外部のリソース

- [ES6 Modules in bulletpoints](https://ponyfoo.com/articles/es6#modules)
- [Export - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
- [Import - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Understanding ES6 Modules](https://www.sitepoint.com/understanding-es6-modules/)
- [Destructuring special case - import statements](https://ponyfoo.com/articles/es6-destructuring-in-depth#special-case-import-statements)
- [Misunderstanding ES6 Modules - Kent C. Dodds](https://medium.com/@kentcdodds/misunderstanding-es6-modules-upgrading-babel-tears-and-a-solution-ad2d5ab93ce0)
- [Modules in JavaScript](http://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript)

### <a name="-javascript-this"></a> <a name="this_def"></a>  JavaScript の *`this`*

*`this`* 演算子の振る舞いは他の言語とは異なり、ほとんどの場合、関数の呼び出し方によって決まります。
（[参考: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)）

この概念にはややこしいポイントがたくさんあり非常に難しいので、以下にあげる外部のリソースを深く読むことを強くおすすめします。
そのため、ここでは *`this`* の中身が何になるかを理解するための個人的なアイデアを紹介することにします。
この考え方は [Yehuda Katz が書いた記事](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/) からのものです。

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

#### <a name="external-resources-6"></a> 外部のリソース

- [Understanding JavaScript Function Invocation and "this" - Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)
- [JavaScript this - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

### <a name="class"></a> クラス

JavaScript は [プロトタイプベース](https://en.wikipedia.org/wiki/Prototype-based_programming) の言語です（例えば、 Java は [クラスベース](https://en.wikipedia.org/wiki/Class-based_programming) の言語です）。
ES6 は、プロトタイプベースの継承に対するシンタックスシュガー（訳注: 原文では「 syntactic sugar 」です）としての JavaScript のクラスを導入しました。
これは新しいクラスベースの継承モデルでは **ありません** 。

もしあなたが他の言語のクラスに馴れていれば、 *クラス* ということばは混乱を招く可能性があります。
もし他の言語のクラスに馴れているなら、 JavaScript のクラスも同じようなものだと考えたりはせず、まったく別物の概念だと考えましょう。

このドキュメントは JavaScript についてゼロから教えようとするものではないため、読者は、プロトタイプが何であって、どのように振る舞うかを知っているものとします。
もしプロトタイプについてよく知らなければ、次のサンプルコードの下に記載された外部のリソースをご覧ください。

#### <a name="samples"></a> サンプルコード

ES6 以前のプロトタイプ構文:

```js
var Person = function(name, age) {
  this.name = name;
  this.age = age;
}
Person.prototype.stringSentence = function() {
  return "Hello, my name is " + this.name + " and I'm " + this.age;
}
```

ES6 のクラス構文:

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

#### <a name="external-resources-7"></a> 外部のリソース

プロトタイプの理解のためのリソース:

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Inheritance and the prototype chain - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

クラスの理解のためのリソース:

- [ES6 Classes in Depth - Nicolas Bevacqua](https://ponyfoo.com/articles/es6-classes-in-depth)
- [ES6 Features - Classes](http://es6-features.org/#ClassDefinition)
- [JavaScript Classes - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

### <a name="extends-and-super-keywords"></a> `extends` キーワードと `super` キーワード

`extends` キーワードは、他のクラスの子どもとなるクラスを作成するために、クラス宣言あるいはクラス式に使われます（[参考: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends)）。
サブクラスはスーパークラスのすべてのプロパティを継承し、追加で新しいプロパティを追加したり継承したプロパティを変更したりすることができます。

`super` キーワードはオブジェクトの親の関数を呼び出すために使用します。
これにはコンストラクターも含まれます。

- コンストラクターの中では、 `super` キーワードは `this` キーワードが使われる前に使わなくてはなりません。
- `super()` を呼び出すと親クラスのコンストラクターが呼ばれます。クラスのコンストラクターに引数を渡したいときは、 `super(arguments)` という形で呼び出します。
- 親クラスが `X` というメソッドを持つ場合は（スタティックメソッドでもよい）、子クラスの中で `super.X()` とすればそれを呼び出すことができます。

#### <a name="sample-code-6"></a> サンプルコード

```js
class Polygon {
  constructor(height, width) {
    this.name = 'Polygon';
    this.height = height;
    this.width = width;
  }

  getHelloPhrase() {
    return `Hi, I am a ${this.name}`;
  }
}

class Square extends Polygon {
  constructor(length) {
    // Here, it calls the parent class' constructor with lengths
    // provided for the Polygon's width and height
    super(length, length);
    // Note: In derived classes, super() must be called before you
    // can use 'this'. Leaving this out will cause a reference error.
    this.name = 'Square';
    this.length = length;
  }

  getCustomHelloPhrase() {
    const polygonPhrase = super.getHelloPhrase(); // accessing parent method with super.X() syntax
    return `${polygonPhrase} with a length of ${this.length}`;
  }

  get area() {
    return this.height * this.width;
  }
}

const mySquare = new Square(10);
console.log(mySquare.area) // 100
console.log(mySquare.getHelloPhrase()) // 'Hi, I am a Square' -- Square inherits from Polygon and has access to its methods
console.log(mySquare.getCustomHelloPhrase()) // 'Hi, I am a Square with a length of 10'
```

**メモ:** `Square` クラスの中で `super()` を呼ぶ前に `this` を使おうとすると、 `ReferenceError` が発生します:

```js
class Square extends Polygon {
  constructor(length) {
    this.height; // ReferenceError, super needs to be called first!

    // Here, it calls the parent class' constructor with lengths
    // provided for the Polygon's width and height
    super(length, length);

    // Note: In derived classes, super() must be called before you
    // can use 'this'. Leaving this out will cause a reference error.
    this.name = 'Square';
  }
}
```

#### <a name="external-resources-8"></a> 外部のリソース

- [Extends - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends)
- [Super operator - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super)
- [Inheritance - MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance)

### <a name="async-await"></a> Async Await

[プロミス](#promises) に加えて、 *`async`* / *`await`* という非同期なコードを扱うための新しい構文を見ることがあるかもしれません。

`async` / `await` 関数の目的は、プロミスを同期的に利用する振る舞いをシンプルにすることです。
そして、プロミスのグループを扱うことです。
プロミスが構造化されたコールバックに似ているのと同じように、 `async` / `await` もジェネレーターとプロミスの組み合わせに似ています。
`async` 関数は *常に* プロミスを返します。
（[参考: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)）

> **メモ:** `async` / `await` はプロミスをベースにしているため、 `async` / `await` を理解しようとする前に、プロミスがどんなもので、どのように動作するのかを理解する必要があります。

> **メモ 2:** [*`await`* は *`async`* 関数の中で使わなくてはなりません](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9#f3f0) 。これは、 `await` はコードのトップレベルでは使えない（コードのトップレベルは `async` 関数の中に入っていないので）、という意味です。

#### <a name="sample-code-7"></a> サンプルコード

```js
async function getGithubUser(username) { // async keyword allows usage of await in the function and means function returns a promise
  const response = await fetch(`https://api.github.com/users/${username}`); // Execution is paused here until the Promise returned by fetch is resolved
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user)) // logging user response - cannot use await syntax since this code isn't in async function
  .catch(err => console.log(err)); // if an error is thrown in our async function, we will catch it here
```

#### <a name="explanation-with-sample-code-2"></a> サンプルコード付きの説明

*`async`* / *`await`* はプロミスの上に構築されていますが、これらを使うとより命令型のスタイルでコードを書くことができます。

*`async`* 演算子は関数に非同期のマークを付けて、常に *プロミス* を返す形にします。
 *`async`* 関数の中で *`await`* 演算子を使うことで、その式の戻り値のプロミスがリゾルブかリジェクトのどちらかをするまで（原文では「 until the returned Promise from the expression either resolves or rejects 」です）その行で処理を一時停止することができます。

```js
async function myFunc() {
  // we can use await operator because this function is async
  return "hello world";
}

myFunc().then(msg => console.log(msg)) // "hello world" -- myFunc's return value is turned into a promise because of async operator
```

`async` 関数の *`return`* 文に到達したときに、プロミスは戻り値を持ってフルフィルされます（訳注: 原文では「 is fullfilled with the value returned 」）。
`async` 関数の中でエラーが発生したら、プロミスのステートは *リジェクテッド* に変わります。
`async` 関数に戻り値が無い場合も、 `async` 関数の実行が完了したときにはプロミスが返され、値を持たずにリゾルブが発生します。

*`await`* 演算子は *プロミス* がフルフィルドになるのを待つために使用するものであり、 *`async`* 関数のボディの中でのみ使用することができます。
処理が *`await`* のところに来たら、プロミスがフルフィルされるまで処理が一時停止されます。

> **メモ:** *`fetch`* は Ajax リクエストができるプロミスを返す関数です。

まず、プロミスを使うと GitHub ユーザー情報の取得がどのようにできたかを見てみましょう:

```js
function getGithubUser(username) {
  return fetch(`https://api.github.com/users/${username}`).then(response => response.json());
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

*`async`* / *`await`* で同じことをすると次のようになります:

```js
async function getGithubUser(username) { // promise + await keyword usage allowed
  const response = await fetch(`https://api.github.com/users/${username}`); // Execution stops here until fetch promise is fulfilled
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

*`async`* / *`await`* 構文は依存関係のある複数のプロミスをチェインするときに特に便利です。

例えば、データベースにあるブログ投稿と作成者情報をフェッチするためのトークンを取得する必要がある場合は次のようになります:

> **メモ:** リゾルブされた値のメソッドやプロパティを同一行で利用する場合、 *`await`* 式はかっこで囲う必要があります。

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

##### <a name="error-handling"></a> エラーハンドリング

*`await`* 式の周りに *`try`* / *`catch`* のブロックを追加しておかないと、キャッチされない例外がーー *`async`* 関数のボディの中で投げられたかどうかにかかわらず、また、 *`await`* でサスペンドされていても ーー *`async`* 関数が返したプロミスをリジェクトします。
`async` 関数の中で `throw` 文を使うことは、リジェクトするプロミスを返すことと同じ意味です。
（[(参考: PonyFoo)](https://ponyfoo.com/articles/understanding-javascript-async-await#error-handling)）

> **メモ:** プロミスは同じように振る舞います！

プロミスを使った場合、エラーチェインの処理は次のようにしていました:

```js
function getUser() { // This promise will be rejected!
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

*`async`* / *`await`* で同じことをすると次のようになります:

```js
async function getUser() { // The returned promise will be rejected!
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

#### <a name="external-resources-9"></a> 外部のリソース

- [Async/Await - JavaScript.Info](https://javascript.info/async-await)
- [ES7 Async/Await](http://rossboucher.com/await/#/)
- [6 Reasons Why JavaScript’s Async/Await Blows Promises Away](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9)
- [JavaScript awaits](https://dev.to/kayis/javascript-awaits)
- [Using Async Await in Express with Node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)
- [Async Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
- [Using async / await in express with node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)

### <a name="truthy--falsy"></a> True になるもの / False になるもの

JavaScript では、 `true` になる値と `false` になる値は、真偽判定のコンテキストで評価されたとき（訳注: 原文では「 when evaluated in a boolean context 」です）に真偽値にキャストされます。
真偽判定のコンテキストの例は、 ```if``` 条件での判定です。

次の値に等しくない値はすべて ```true``` にキャストされます:

- ```false```
- ```0```
- ```""``` （空文字列）
- ```null```
- ```undefined```
- ```NaN```

*真偽判定のコンテキスト* の例は次のとおりです:

- ```if``` 条件評価

```js
if (myVar) {}
```

```myVar``` にはどんな[第一級市民](https://en.wikipedia.org/wiki/First-class_citizen)（変数、関数、真偽値）を置くこともできますが、真偽判定のコンテキストで評価されているため真偽値にキャストされます。

- 論理 **否定** 演算子 ```!``` の後

この演算子はそのオペランドが `true` に変換できる場合は `false` を返します。
逆の場合は `true` を返します。

```js
!0 // true -- 0 is falsy so it returns true
!!0 // false -- 0 is falsy so !0 returns true so !(!0) returns false
!!"" // false -- empty string is falsy so NOT (NOT false) equals false
```

- *真偽値* オブジェクトコンストラクターでの使用

```js
new Boolean(0) // false
new Boolean(1) // true
```

- 三項演算子の評価部分（訳注: 原文では「 In a ternary evaluation 」です）

```js
myVar ? "truthy" : "falsy"
```

`myVar` は真偽判定コンテキストで評価されます。

2 つの値の比較には注意が必要です。

（最終的に真偽値にキャストされる）比較対象のオブジェクトの値は、真偽値にキャストされるのでは **なく** 、 [プリミティブへの変換仕様](http://javascript.info/object-toprimitive) に基いて、プリミティブ値に変換されます。
内部的には、 `[] == true` のようにオブジェクトが真偽値と比較された場合、 `[].toString() == true` という比較が行われます。

```js
let a = [] == true // a is false since [].toString() give "" back.
let b = [1] == true // b is true since [1].toString() give "1" back.
let c = [2] == true // c is false since [2].toString() give "2" back.
```

#### <a name="external-resources-10"></a> 外部のリソース

- [Truthy (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
- [Falsy (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
- [Truthy and Falsy values in JS - Josh Clanton](http://adripofjavascript.com/blog/drips/truthy-and-falsy-values-in-javascript.html)

### <a name="anamorphisms-and-catamorphisms"></a> アナモルフィズム / カタモルフィズム

#### <a name="anamorphisms"></a> アナモルフィズム

アナモルフィズム（訳注: 原文では「 anamorphisms 」です）とは、あるオブジェクトを、オブジェクト型を含むより複雑な構造体にマップする関数のことです。
それは、シンプルな構造体を複雑な構造体に *アンフォールド* する（訳注: 原文では「 unfolding 」です）処理です。
整数を、整数のリストにアンフォールドする場合を考えてみましょう。
この場合、整数が最初のオブジェクトで、整数のリストがより複雑な構造体です。

**サンプルコード**

```js
function downToOne(n) {
  const list = [];

  for (let i = n; i > 0; --i) {
    list.push(i);
  }

  return list;
}

downToOne(5)
  //=> [ 5, 4, 3, 2, 1 ]
```

#### <a name="catamorphisms"></a> カタモルフィズム

カタモルフィズム（訳注: 原文では「 catamorphisms 」です）とは、アナモルフィズムの逆で、複雑な構造体であるオブジェクトをよりシンプルな構造体に *フォールド* する（訳注: 原文では「 fold 」です）ことです。
次の `product` のサンプルを見てください。
`product` は整数のリストを受け取り単一の整数を返します。

**サンプルコード**

```js
function product(list) {
  let product = 1;

  for (const n of list) {
    product = product * n;
  }

  return product;
}

product(downToOne(5)) // 120
```

#### <a name="external-resources-11"></a> 外部のリソース

* [Anamorphisms in JavaScript](http://raganwald.com/2016/11/30/anamorphisms-in-javascript.html)
* [Anamorphism](https://en.wikipedia.org/wiki/Anamorphism)
* [Catamorphism](https://en.wikipedia.org/wiki/Catamorphism)

### <a name="generators"></a> ジェネレーター

`downToOne` 関数を書く別の方法として、ジェネレーターを使ったものがあります。
`Generator` オブジェクトを生成するには、 `function *` 宣言を使わなくてはいけません。
ジェネレーターは、一度脱出した後に、コンテキスト（変数バインディング）を保った形で再突入できる関数です（訳注: 原文では「 Generators are functions that can be exited and later re-entered with its context (variable bindings) saved across re-entrances 」です）。

例えば、上の `downToOne` 関数は次のように書き直すことができます:

```js
function * downToOne(n) {
  for (let i = n; i > 0; --i) {
    yield i;
  }
}

[...downToOne(5)] //[ 5, 4, 3, 2, 1 ]
```

ジェネレーターはイテラブルオブジェクトを返します。
イテレーターの `next()` 関数が呼ばれると、最初の `yield` 式までが実行されます。
`yield` 式はイテレーターから返すべき値を指定します。
`yield*` を使えば、その処理が別のジェネレーター関数に委譲されます。
ジェネレーター式の中で `return` 式が呼ばれると、それはジェネレーターに完了済みという印を付けて、戻り値として返します。
さらに `next()` を呼び出しても新しい値が返されることはありません。

**サンプルコード**

```js
// Yield Example
function * idMaker() {
  var index = 0;
  while (index < 2) {
    yield index;
    index = index + 1;
  }
}

var gen = idMaker();

gen.next().value; // 0
gen.next().value; // 1
gen.next().value; // undefined
```

`yield*` 式を使えば、ジェネレーターの繰り返しの中で別のジェネレーターを呼び出すことができます。

```js
// Yield * Example
function * genB(i) {
  yield i + 1;
  yield i + 2;
  yield i + 3;
}

function * genA(i) {
  yield i;
  yield* genB(i);
  yield i + 10;
}

var gen = genA(10);

gen.next().value; // 10
gen.next().value; // 11
gen.next().value; // 12
gen.next().value; // 13
gen.next().value; // 20
```

```js
// Generator Return Example
function* yieldAndReturn() {
  yield "Y";
  return "R";
  yield "unreachable";
}

var gen = yieldAndReturn()
gen.next(); // { value: "Y", done: false }
gen.next(); // { value: "R", done: true }
gen.next(); // { value: undefined, done: true }
```

#### <a name="external-resources-12"></a> 外部のリソース

* [Mozilla MDN Web Docs, Iterators and Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Generators)

### <a name="static-methods"></a> スタティックメソッド

#### <a name="short-explanation-1"></a> 短い説明

`static` キーワードは、スタティックメソッドを宣言するためにクラスの中で使用します。
スタティックメソッドはクラスの中の関数であり、クラスオブジェクトに所属します。
そのクラスのインスタンスからは利用することができません。

#### <a name="sample-code-8"></a> サンプルコード

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }
}

//Note that we did not have to create an instance of the Repo class
console.log(Repo.getName()) //Repo name is modern-js-cheatsheet

let r = new Repo();
console.log(r.getName()) //Uncaught TypeError: repo.getName is not a function
```

#### <a name="detailed-explanation-2"></a> 詳細な説明

スタティックメソッドは、 `this` キーワードを使えば別のスタティックメソッドの中から呼ぶことができます。
しかし、スタティックではないメソッド（訳注: 原文では「 non-static methods 」です）の場合はこれはできません。
スタティックでないメソッドが `this` キーワードを使ってスタティックメソッドに直接アクセスすることはできません。

##### <a name="calling-other-static-methods-from-a-static-method"></a> スタティックメソッドから別のスタティックメソッドを呼ぶ

スタティックメソッドを別のスタティックメソッドから呼び出すには、次のように `this` キーワードを使うことができます:

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  static modifyName(){
    return this.getName() + '-added-this'
  }
}

console.log(Repo.modifyName()) //Repo name is modern-js-cheatsheet-added-this
```

##### <a name="calling-static-methods-from-non-static-methods"></a> スタティックでないメソッドからスタティックメソッドを呼ぶ

スタティックでないメソッドからはスタティックメソッドを呼ぶ方法が 2 つあります:

Non-static methods can call static methods in 2 ways;

1. クラス名を使う

スタティックでないメソッドからスタティックメソッドにアクセスするには、クラス名を使って、プロパティのような形でスタティックメソッドを呼び出します。
例: `ClassName.StaticMethodName`

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName(){
    return Repo.getName() + ' and it contains some really important stuff'
  }
}

// we need to instantiate the class to use non-static methods
let r = new Repo()
console.log(r.useName()) //Repo name is modern-js-cheatsheet and it contains some really important stuff
```

2. コンストラクターを使う

スタティックメソッドは `constructor` オブジェクトのプロパティとして呼ぶことができます。

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName(){
    //Calls the static method as a property of the constructor
    return this.constructor.getName() + ' and it contains some really important stuff'
  }
}

// we need to instantiate the class to use non-static methods
let r = new Repo()
console.log(r.useName()) //Repo name is modern-js-cheatsheet and it contains some really important stuff
```

#### <a name="external-resources-13"></a> 外部のリソース

- [static keyword- MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static)
- [Static Methods- Javascript.info](https://javascript.info/class#static-methods)
- [Static Members in ES6- OdeToCode](http://odetocode.com/blogs/scott/archive/2015/02/02/static-members-in-es6.aspx)

## <a name="glossary"></a> 用語集

### <a name="-scope"></a> <a name="scope_def"></a> スコープ

値と式が「見え」て、参照可能な場合なコンテキストのこと。
変数やその他の式が「カレントスコープ」に無い場合は、それらは利用することができません。

ソース: [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

### <a name="-variable-mutation"></a> <a name="mutation_def"></a> 変数ミューテーション

初期値が後から変更されたとき、その変数はミューテートされた（訳注: 原文では「 have been mutated 」です）と言います。

```js
var myArray = [];
myArray.push("firstEl") // myArray is being mutated
```

もしある変数がミューテートできなければ、その変数は *イミュータブル* である（訳注: 原文では「 immutable 」です）と言います。

詳しくは、 [MDN の Mutable の記事](https://developer.mozilla.org/en-US/docs/Glossary/Mutable) をご覧ください。
