# Modern JavaScript Cheatsheet

![Modern JavaScript cheatsheet](https://i.imgur.com/aexPxMb.png)
<sub>Bildnachweis: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</sub>

> Wenn dir dieser Inhalt gefällt, kannst du mich anpingen oder mir auf Twitter folgen :+1:

[![Tweet for help](https://img.shields.io/twitter/follow/mbeaudru?label=Tweet%20%40mbeaudru&style=social)](https://twitter.com/mbeaudru/)

## Einführung

### Motivation

Dieses Dokument ist ein Spickzettel für JavaScript, das du häufig in modernen Projekten und den meisten aktuellen Beispielcodes antreffen wirst.

Dieser Leitfaden ist nicht dazu gedacht, dir JavaScript von Grund auf beizubringen, sondern ist eine Hilfe für Entwickler mit grundlegendem Wissen, die Schwierigkeiten haben, sich mit modernen Codebasen vertraut zu machen (oder sagen wir, React zu lernen), aufgrund der in JavaScript verwendeten Konzepte.

Außerdem werde ich manchmal persönliche Tipps geben, die diskutierbar sein könnten, aber ich werde darauf hinweisen, dass es eine persönliche Empfehlung ist, wenn ich das tue.

> **Hinweis:** Die meisten der hier eingeführten Konzepte stammen aus einem JavaScript Sprachupdate (ES2015, oft als ES6 bezeichnet). Neue Funktionen, die durch dieses Update hinzugefügt wurden, findest du [hier](http://es6-features.org); sehr gut gemacht.

### Ergänzende Ressourcen

Wenn du Schwierigkeiten hast, eine Vorstellung zu verstehen, schlage ich vor, dass du nach Antworten in den folgenden Ressourcen suchst:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/de/search?q=)
- [You don't know JS (Buch)](https://github.com/getify/You-Dont-Know-JS)
- [Eloquent JavaScript (Buch)](https://eloquentjavascript.net)
- [Douglas Crockford's Blog](https://www.crockford.com/javascript/)
- [ES6 Features mit Beispielen](http://es6-features.org)
- [Wes Bos Blog (ES6)](https://wesbos.com/javascript)
- [Javascript Grundlagen für Anfänger](https://www.udacity.com/course/javascript-basics--ud804) - ein kostenloser Udacity-Kurs
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) um spezifische Blogs und Ressourcen zu finden
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)

## Inhaltsverzeichnis

- [Modern JavaScript Cheatsheet](#modern-javascript-cheatsheet)
  * [Einführung](#einführung)
    + [Motivation](#motivation)
    + [Ergänzende Ressourcen](#ergänzende-ressourcen)
  * [Inhaltsverzeichnis](#inhaltsverzeichnis)
  * [Begriffe](#begriffe)
    + [Variablendeklaration: var, const, let](#variablendeklaration-var-const-let)
      - [Kurze Erklärung](#kurze-erklärung)
      - [Beispielcode](#beispielcode)
      - [Ausführliche Erklärung](#ausführliche-erklärung)
      - [Externe Ressource](#externe-ressource)
    + [Pfeilfunktion](#-pfeilfunktion)
      - [Beispielcode](#beispielcode-1)
      - [Ausführliche Erklärung](#ausführliche-erklärung-1)
        * [Prägnanz](#prägnanz)
        * [*this* Referenz](#this-referenz)
      - [Nützliche Ressourcen](#nützliche-ressourcen)
    + [Standardparameterwert für Funktionen](#standardparameterwert-für-funktionen)
      - [Externe Ressource](#externe-ressource-1)
    + [Destrukturierung von Objekten und Arrays](#destrukturierung-von-objekten-und-arrays)
      - [Erklärung mit Beispielcode](#erklärung-mit-beispielcode)
      - [Nützliche Ressourcen](#nützliche-ressourcen-1)
    + [Array-Methoden - map / filter / reduce](#array-methoden---map--filter--reduce--find)
      - [Beispielcode](#beispielcode-2)
      - [Erklärung](#erklärung)
        * [Array.prototype.map()](#arrayprototypemap)
        * [Array.prototype.filter()](#arrayprototypefilter)
        * [Array.prototype.reduce()](#arrayprototypereduce)
        * [Array.prototype.find()](#arrayprototypefind)
      - [Externe Ressource](#externe-ressource-2)
    + [Spread-Operator "..."](#spread-operator-)
      - [Beispielcode](#beispielcode-3)
      - [Erklärung](#erklärung-1)
        * [In Iterables (wie Arrays)](#in-iterables-wie-arrays)
        * [Funktionsrestparameter](#funktionsrestparameter)
        * [Objekteigenschaften ausbreiten](#objekteigenschaften-ausbreiten)
      - [Externe Ressourcen](#externe-ressourcen)
    + [Objekteigenschaften Kurzschreibweise](#objekteigenschaften-kurzschreibweise)
      - [Erklärung](#erklärung-2)
      - [Externe Ressourcen](#externe-ressourcen-1)
    + [Promises](#promises)
      - [Beispielcode](#beispielcode-4)
      - [Erklärung](#erklärung-3)
        * [Das Promise erstellen](#das-promise-erstellen)
        * [Verwendung von Promise-Handlern](#verwendung-von-promise-handlern)
      - [Externe Ressourcen](#externe-ressourcen-2)
    + [Template Literale](#template-literale)
      - [Beispielcode](#beispielcode-5)
      - [Externe Ressourcen](#externe-ressourcen-3)
    + [Tagged Template Literale](#tagged-template-literale)
      - [Externe Ressourcen](#externe-ressourcen-4)
    + [Imports / Exports](#imports--exports)
      - [Erklärung mit Beispielcode](#erklärung-mit-beispielcode-1)
        * [Benannte Exports](#benannte-exports)
        * [Standardimport / export](#standardimport--export)
      - [Externe Ressourcen](#externe-ressourcen-5)
    + [JavaScript *this*](#-javascript-this)
      - [Externe Ressourcen](#externe-ressourcen-6)
    + [Klasse](#klasse)
      - [Beispiele](#beispiele)
      - [Externe Ressourcen](#externe-ressourcen-7)
    + [Extends und super](#extends-und-super)
      - [Beispielcode](#beispielcode-6)
      - [Externe Ressourcen](#externe-ressourcen-8)
    + [Async Await](#async-await)
      - [Beispielcode](#beispielcode-7)
      - [Erklärung mit Beispielcode](#erklärung-mit-beispielcode-2)
      - [Fehlerbehandlung](#fehlerbehandlung)
      - [Externe Ressourcen](#externe-ressourcen-9)
    + [Truthy / Falsy](#truthy--falsy)
      - [Externe Ressourcen](#externe-ressourcen-10)
    + [Anamorphismen / Katamorphismen](#anamorphismen-und-katamorphismen)
      - [Anamorphismen](#anamorphismen)
      - [Katamorphismen](#katamorphismen)
      - [Externe Ressourcen](#externe-ressourcen-11)
    + [Generatoren](#generatoren)
      - [Externe Ressourcen](#externe-ressourcen-12)
    + [Statische Methoden](#statische-methoden)
      - [Kurze Erklärung](#kurze-erklärung-1)
      - [Beispielcode](#beispielcode-8)
      - [Ausführliche Erklärung](#ausführliche-erklärung-2)
        * [Andere statische Methoden aus einer statischen Methode aufrufen](#andere-statische-methoden-aus-einer-statischen-methode-aufrufen)
        * [Statische Methoden aus nicht-statischen Methoden aufrufen](#statische-methoden-aus-nicht-statischen-methoden-aufrufen)
      - [Externe Ressourcen](#externe-ressourcen-13)
  * [Glossar](#glossar)
    + [Scope](#-scope)
    + [Variablenmutation](#-variablenmutation)

## Begriffe

### Variablendeklaration: var, const, let

In JavaScript gibt es drei Schlüsselwörter, um eine Variable zu deklarieren, und jedes hat seine Unterschiede. Diese Schlüsselwörter sind ```var```, ```let``` und ```const```.

#### Kurze Erklärung

Variablen, die mit dem Schlüsselwort ```const``` deklariert sind, können nicht neu zugewiesen werden, während ```let``` und ```var``` neu zugewiesen werden können.

Ich empfehle, deine Variablen standardmäßig mit ```const``` zu deklarieren, aber mit ```let```, wenn es eine Variable ist, die du später *mutieren* oder neu zuweisen musst.

<table>
  <tr>
    <th></th>
    <th>Scope</th>
    <th>Neu zuzuweisend</th>
    <th>Veränderbar</th>
   <th><a href="#tdz_sample">Temporal Dead Zone</a></th>
  </tr>
  <tr>
    <th>const</th>
    <td>Block</td>
    <td>Nein</td>
    <td><a href="#const_mutable_sample">Ja</a></td>
    <td>Ja</td>
  </tr>
  <tr>
    <th>let</th>
    <td>Block</td>
    <td>Ja</td>
    <td>Ja</td>
    <td>Ja</td>
  </tr>
   <tr>
    <th>var</th>
    <td>Funktion</td>
    <td>Ja</td>
    <td>Ja</td>
    <td>Nein</td>
  </tr>
</table>

#### Beispielcode

```javascript
const person = "Nick";
person = "John" // Wird einen Fehler werfen, person kann nicht neu zugewiesen werden
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", Neu-Zuweisung ist erlaubt mit let
```

#### Ausführliche Erklärung

Der [*Scope*](#scope_def) einer Variable bedeutet grob "wo ist diese Variable im Code verfügbar".

##### var

```var``` deklarierte Variablen sind *funktionsumfänglich*, was bedeutet, dass, wenn eine Variable in einer Funktion erstellt wird, alles in dieser Funktion Zugriff auf diese Variable hat. Außerdem kann eine *funktionsumfängliche* Variable, die in einer Funktion erstellt wurde, nicht außerhalb dieser Funktion zugegriffen werden.

Ich empfehle dir, es dir so vorzustellen, als ob eine *X-umfängliche* Variable bedeutet, dass diese Variable eine Eigenschaft von X ist.

```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - myVar ist innerhalb der Funktion zugänglich
}
console.log(myVar); // Wirft einen ReferenceError, myVar ist außerhalb der Funktion nicht zugänglich.
```

Fokussieren wir uns immer noch auf den Variablenscope, hier ist ein subtileres Beispiel:

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // eigentlich, da myVar funktionsumfänglich ist, haben wir einfach den vorherigen myVar-Wert "Nick" durch "John" ersetzt
  }
  console.log(myVar); // "John" - sieh, wie die Anweisungen im if-Block diesen Wert beeinflusst haben
}
console.log(myVar); // Wirft einen ReferenceError, myVar ist außerhalb der Funktion nicht zugänglich.
```

Außerdem werden *var* deklarierte Variablen zum Anfang des Scopes bei der Ausführung verschoben. Dies nennt man [var hoisting](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Statements/var#var_hoisting).

Dieser Codeabschnitt:

```js
console.log(myVar) // undefined -- kein Fehler geworfen
var myVar = 2;
```

wird bei der Ausführung so verstanden:

```js
var myVar;
console.log(myVar) // undefined -- kein Fehler geworfen
myVar = 2;
```

##### let

```var``` und ```let ``` sind ungefähr gleich, aber bei ```let``` deklarierte Variablen

- haben einen *Block-Scope*
- sind **nicht** zugänglich, bevor sie zugewiesen werden
- können nicht im gleichen Scope neu deklariert werden

Lasst uns die Auswirkung der Block-Scoping anhand unseres vorherigen Beispiels sehen:

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // eigentlich, da myVar einen Block-Scope hat, haben wir gerade eine neue Variable myVar erstellt.
    // Diese Variable ist außerhalb dieses Blocks nicht zugänglich und völlig unabhängig
    // von der ersten erstellten myVar!
  }
  console.log(myVar); // "Nick", sieh, wie die Anweisungen im if-Block diesen Wert NICHT beeinflusst haben
}
console.log(myVar); // Wirft einen ReferenceError, myVar ist außerhalb der Funktion nicht zugänglich.
```

<a name="tdz_sample"></a> Nun, was es für *let* (und *const*) Variablen bedeutet, nicht zugänglich zu sein, bevor sie zugewiesen werden:

```js
console.log(myVar) // wirft einen ReferenceError !
let myVar = 2;
```

Im Gegensatz zu *var* Variablen, wenn du versuchst, eine *let* oder *const* Variable zu lesen oder zu schreiben, bevor sie zugewiesen sind, wird ein Fehler ausgelöst. Dieses Phänomen wird oft [*Temporal Dead Zone*](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Statements/let#Temporal_Dead_Zone_and_errors_with_let) oder *TDZ* genannt.

> **Hinweis:** Technisch gesehen werden *let* und *const* Variablendeklarationen auch gehoistet, aber nicht ihre Zuweisung. Da sie so gemacht sind, dass sie nicht vor der Zuweisung verwendet werden können, fühlt es sich intuitiv an, als ob es kein Hoisting gäbe, aber es gibt es. Finde mehr in [dieser sehr detaillierten Erklärung](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified) heraus, wenn du mehr wissen möchtest.

Außerdem kannst du eine *let* Variable nicht neu deklarieren:

```js
let myVar = 2;
let myVar = 3; // Wirft einen SyntaxError
```

##### const

Mit *const* deklarierte Variablen verhalten sich wie *let*-Variablen, können aber auch nicht neu zugewiesen werden.

Zusammenfassend können *const*-Variablen:

- haben einen *Block-Scope*
- sind nicht zugänglich bevor sie zugewiesen werden
- können nicht im gleichen Scope neu deklariert werden
- können nicht neu zugewiesen werden

```js
const myVar = "Nick";
myVar = "John" // Wirft einen Fehler, Neuzuweisung ist nicht erlaubt
```

```js
const myVar = "Nick";
const myVar = "John" // Wirft einen Fehler, Neudeklarierung ist nicht erlaubt
```

<a name="const_mutable_sample"></a> Aber es gibt eine Feinheit: ```const``` Variablen sind nicht [**unveränderbar**](#mutation_def)! Konkret bedeutet das, dass *Objekt*- und *Array*-```const``` deklarierte Variablen **verändert** werden können.

Für Objekte:
```js
const person = {
  name: 'Nick'
};
person.name = 'John' // das funktioniert! Die Variable person wird nicht komplett neu zugewiesen, sondern verändert
console.log(person.name) // "John"
person = "Sandra" // wirft einen Fehler, da Neu-Zuweisung nicht erlaubt ist für const deklarierte Variablen
```

Für Arrays:
```js
const person = [];
person.push('John'); // das funktioniert! Die Variable person wird nicht komplett neu zugewiesen, sondern verändert
console.log(person[0]) // "John"
person = ["Nick"] // wirft einen Fehler, da Neu-Zuweisung nicht erlaubt ist für const deklarierte Variablen
```

#### Externe Ressource

- [Wie let und const in JavaScript skopiert werden - WesBos](http://wesbos.com/javascript-scoping/)
- [Temporal Dead Zone (TDZ) Demystifiziert](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="arrow_func_concept"></a> Pfeilfunktion

Das ES6 JavaScript Update hat *Pfeilfunktionen* eingeführt, die eine weitere Methode darstellen, Funktionen zu deklarieren und zu verwenden. Hier sind die Vorteile, die sie mitbringen:

- Kürzerer Code
- *this* wird aus der Umgebung übernommen
- implizite Rückgabe

#### Beispielcode

- Kürze und implizite Rückgabe

```js
function double(x) { return x * 2; } // Traditioneller Weg
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // Gleiche Funktion als Pfeilfunktion mit impliziter Rückgabe geschrieben
console.log(double(2)) // 4
```

- *this*-Referenz

In einer Pfeilfunktion ist *this* gleich dem *this*-Wert des umschließenden Ausführungskontextes. Im Grunde musst du mit Pfeilfunktionen nicht mehr den Trick "that = this" anwenden, bevor du eine Funktion in einer Funktion aufrufst.

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### Ausführliche Erklärung

##### Prägnanz

Pfeilfunktionen sind in vielerlei Hinsicht prägnanter als traditionelle Funktionen. Lass uns alle möglichen Fälle überprüfen:

- Implizite vs. explizite Rückgabe

Eine **explizite Rückgabe** ist eine Funktion, in deren Körper das Schlüsselwort *return* verwendet wird.

```js
  function double(x) {
    return x * 2; // diese Funktion gibt explizit x * 2 zurück, das Schlüsselwort *return* wird verwendet
  }
```

Auf traditionelle Weise geschriebene Funktionen hatten immer eine explizite Rückgabe. Aber mit Pfeilfunktionen kannst du eine *implizite Rückgabe* durchführen, was bedeutet, dass du das Schlüsselwort *return* nicht verwenden musst, um einen Wert zurückzugeben.

```js
  const double = (x) => {
    return x * 2; // Hier explizite Rückgabe
  }
```

Da diese Funktion nur etwas zurückgibt (keine Anweisungen vor dem Schlüsselwort *return*), können wir eine implizite Rückgabe durchführen.

```js
  const double = (x) => x * 2; // Korrekt, gibt x*2 zurück
```

Um dies zu tun, müssen wir nur die **Klammern** und das Schlüsselwort **return** entfernen. Daher wird sie als *implizite* Rückgabe bezeichnet, das Schlüsselwort *return* ist nicht vorhanden, aber diese Funktion wird tatsächlich ```x * 2``` zurückgeben.

> **Hinweis:** Wenn deine Funktion keinen Wert zurückgibt (mit *Nebenwirkungen*), führt sie weder eine explizite noch eine implizite Rückgabe durch.

Außerdem, wenn du ein *Objekt* implizit zurückgeben möchtest, **musst du es in Klammern setzen**, da es sonst zu Konflikten mit den Blockklammern kommen würde:

```js
const getPerson = () => ({ name: "Nick", age: 24 })
console.log(getPerson()) // { name: "Nick", age: 24 } -- Objekt wird implizit durch Pfeilfunktion zurückgegeben
```

- Nur ein Argument

Wenn deine Funktion nur einen Parameter hat, kannst du die Klammern um ihn herum weglassen. Wenn wir den oben genannten *double*-Code wieder aufgreifen:

```js
  const double = (x) => x * 2; // diese Pfeilfunktion nimmt nur einen Parameter entgegen
```

Klammern um den Parameter können vermieden werden:

```js
  const double = x => x * 2; // diese Pfeilfunktion nimmt nur einen Parameter entgegen
```

- Keine Argumente

Wenn einer Pfeilfunktion kein Argument übergeben wird, musst du Klammern angeben, sonst ist die Syntax nicht gültig.

```js
  () => { // Klammern werden angegeben, alles ist in Ordnung
    const x = 2;
    return x;
  }
```

```js
  => { // Keine Klammern, das wird nicht funktionieren!
    const x = 2;
    return x;
  }
```

##### *this*-Referenz

Um diese Nuance, die mit Pfeilfunktionen eingeführt wurde, zu verstehen, muss du wissen, wie [this](#this_def) sich in JavaScript verhält.

In einer Pfeilfunktion ist *this* gleich dem *this*-Wert des umschließenden Ausführungskontextes. Das bedeutet, dass eine Pfeilfunktion kein neues *this* erstellt, sondern es stattdessen aus seiner Umgebung übernimmt.

Ohne Pfeilfunktion, wenn du in einer Funktion innerhalb einer Funktion auf eine Variable von *this* zugreifen wolltest, musstest du den Trick *that = this* oder *self = this* anwenden.

Zum Beispiel beim Verwenden der setTimeout-Funktion innerhalb von myFunc:

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // that = this Trick
  setTimeout(
    function() { // Ein neues *this* wird in diesem Funktionsbereich erstellt
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // undefiniert -- siehe Funktionsdeklaration oben
    },
    0
  );
}
```

Aber mit Pfeilfunktion wird *this* aus seiner Umgebung übernommen:

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => { // this wird aus der Umgebung übernommen, was hier myFunc bedeutet
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

#### Nützliche Ressourcen

- [Einführung in Pfeilfunktionen - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript Pfeilfunktion - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Pfeilfunktion und lexikalisches *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

### Standardparameterwert für Funktionen

Ab dem ES2015 JavaScript Update kannst du deinen Funktionsparametern Standardwerte zuweisen, indem du folgende Syntax verwendest:

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- kein Wert wird übergeben, daher wird dem x in myFunc der Standardwert 10 zugewiesen
console.log(myFunc(5)) // 5 -- ein Wert wird übergeben, daher ist x gleich 5 in myFunc

console.log(myFunc(undefined)) // 10 -- der Wert undefined wird übergeben, daher wird der Standardwert dem x zugewiesen
console.log(myFunc(null)) // null -- ein Wert (null) wird übergeben, siehe unten für weitere Details
```

Der Standardparameter wird in zwei und nur zwei Situationen angewendet:

- Kein Parameter übergeben
- *undefined* Parameter übergeben

Anders ausgedrückt, wenn du *null* übergibst, wird der Standardparameter **nicht angewendet**.

> **Hinweis:** Die Zuweisung eines Standardwerts kann auch mit destrukturierten Parametern verwendet werden (siehe nächste Notion, um ein Beispiel zu sehen)

#### Externe Ressource

- [Standardparameterwert - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Standardparameter - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

### Destrukturierung von Objekten und Arrays

*Destrukturierung* ist eine praktische Methode, neue Variablen zu erstellen, indem einige Werte aus in Objekten oder Arrays gespeicherten Daten extrahiert werden.

Um nur einige Anwendungsfälle zu nennen, kann die *Destrukturierung* verwendet werden, um Funktionsparameter oder *this.props* in React-Projekten zu destrukturieren.

#### Erklärung mit Beispielcode

- Objekt

Betrachten wir das folgende Objekt für alle Beispiele:

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

Ohne Destrukturierung

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

Mit Destrukturierung, alles in einer Zeile:

```js
const { firstName: first, age, city = "Paris" } = person; // Das war's !

console.log(age) // 35 -- Eine neue Variable age wird erstellt und ist gleich person.age
console.log(first) // "Nick" -- Eine neue Variable first wird erstellt und ist gleich person.firstName
console.log(firstName) // ReferenceError -- person.firstName existiert, ABER die neu erstellte Variable ist als first benannt
console.log(city) // "Paris" -- Eine neue Variable city wird erstellt und da person.city undefiniert ist, ist city gleich dem bereitgestellten Standardwert "Paris".
```

**Hinweis:** In ```const { age } = person;``` werden die Klammern nach dem *const*-Schlüsselwort nicht verwendet, um ein Objekt oder einen Block zu deklarieren, sondern es ist die *Destrukturierungssyntax*.

- Funktionsparameter

*Destrukturierung* wird häufig verwendet, um Objektparameter in Funktionen zu destrukturieren.

Ohne Destrukturierung

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

Bei der Destrukturierung des Objektparameters *person* erhalten wir eine präzisere Funktion:

```js
function joinFirstLastName({ firstName, lastName }) { // wir erstellen Variablen firstName und lastName durch Destrukturierung des person-Parameters
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

Destrukturierung ist noch angenehmer mit [Pfeilfunktionen](#arrow_func_concept) zu verwenden:

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```

- Array

Betrachten wir das folgende Array:

```js
const myArray = ["a", "b", "c"];
```

Ohne Destrukturierung

```js
const x = myArray[0];
const y = myArray[1];
```

Mit Destrukturierung

```js
const [x, y] = myArray; // Das war's !

console.log(x) // "a"
console.log(y) // "b"
```

#### Nützliche Ressourcen

- [ES6 Features - Destrukturierende Zuweisung](http://es6-features.org/#ArrayMatching)
- [Objektdestrukturierung - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destrukturierung](http://exploringjs.com/es6/ch_destructuring.html)

### Array-Methoden - map / filter / reduce / find

*Map*, *filter*, *reduce* und *find* sind Array-Methoden, die aus einem Programmierparadigma namens [*funktionale Programmierung*](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0) stammen.

Zusammengefasst:

- **Array.prototype.map()** nimmt ein Array, führt eine Operation auf seinen Elementen durch und gibt ein Array mit den transformierten Elementen zurück.
- **Array.prototype.filter()** nimmt ein Array, entscheidet elementweise, ob es dieses behalten will oder nicht, und gibt ein Array nur mit den behaltenen Elementen zurück.
- **Array.prototype.reduce()** nimmt ein Array und aggregiert die Elemente zu einem einzelnen Wert (der zurückgegeben wird).
- **Array.prototype.find()** nimmt ein Array und gibt das erste Element zurück, das die bereitgestellte Bedingung erfüllt.

Ich empfehle, sie so oft wie möglich zu verwenden, indem du den Prinzipien der funktionalen Programmierung folgst, da sie zusammensetzbar, prägnant und elegant sind.

Mit diesen vier Methoden kannst du in den meisten Situationen die Verwendung von *for* und *forEach* Schleifen vermeiden. Wenn du versucht bist, eine *for*-Schleife zu machen, versuche es mit *map*, *filter*, *reduce* und *find* zusammengesetzt. Es könnte anfangs schwierig sein, da es dich zwingt, eine neue Denkweise zu erlernen, aber sobald du es beherrschst, wird alles einfacher.

#### Beispielcode

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
const doubledNumbers = numbers.map(n => n * 2); // [0, 2, 4, 6, 8, 10, 12]
const evenNumbers = numbers.filter(n => n % 2 === 0); // [0, 2, 4, 6]
const sum = numbers.reduce((prev, next) => prev + next, 0); // 21
const greaterThanFour = numbers.find((n) => n>4); // 5
```

Berechne die Gesamtsumme der Noten für Schüler mit Noten 10 oder darüber, indem du map, filter und reduce zusammensetzt:

```js
const students = [
  { name: "Nick", grade: 10 },
  { name: "John", grade: 15 },
  { name: "Julia", grade: 19 },
  { name: "Nathalie", grade: 9 },
];

const aboveTenSum = students
  .map(student => student.grade) // wir mappen das students Array auf ein Array ihrer Noten
  .filter(grade => grade >= 10) // wir filtern das Noten-Array, um diejenigen 10 oder darüber zu behalten
  .reduce((prev, next) => prev + next, 0); // wir summieren alle Noten 10 oder darüber nacheinander

console.log(aboveTenSum) // 44 -- 10 (Nick) + 15 (John) + 19 (Julia), Nathalie unter 10 wird ignoriert
```

#### Erklärung

Betrachten wir das folgende Array von Zahlen für unsere Beispiele:

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

Was passiert hier? Wir verwenden .map auf dem *numbers*-Array, die Map iteriert über jedes Element des Arrays und übergibt es unserer Funktion. Das Ziel der Funktion ist es, einen neuen Wert aus dem übergebenen Wert zu erzeugen und zurückzugeben, so dass map ihn ersetzen kann.

Lasst uns diese Funktion extrahieren, um es einmal klarer zu machen:

```js
const doubleN = function(n) { return n * 2; };
const doubledNumbers = numbers.map(doubleN);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

**Hinweis**: Du wirst diese Methode oft in Kombination mit [Pfeilfunktionen](#-pfeilfunktion) antreffen

```js
const doubledNumbers = numbers.map(n => n * 2);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

```numbers.map(doubleN)``` produziert ```[doubleN(0), doubleN(1), doubleN(2), doubleN(3), doubleN(4), doubleN(5), doubleN(6)]```, was gleich ```[0, 2, 4, 6, 8, 10, 12]``` ist.

> **Hinweis:** Wenn du kein neues Array zurückgeben musst und nur eine Schleife mit Nebeneffekten machen willst, solltest du vielleicht stattdessen eine for / forEach-Schleife anstelle von map verwenden.

##### Array.prototype.filter()

```js
const evenNumbers = numbers.filter(function(n) {
  return n % 2 === 0; // true, wenn "n" gerade ist, false, wenn "n" ungerade ist
});
console.log(evenNumbers); // [0, 2, 4, 6]
```

**Hinweis**: Du wirst diese Methode oft in Kombination mit [Pfeilfunktionen](#-pfeilfunktion) antreffen

```js
const evenNumbers = numbers.filter(n => n % 2 === 0);
console.log(evenNumbers); // [0, 2, 4, 6]
```

Wir verwenden .filter auf dem *numbers*-Array, filter iteriert über jedes Element des Arrays und übergibt es unserer Funktion. Das Ziel der Funktion ist es, einen Boolean zurückzugeben, der bestimmt, ob der aktuelle Wert behalten wird oder nicht. Filter gibt dann das Array nur mit den behaltenen Werten zurück.

##### Array.prototype.reduce()

Das Ziel der reduce-Methode ist es, alle Elemente des Arrays, über das sie iteriert, in einen einzigen Wert zu *reduzieren*. Wie diese Elemente aggregiert werden, liegt bei dir.

```js
const sum = numbers.reduce(
  function(acc, n) {
    return acc + n;
  },
  0 // Wert der Akkumulatorvariablen beim ersten Iterationsschritt
);

console.log(sum) // 21
```

**Hinweis**: Du wirst diese Methode oft in Kombination mit [Pfeilfunktionen](#-pfeilfunktion) antreffen

```js
const sum = numbers.reduce((acc, n) => acc + n, 0);
console.log(sum) // 21
```

Wie bei den .map- und .filter-Methoden wird .reduce auf einem Array angewandt und nimmt eine Funktion als ersten Parameter.

Diesmal gibt es allerdings Änderungen:

- .reduce nimmt zwei Parameter

Der erste Parameter ist eine Funktion, die bei jedem Iterationsschritt aufgerufen wird.

Der zweite Parameter ist der Wert der Akkumulatorvariablen (*acc* hier) beim ersten Iterationsschritt (lies den nächsten Punkt, um dies zu verstehen).

- Funktionsparameter

Die Funktion, die du als ersten Parameter von .reduce übergibst, nimmt zwei Parameter entgegen. Der erste (*acc* hier) ist die Akkumulatorvariable, während der zweite Parameter (*n*) das aktuelle Element ist.

Die Akkumulatorvariable entspricht dem Rückgabewert deiner Funktion im **vorherigen** Iterationsschritt. Beim ersten Schritt der Iteration ist *acc* gleich dem Wert, den du als zweiten Parameter von .reduce übergeben hast.

###### Beim ersten Iterationsschritt

```acc = 0```, weil wir 0 als zweiten Parameter für reduce übergeben haben

```n = 0```, erstes Element des *numbers*-Arrays

Die Funktion gibt *acc* + *n* --> 0 + 0 --> 0 zurück

###### Beim zweiten Iterationsschritt

```acc = 0```, weil es der Wert ist, den die Funktion im vorherigen Iterationsschritt zurückgegeben hat

```n = 1```, zweites Element des *numbers*-Arrays

Die Funktion gibt *acc* + *n* --> 0 + 1 --> 1 zurück

###### Beim dritten Iterationsschritt

```acc = 1```, weil es der Wert ist, den die Funktion im vorherigen Iterationsschritt zurückgegeben hat

```n = 2```, drittes Element des *numbers*-Arrays

Die Funktion gibt *acc* + *n* --> 1 + 2 --> 3 zurück

###### Beim vierten Iterationsschritt

```acc = 3```, weil es der Wert ist, den die Funktion im vorherigen Iterationsschritt zurückgegeben hat

```n = 3```, viertes Element des *numbers*-Arrays

Die Funktion gibt *acc* + *n* --> 3 + 3 --> 6 zurück

###### [...] Beim letzten Iterationsschritt

```acc = 15```, weil es der Wert ist, den die Funktion im vorherigen Iterationsschritt zurückgegeben hat

```n = 6```, letztes Element des *numbers*-Arrays

Die Funktion gibt *acc* + *n* --> 15 + 6 --> 21 zurück

Da dies der letzte Iterationsschritt ist, gibt **.reduce** 21 zurück.

##### Array.prototype.find()

```js
const greaterThanZero = numbers.find(function(n) {
  return n > 0; // gibt die Nummer zurück, die gerade größer als 0 ist
});
console.log(greaterThanZero); // 1
```

**Hinweis**: Du wirst diese Methode oft in Kombination mit [Pfeilfunktionen](#-pfeilfunktion) antreffen

Wir verwenden .find auf dem *numbers*-Array, .find iteriert über jedes Element des Arrays und übergibt es unserer Funktion, bis die Bedingung erfüllt ist. Das Ziel der Funktion ist es, das Element zurückzugeben, das die aktuelle Testfunktion erfüllt. Die .find-Methode führt die Callback-Funktion einmal für jeden Index des Arrays aus, bis der Callback einen wahren Wert zurückgibt.

**Hinweis**: Sie gibt sofort den Wert des Elements zurück (das die Bedingung erfüllt), wenn gefunden. Andernfalls gibt sie undefined zurück.

#### Externe Ressource

- [Verständnis von map / filter / reduce in JS](https://hackernoon.com/understanding-map-filter-and-reduce-in-javascript-5df1c7eee464)

### Spread-Operator "..."

Der Spread-Operator ```...``` wurde mit ES2015 eingeführt und wird verwendet, um Elemente eines iterierbaren Objekts (wie ein Array) an Stellen auszubreiten, an denen mehrere Elemente passen können.

#### Beispielcode

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

#### Erklärung

##### In Iterables (wie Arrays)

Wenn wir die folgenden zwei Arrays haben:

```js
const arr1 = ["a", "b", "c"];
const arr2 = [arr1, "d", "e", "f"]; // [["a", "b", "c"], "d", "e", "f"]
```

*arr2* das erste Element ist ein Array, weil *arr1* so, wie es ist, in *arr2* eingefügt wird. Aber was wir wollen, ist, dass *arr2* ein Array von Buchstaben ist. Um dies zu erreichen, können wir die Elemente von *arr1* in *arr2* *ausbreiten*.

Mit dem Spread-Operator

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

##### Funktionsrestparameter

In Funktionsparametern können wir den Rest-Operator verwenden, um Parameter in einem Array einzufügen, über das wir iterieren können. Es gibt bereits ein **arguments**-Objekt, das an jede Funktion gebunden ist und einem Array mit allen Parametern entspricht, die in die Funktion eingegeben wurden.

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

Aber nehmen wir an, dass wir wollen, dass diese Funktion einen neuen Schüler mit seinen Noten und seinem Durchschnitt erstellt. Wäre es nicht praktischer, die ersten beiden Parameter in zwei separate Variablen zu extrahieren und dann alle Noten in einem Array zu haben, über das wir iterieren können?

Genau das ermöglicht der Rest-Operator!

```js
function createStudent(firstName, lastName, ...grades) {
  // firstName = "Nick"
  // lastName = "Anderson"
  // [10, 12, 6] -- "..." nimmt alle anderen übergebenen Parameter und erzeugt eine "grades"-Arrayvariable, die sie enthält

  const avgGrade = grades.reduce((acc, curr) => acc + curr, 0) / grades.length; // berechnet den Durchschnitt aus den Noten

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

> **Hinweis:** Die Funktion createStudent ist schlecht, weil wir nicht überprüfen, ob grades.length existiert oder verschieden von 0 ist. Aber so ist es einfacher zu lesen, deshalb habe ich diesen Fall nicht behandelt.

##### Objekteigenschaften ausbreiten

Für dieses Beispiel empfehle ich, die vorherigen Erklärungen zum Rest-Operator bei iterierbaren Objekten und Funktionsparametern zu lesen.

```js
const myObj = { x: 1, y: 2, a: 3, b: 4 };
const { x, y, ...z } = myObj; // Objektdestrukturierung hier
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

// z sind die restlichen Eigenschaften des destrukturierten Objekts: myObj-Objekt minus x- und y-Eigenschaften, die destrukturiert wurden

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }

// Hier werden die Eigenschaften von z-Objekten in n ausgespreitet
```

#### Externe Ressourcen

- [TC39 - Objekt rest/spread](https://github.com/tc39/proposal-object-rest-spread)
- [Einführung in den Spread-Operator - WesBos](https://github.com/wesbos/es6-articles/blob/master/28%20-%20Spread%20Operator%20Introduction.md)
- [JavaScript & der Spread-Operator](https://codeburst.io/javascript-the-spread-operator-a867a71668ca)
- [6 großartige Verwendungen des Spread-Operators](https://davidwalsh.name/spread-operator)

### Objekteigenschaften Kurzschreibweise

Wenn man einer Objekteigenschaft eine Variable zuweist, deren Name gleich dem Eigenschaftsnamen ist, kann man folgendes tun:

```js
const x = 10;
const myObj = { x };
console.log(myObj.x) // 10
```

#### Erklärung

Normalerweise (vor ES2015) wenn du ein neues *Objektliteral* deklarierst und Variablen als Werte für Objekteigenschaften verwenden möchtest, würdest du diesen Code schreiben:

```js
const x = 10;
const y = 20;

const myObj = {
  x: x, // weist x Variable Wert myObj.x zu
  y: y // weist y Variable Wert myObj.y zu
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```

Wie du sehen kannst, ist das ziemlich wiederholend, weil die Namen der Eigenschaften von myObj den Variablennamen entsprechen, die du diesen zuweisen willst.

Mit ES2015 kannst du diese Abkürzung verwenden, wenn der Variablenname dem Namen der Eigenschaft entspricht:

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

#### Externe Ressourcen

- [Property shorthand - ES6 Features](http://es6-features.org/#PropertyShorthand)


### Promises

Ein Promise ist ein Objekt, das synchron aus einer asynchronen Funktion zurückgegeben werden kann ([ref](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261#3cd0)).

Promises können verwendet werden, um der [Callback-Hölle](http://callbackhell.com/) zu entkommen, und sie begegnen uns in modernen JavaScript-Projekten immer häufiger.

#### Beispielcode

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

#### Erklärung

Wenn du eine *Ajax-Anfrage* machst, ist die Antwort nicht synchron, weil du eine Ressource anforderst, die einige Zeit zur Antwort braucht. Sie könnte sogar nie kommen, falls die angeforderte Ressource aus irgendeinem Grund nicht verfügbar ist (404).

Um diese Art von Situation zu handhaben, hat uns ES2015 *Promises* gegeben. Promises können drei verschiedene Zustände haben:

- Pending (Im Warten)
- Fulfilled (Erfüllt)
- Rejected (Abgelehnt)

Nehmen wir an, wir möchten Promises verwenden, um eine Ajax-Anfrage zu tätigen und die Ressource X zu holen.

##### Das Promise erstellen

Zuerst erstellen wir ein Promise. Wir verwenden die jQuery get-Methode, um unsere Ajax-Anfrage an X zu stellen.

```js
const xFetcherPromise = new Promise( // Erstelle Promise mit dem "new" Schlüsselwort und speichere es in einer Variable
  function(resolve, reject) { // Der Promise-Konstruktor nimmt eine Funktion entgegen, die selbst die Parameter resolve und reject besitzt
    $.get("X") // Starte die Ajax-Anfrage
      .done(function(X) { // Sobald die Anfrage beendet ist...
        resolve(X); // ... erfülle das Promise mit dem Wert X als Parameter
      })
      .fail(function(error) { // Falls die Anfrage fehlschlägt...
        reject(error); // ... lehne das Promise mit dem Fehler als Parameter ab
      });
  }
)
```

Wie im obigen Beispiel zu sehen ist, nimmt das Promise-Objekt eine *Executor*-Funktion entgegen, die zwei Parameter **resolve** und **reject** hat. Diese Parameter sind Funktionen, die, wenn aufgerufen, den Promise-Zustand *pending* jeweils in einen *fulfilled* und *rejected* Zustand überführen.

Das Promise befindet sich in einem Pending-Zustand nach seiner Erstellung, und seine *Executor*-Funktion wird sofort ausgeführt. Sobald eine der Funktionen *resolve* oder *reject* in der *Executor*-Funktion aufgerufen wird, ruft das Promise seine zugehörigen Handler auf.

##### Verwendung von Promise-Handlern

Um das Ergebnis (oder den Fehler) des Promises zu erhalten, müssen wir ihm Handler zuweisen, indem wir Folgendes tun:

```js
xFetcherPromise
  .then(function(X) {
    console.log(X);
  })
  .catch(function(err) {
    console.log(err)
  })
```

Wenn das Promise erfolgreich ist, wird *resolve* ausgeführt und die Funktion, die als `.then` Parameter übergeben wurde, wird ausgeführt.

Wenn es fehlschlägt, wird *reject* ausgeführt und die Funktion, die als `.catch` Parameter übergeben wurde, wird ausgeführt.

> **Hinweis :** Wenn das Promise bereits erfüllt oder abgelehnt wurde, wenn ein entsprechender Handler angehängt wird, wird der Handler aufgerufen, sodass es keinen Wettlaufzustand zwischen dem Abschluss einer asynchronen Operation und dem Anhängen ihrer Handler gibt. [(Ref: MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise#Description)

#### Externe Ressourcen

- [JavaScript Promises für Dummys - Jecelyn Yeen](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [JavaScript Promise API - David Walsh](https://davidwalsh.name/promises)
- [Promises verwenden - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [Was ist ein Promise - Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- [JavaScript Promises: Eine Einführung - Jake Archibald](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
- [Promise Dokumentation - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

### Template Literale

Template Literale sind eine [*Ausdrucksinterpolation*](https://en.wikipedia.org/wiki/String_interpolation) für ein- und mehrzeilige Strings.

Anders ausgedrückt, handelt es sich um eine neue String-Syntax, in der du bequem jede JavaScript-Ausdrücke verwenden kannst (beispielsweise Variablen).

#### Beispielcode

```js
const name = "Nick";
`Hallo ${name}, der folgende Ausdruck ist gleich vier : ${2+2}`;

// Hallo Nick, der folgende Ausdruck ist gleich vier: 4
```

#### Externe Ressourcen

- [String-Interpolation - ES6 Features](http://es6-features.org/#StringInterpolation)
- [ES6 Template Literale - Addy Osmani](https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

### Tagged Template Literale

Template Tags sind *Funktionen, die einem [Template Literal](#template-literals) vorangestellt werden können*. Wenn eine Funktion auf diese Weise aufgerufen wird, ist der erste Parameter ein Array der *Strings*, die zwischen den interpolierten Variablen des Templates auftreten, und die nachfolgenden Parameter sind die interpolierten Werte. Verwende einen Spread-Operator `...`, um alle zu erfassen. [(Ref: MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#Tagged_template_literals).

> **Hinweis :** Eine berühmte Bibliothek namens [styled-components](https://www.styled-components.com/) setzt schwer auf dieses Feature.

Hier ist ein Spielzeugbeispiel, wie sie funktionieren.
```js
function highlight(strings, ...values) {
  const interpolation = strings.reduce((prev, current) => {
    return prev + current + (values.length ? "<mark>" + values.shift() + "</mark>" : "");
  }, "");

  return interpolation;
}

const condiment = "Marmelade";
const meal = "Toast";

highlight`Ich mag ${condiment} auf ${meal}.`;
// "Ich mag <mark>Marmelade</mark> auf <mark>Toast</mark>."
```

Ein interessanteres Beispiel:
```js
function comma(strings, ...values) {
  return strings.reduce((prev, next) => {
    let value = values.shift() || [];
    value = value.join(", ");
    return prev + next + value;
  }, "");
}

const snacks = ['Äpfel', 'Bananen', 'Kirschen'];
comma`Ich mag ${snacks} zum Knabbern.`;
// "Ich mag Äpfel, Bananen, Kirschen zum Knabbern."
```

#### Externe Ressourcen
- [Wes Bos zu gekennzeichneten Template Literalen](http://wesbos.com/tagged-template-literals/)
- [Bibliothek von gängigen Template Tags](https://github.com/declandewet/common-tags)

### Imports / Exports

ES6-Module werden verwendet, um auf Variablen oder Funktionen in einem Modul zuzugreifen, die explizit von den Modulen exportiert wurden, die es importiert.

Ich empfehle dringend, sich die Ressourcen von MDN zu Import/Export anzusehen (siehe externe Ressourcen unten), da sie sowohl unkompliziert als auch vollständig sind.

#### Erklärung mit Beispielcode

##### Benannte Exports

Mit benannten Exports können mehrere Werte aus einem Modul exportiert werden.

> **Hinweis :** Du kannst nur [Erstklassige Bürger](https://en.wikipedia.org/wiki/First-class_citizen) mit einem Namen benannt exportieren.

```js
// mathConstants.js
export const pi = 3.14;
export const exp = 2.7;
export const alpha = 0.35;

// -------------

// myFile.js
import { pi, exp } from './mathConstants.js'; // Benannter Import -- Destructuring-ähnliche Syntax
console.log(pi) // 3.14
console.log(exp) // 2.7

// -------------

// mySecondFile.js
import * as constants from './mathConstants.js'; // Injiziere alle exportierten Werte in die Variable constants
console.log(constants.pi) // 3.14
console.log(constants.exp) // 2.7
```

Obwohl benannte Imports wie *Destructuring* aussehen, haben sie eine andere Syntax und sind nicht dasselbe. Sie unterstützen keine Standardwerte oder *tiefes* Destructuring.

Außerdem kannst du Aliase verwenden, aber die Syntax ist anders als die, die beim Destructuring verwendet wird:

```js
import { foo as bar } from 'myFile.js'; // foo wird importiert und in eine neue bar Variable injiziert
```

##### Standardimport / export

Bezüglich des Standardexports gibt es nur einen einzigen Standardexport pro Modul. Ein Standardexport kann eine Funktion, eine Klasse, ein Objekt oder irgendetwas anderes sein. Dieser Wert wird als der "Haupt"-exportierte Wert angesehen, da er am einfachsten zu importieren ist. [Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description)

```js
// coolNumber.js
const ultimateNumber = 42;
export default ultimateNumber;

// ------------

// myFile.js
import number from './coolNumber.js';
// Standardexport, unabhängig von seinem Namen, wird automatisch in die Variable number injiziert;
console.log(number) // 42
```

Exportieren einer Funktion:

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

#### Externe Ressourcen

- [ES6-Module in Stichpunkten](https://ponyfoo.com/articles/es6#modules)
- [Export - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
- [Import - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Verständnis von ES6-Modulen](https://www.sitepoint.com/understanding-es6-modules/)
- [Destructuring Sonderfall - Importanweisungen](https://ponyfoo.com/articles/es6-destructuring-in-depth#special-case-import-statements)
- [Missverständnisse bezüglich ES6-Modulen - Kent C. Dodds](https://medium.com/@kentcdodds/misunderstanding-es6-modules-upgrading-babel-tears-and-a-solution-ad2d5ab93ce0)
- [Module in JavaScript](http://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript)

### <a name="this_def"></a> JavaScript *this*

Der *this*-Operator verhält sich anders als in anderen Sprachen und wird in den meisten Fällen durch die Art und Weise bestimmt, wie eine Funktion aufgerufen wird. ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)).

Diese Vorstellung hat viele Feinheiten und ist ziemlich schwierig, daher schlage ich vor, in die unten aufgeführten externen Ressourcen einzutauchen. Ich werde das wiedergeben, was ich persönlich im Kopf habe, um zu bestimmen, was *this* gleich ist. Ich habe diesen Tipp aus [diesem Artikel von Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/) gelernt.

```js
function myFunc() {
  ...
}

// Nach jeder Anweisung findest du den Wert von *this* in myFunc

myFunc.call("myString", "hallo") // "myString" -- der erste .call-Parameterwert wird in *this* injiziert

// Im Nicht-Strict-Modus
myFunc("hallo") // window -- myFunc() ist syntaktischer Zucker für myFunc.call(window, "hallo")

// Im Strict-Modus
myFunc("hallo") // undefined -- myFunc() ist syntaktischer Zucker für myFunc.call(undefined, "hallo")
```

```js
var person = {
  myFunc: function() { ... }
}

person.myFunc.call(person, "test") // person Objekt -- der erste call-Parameter wird in *this* injiziert
person.myFunc("test") // person Objekt -- person.myFunc() ist syntaktischer Zucker für person.myFunc.call(person, "test")

var myBoundFunc = person.myFunc.bind("hallo") // Erstellt eine neue Funktion, in der wir "hallo" in den *this*-Wert injizieren
person.myFunc("test") // person Objekt -- Die bind-Methode hat keine Auswirkung auf die Originalmethode
myBoundFunc("test") // "hallo" -- myBoundFunc ist person.myFunc mit "hallo" gebunden an *this*
```

#### Externe Ressourcen

- [Verständnis von JavaScript-Funktionsaufrufen und "this" - Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)
- [JavaScript this - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

### Klasse

JavaScript ist eine [prototypbasierte](https://en.wikipedia.org/wiki/Prototype-based_programming) Sprache (während Java beispielsweise eine [klassenbasierte](https://en.wikipedia.org/wiki/Class-based_programming) Sprache ist). ES6 hat JavaScript-Klassen eingeführt, die als syntaktischer Zucker für die prototypbasierte Vererbung gedacht sind und **kein** neues klassenbasiertes Vererbungsmodell darstellen ([ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)).

Das Wort *class* ist tatsächlich irreführend, wenn du mit Klassen in anderen Sprachen vertraut bist. Wenn du es bist, vermeide Annahmen darüber, wie JavaScript-Klassen funktionieren, auf dieser Grundlage und betrachte es als eine völlig unterschiedliche Vorstellung.

Da dieses Dokument nicht den Anspruch hat, dir die Sprache von Grund auf beizubringen, gehe ich davon aus, dass du weißt, was Prototypen sind und wie sie sich verhalten. Wenn nicht, sieh dir die unten aufgeführten externen Ressourcen nach dem Beispielcode an.


#### Beispiele

Vor ES6, Prototyp-Syntax:

```js
var Person = function(name, age) {
  this.name = name;
  this.age = age;
}
Person.prototype.stringSentence = function() {
  return "Hallo, mein Name ist " + this.name + " und ich bin " + this.age;
}
```

Mit ES6-Klassensyntax:

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  stringSentence() {
    return `Hallo, mein Name ist ${this.name} und ich bin ${this.age}`;
  }
}

const myPerson = new Person("Manu", 23);
console.log(myPerson.age) // 23
console.log(myPerson.stringSentence()) // "Hallo, mein Name ist Manu und ich bin 23
```

#### Externe Ressourcen

Zum Verständnis von Prototypen:

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Vererbung und die Prototyp-Kette - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

Zum Verständnis von Klassen:

- [ES6 Klassen im Detail - Nicolas Bevacqua](https://ponyfoo.com/articles/es6-classes-in-depth)
- [ES6-Features - Klassen](http://es6-features.org/#ClassDefinition)
- [JavaScript Klassen - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

### `Extends` und `super`

Das Schlüsselwort `extends` wird in Klassendeklarationen oder Klassenausdrücken verwendet, um eine Klasse zu erstellen, die ein Kind einer anderen Klasse ist ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends)). Die Unterklasse erbt alle Eigenschaften der Oberklasse und kann zusätzlich neue Eigenschaften hinzufügen oder die geerbten modifizieren.

Das Schlüsselwort `super` wird verwendet, um Funktionen eines Oberobjekts aufzurufen, einschließlich seines Konstruktors.

- Das Schlüsselwort `super` muss verwendet werden, bevor das Schlüsselwort `this` im Konstruktor verwendet wird.
- Der Aufruf von `super()` ruft den Konstruktor der Oberklasse auf. Wenn du einige Argumente im Konstruktor einer Klasse an den Konstruktor ihres Elternteils weitergeben möchtest, rufst du ihn mit `super(arguments)` auf.
- Wenn die Oberklasse eine Methode (auch statisch) namens `X` hat, kannst du mit `super.X()` diese in einer Unterklasse aufrufen.

#### Beispielcode

```js
class Polygon {
  constructor(height, width) {
    this.name = 'Polygon';
    this.height = height;
    this.width = width;
  }

  getHelloPhrase() {
    return `Hallo, ich bin ein ${this.name}`;
  }
}

class Square extends Polygon {
  constructor(length) {
    // Hier wird der Konstruktor der Oberklasse mit den Längen
    // für die Breite und Höhe des Polygons aufgerufen
    super(length, length);
    // Hinweis: In abgeleiteten Klassen muss super() aufgerufen werden, bevor du
    // 'this' verwenden kannst. Wenn du dies auslässt, wird ein Referenzfehler verursacht.
    this.name = 'Quadrat';
    this.length = length;
  }

  getCustomHelloPhrase() {
    const polygonPhrase = super.getHelloPhrase(); // Zugriff auf die Elternmethode mit super.X()-Syntax
    return `${polygonPhrase} mit einer Länge von ${this.length}`;
  }

  get area() {
    return this.height * this.width;
  }
}

const mySquare = new Square(10);
console.log(mySquare.area) // 100
console.log(mySquare.getHelloPhrase()) // 'Hallo, ich bin ein Quadrat' -- Square erbt von Polygon und hat Zugriff auf seine Methoden
console.log(mySquare.getCustomHelloPhrase()) // 'Hallo, ich bin ein Quadrat mit einer Länge von 10'
```

**Hinweis :** Wenn wir versucht hätten, `this` vor dem Aufruf von `super()` in der Square-Klasse zu verwenden, wäre ein ReferenceError ausgelöst worden:

```js
class Square extends Polygon {
  constructor(length) {
    this.height; // ReferenceError, super muss zuerst aufgerufen werden!

    // Hier wird der Konstruktor der Oberklasse mit den Längen
    // für die Breite und Höhe des Polygons aufgerufen
    super(length, length);

    // Hinweis: In abgeleiteten Klassen muss super() aufgerufen werden bevor du
    // 'this' verwenden kannst. Wenn du dies auslässt, wird ein Referenzfehler verursacht.
    this.name = 'Quadrat';
  }
}
```

#### Externe Ressourcen

- [Extends - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends)
- [Super-Operator - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super)
- [Vererbung - MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance)

### Async Await

Zusätzlich zu [Promises](#promises) gibt es eine neue Syntax, die du vielleicht antriffst, um asynchronen Code zu handhaben, nämlich *async / await*.

Der Zweck von async/await-Funktionen ist es, die Verwendung von Promises synchron zu vereinfachen und ein Verhalten für eine Gruppe von Promises durchzuführen. Genau wie Promises ähnlich wie strukturierte Callbacks sind, ist async/await ähnlich wie die Kombination von Generatoren und Promises. Async-Funktionen geben *immer* ein Promise zurück. ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function))

> **Hinweis :** Du musst verstehen, was Promises sind und wie sie funktionieren, bevor du versuchst, async / await zu verstehen, da diese darauf basieren.

> **Hinweis 2:** [*await* muss in einer *async* Funktion verwendet werden](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9#f3f0), was bedeutet, dass du await nicht auf der obersten Ebene unseres Codes verwenden kannst, da dies nicht innerhalb einer async-Funktion ist.

#### Beispielcode

```js
async function getGithubUser(username) { // das async-Schlüsselwort ermöglicht die Verwendung von await in der Funktion und bedeutet, dass die Funktion ein Promise zurückgibt
  const response = await fetch(`https://api.github.com/users/${username}`); // Die Ausführung wird hier pausiert, bis das von fetch zurückgegebene Promise aufgelöst ist
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user)) // das Nutzer-Response loggen - await-Syntax kann nicht verwendet werden, da dieser Code nicht in einer async-Funktion ist
  .catch(err => console.log(err)); // wenn ein Fehler in unserer async-Funktion geworfen wird, werden wir ihn hier erwischen
```

#### Erklärung mit Beispielcode

*Async / Await* basiert auf Promises, ermöglicht aber eine imperativere Code-Stil.

Der *async*-Operator markiert eine Funktion als asynchron und wird immer ein *Promise* zurückgeben. Du kannst den *await*-Operator in einer *async*-Funktion verwenden, um die Ausführung in dieser Zeile zu pausieren, bis das vom Ausdruck zurückgegebene Promise entweder aufgelöst oder abgelehnt wird.

```js
async function myFunc() {
  // wir können den await-Operator verwenden, weil diese Funktion async ist
  return "hallo welt";
}

myFunc().then(msg => console.log(msg)) // "hallo welt" -- der Rückgabewert von myFunc wird durch den async-Operator in ein Promise umgewandelt
```

Wenn das *return*-Statement einer async-Funktion erreicht wird, wird das Promise mit dem zurückgegebenen Wert erfüllt. Wenn innerhalb einer async-Funktion ein Fehler geworfen wird, wechselt der Promise-Zustand zu *abgelehnt*. Wenn aus einer async-Funktion kein Wert zurückgegeben wird, wird trotzdem ein Promise zurückgegeben und löst ohne Wert auf, wenn die Ausführung der async-Funktion abgeschlossen ist.

Der *await*-Operator wird verwendet, um auf die Erfüllung eines *Promise* zu warten und kann nur im Körper einer *async*-Funktion verwendet werden. Beim Auftreffen wird die Codeausführung pausiert, bis das Promise erfüllt ist.

> **Hinweis :** *fetch* ist eine Funktion, die ein Promise zurückgibt, das einen AJAX-Anfrage ermöglicht

Sehen wir uns an, wie wir einen Github-Nutzer mit Promises zuerst abrufen würden:

```js
function getGithubUser(username) {
  return fetch(`https://api.github.com/users/${username}`).then(response => response.json());
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

Hier ist das äquivalente *async / await*:

```js
async function getGithubUser(username) { // promise + await-Schlüsselwortverwendung erlaubt
  die Antwort = await fetch(`https://api.github.com/users/${username}`); // Die Ausführung stoppt hier, bis das fetch-Promise erfüllt ist
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

Die *async / await*-Syntax ist besonders praktisch, wenn du Promises verketten musst, die voneinander abhängig sind.

Wenn du beispielsweise einen Token abrufen musst, um einen Blogeintrag in einer Datenbank und dann die Autoreninformationen abzurufen:

> **Hinweis :** *await*-Ausdrücke müssen in Klammern eingefasst werden, um Methoden und Eigenschaften des aufgelösten Werts auf derselben Zeile aufzurufen.

```js
async function fetchPostById(postId) {
  const token = (await fetch('token_url')).json().token;
  const post = (await fetch(`/posts/${postId}?token=${token}`)).json();
  der Autor = (await fetch(`/users/${post.authorId}`)).json();

  post.author = author;
  return post;
}

fetchPostById('gzIrzeo64')
  .then(post => console.log(post))
  .catch(err => console.log(err));
```

##### Fehlerbehandlung

Sofern wir *try / catch*-Blöcke nicht um *await*-Ausdrücke herum hinzufügen, werden unerfasste Ausnahmen – unabhängig davon, ob sie im Körper Ihrer *async*-Funktion oder während ihrer Unterbrechung während *await* geworfen wurden – das Promise, das von der *async*-Funktion zurückgegeben wird, ablehnen. Die Verwendung des `throw`-Statements in einer asynchronen Funktion ist dasselbe wie die Rückgabe eines Promises, das abgelehnt wird. [(Ref: PonyFoo)](https://ponyfoo.com/articles/understanding-javascript-async-await#error-handling).

> **Hinweis :** Promises verhalten sich gleich!

Mit Promises sieht die Fehlerbearbeitungskette so aus:

```js
function getUser() { // Dieses Promise wird abgelehnt!
  return new Promise((res, rej) => rej("Benutzer nicht gefunden!"));
}

function getAvatarByUsername(userId) {
  return getUser(userId).then(user => user.avatar);
}

function getUserAvatar(username) {
  return getAvatarByUsername(username).then(avatar => ({ username, avatar }));
}

getUserAvatar('mbeaudru')
  .then(res => console.log(res))
  .catch(err => console.log(err)); // "Benutzer nicht gefunden!"
```

Das Äquivalent mit *async / await*:

```js
async function getUser() { // Das zurückgegebene Promise wird abgelehnt sein!
  wirf "Benutzer nicht gefunden!";
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
  .catch(err => console.log(err)); // "Benutzer nicht gefunden!"
```

#### Externe Ressourcen

- [Async/Await - JavaScript.Info](https://javascript.info/async-await)
- [ES7 Async/Await](http://rossboucher.com/await/#/)
- [6 Gründe, warum JavaScripts Async/Await Promises wegblasen](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9)
- [JavaScript awaits](https://dev.to/kayis/javascript-awaits)
- [Verwendung von Async Await in Express mit Node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)
- [Async-Funktion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
- [Verwendung von async / await in express mit node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)


### Truthy / Falsy

In JavaScript ist ein Truthy- oder Falsy-Wert ein Wert, der in einen Boolean umgewandelt wird, wenn er in einem booleschen Kontext ausgewertet wird. Ein Beispiel für einen booleschen Kontext wäre die Auswertung einer ```if```-Bedingung:

Jeder Wert wird zu ```true``` umgewandelt, es sei denn, sie sind gleich:

- ```false```
- ```0```
- ```""``` (leerer String)
- ```null```
- ```undefined```
- ```NaN```

Hier sind Beispiele für *booleschen Kontext*:

- Auswertung einer ```if```-Bedingung

```js
if (myVar) {}
```

```myVar``` kann ein [first-class citizen](https://en.wikipedia.org/wiki/First-class_citizen) (Variable, Funktion, Boolean) sein, aber es wird in einen Boolean umgewandelt, weil es in einem booleschen Kontext ausgewertet wird.

- Nach dem logischen **NICHT** ```!```-Operator

Dieser Operator gibt false zurück, wenn sein einzelner Operand in true umgewandelt werden kann; andernfalls gibt er true zurück.

```js
!0 // true -- 0 ist falsy, also gibt es true zurück
!!0 // false -- 0 ist falsy, also gibt !0 true zurück, daher liefert !(!0) false
!!"" // false -- leerer String ist falsy, also NICHT (NICHT false) ist gleich false
```

- Mit dem *Boolean*-Objektkonstruktor

```js
new Boolean(0) // false
new Boolean(1) // true
```

- In einer ternären Auswertung

```js
myVar ? "truthy" : "falsy"
```

myVar wird in einem booleschen Kontext ausgewertet.

Sei vorsichtig beim Vergleichen von 2 Werten. Die Objektwerte (die zu true umgewandelt werden sollten) werden **nicht** in einen Boolean umgewandelt, sondern es wird gezwungen, in einen primitiven Wert mithilfe der [ToPrimitives-Spezifikation](http://javascript.info/object-toprimitive) umgewandelt. Intern, wenn ein Objekt mit einem Boolean-Wert wie `[] == true` verglichen wird, macht es `[].toString() == true`, also...

```js
let a = [] == true // a ist false, da [].toString() "" zurückgibt.
let b = [1] == true // b ist true, da [1].toString() "1" zurückgibt.
let c = [2] == true // c ist false, da [2].toString() "2" zurückgibt.
```

#### Externe Ressourcen

- [Truthy (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
- [Falsy (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
- [Truthy und Falsy-Werte in JS - Josh Clanton](http://adripofjavascript.com/blog/drips/truthy-and-falsy-values-in-javascript.html)

### Anamorphismen und Katamorphismen

#### Anamorphismen

Anamorphismen sind Funktionen, die von einem Objekt auf eine komplexere Struktur abbilden, die den Typ des Objekts enthält. Es ist der Prozess des *Entfaltens* einer einfachen Struktur in eine komplexere. Betrachte das Entfalten einer Ganzzahl in eine Liste von Ganzzahlen. Die Ganzzahl ist unser Ausgangsobjekt und die Liste von Ganzzahlen ist die komplexere Struktur.

**Beispielcode**

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

#### Katamorphismen

Katamorphismen sind das Gegenteil von Anamorphismen, da sie Objekte einer komplexeren Struktur nehmen und sie in einfachere Strukturen *falten*. Nehme das folgende Beispiel `product`, welches eine Liste von Ganzzahlen nimmt und eine einzelne Ganzzahl zurückgibt.

**Beispielcode**

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

#### Externe Ressourcen

* [Anamorphisms in JavaScript](http://raganwald.com/2016/11/30/anamorphisms-in-javascript.html)
* [Anamorphism](https://en.wikipedia.org/wiki/Anamorphism)
* [Catamorphism](https://en.wikipedia.org/wiki/Catamorphism)

### Generatoren

Eine andere Möglichkeit, die Funktion `downToOne` zu schreiben, ist die Verwendung eines Generators. Um ein `Generator`-Objekt zu instanziieren, muss man die `function *`-Deklaration verwenden. Generatoren sind Funktionen, die verlassen und später mit gespeichertem Kontext (Variablenbindungen) wieder betreten werden können.

Zum Beispiel kann die oben genannte Funktion `downToOne` wie folgt umgeschrieben werden:

```js
function * downToOne(n) {
  for (let i = n; i > 0; --i) {
    yield i;
  }
}

[...downToOne(5)] // [ 5, 4, 3, 2, 1 ]
```

Generatoren geben ein iterierbares Objekt zurück. Wenn die `next()`-Funktion des Iterators aufgerufen wird, wird sie ausgeführt, bis zum ersten `yield`-Ausdruck, welcher den zurückzugebenden Wert vom Iterator angibt oder mit `yield*`, das an eine andere Generatorfunktion delegiert. Wenn in dem Generator eine `return`-Anweisung aufgerufen wird, wird der Generator als beendet markiert und gibt den Rückgabewert zurück. Weitere Aufrufe von `next()` geben keine neuen Werte zurück.

**Beispielcode**

```js
// Yield-Beispiel
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

Der `yield*`-Ausdruck ermöglicht einem Generator, eine andere Generatorfunktion während der Iteration aufzurufen.

```js
// Yield * Beispiel
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
// Generator Return-Beispiel
function* yieldAndReturn() {
  yield "Y";
  return "R";
  yield "unerreichbar";
}

var gen = yieldAndReturn()
gen.next(); // { value: "Y", done: false }
gen.next(); // { value: "R", done: true }
gen.next(); // { value: undefined, done: true }
```

#### Externe Ressourcen

* [Mozilla MDN Web Docs, Iteratoren und Generatoren](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Generators)

### Statische Methoden

#### Kurze Erklärung

Das Schlüsselwort `static` wird in Klassen verwendet, um statische Methoden zu deklarieren. Statische Methoden sind Funktionen in einer Klasse, die zum Klassenobjekt gehören und nicht für irgendeine Instanz dieser Klasse verfügbar sind.

#### Beispielcode

```js
class Repo {
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }
}

// Beachte, dass wir keine Instanz der Repo-Klasse erstellen mussten
console.log(Repo.getName()) // Der Name des Repos ist modern-js-cheatsheet

let r = new Repo();
console.log(r.getName()) // Ungefangener TypeError: r.getName ist keine Funktion
```

#### Ausführliche Erklärung

Statische Methoden können innerhalb einer anderen statischen Methode mithilfe des Schlüsselworts `this` aufgerufen werden, dies funktioniert jedoch nicht für nicht-statische Methoden. Nicht-statische Methoden können nicht direkt auf statische Methoden mit dem Schlüsselwort `this` zugreifen.

##### Andere statische Methoden aus einer statischen Methode aufrufen.

Um eine statische Methode aus einer anderen statischen Methode aufzurufen, kann das Schlüsselwort `this` verwendet werden wie folgt;

```js
class Repo {
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  static modifyName() {
    return this.getName() + '-added-this'
  }
}

console.log(Repo.modifyName()) // Der Name des Repos ist modern-js-cheatsheet-added-this
```

##### Statische Methoden aus nicht-statischen Methoden aufrufen.

Nicht-statische Methoden können auf zwei Weisen statische Methoden aufrufen;
1. ###### Mit dem Klassennamen.

Um Zugriff auf eine statische Methode von einer nicht-statischen Methode zu bekommen, verwenden wir den Klassennamen und rufen die statische Methode wie eine Eigenschaft auf. z.B `ClassName.StaticMethodName`

```js
class Repo {
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName() {
    return Repo.getName() + ' and it contains some really important stuff'
  }
}

// Wir müssen die Klasse instanziieren, um nicht-statische Methoden zu verwenden
let r = new Repo()
console.log(r.useName()) // Der Name des Repos ist modern-js-cheatsheet und enthält einige wirklich wichtige Dinge
```

2. ###### Mit dem Konstruktor

Statische Methoden können als Eigenschaften des Konstruktorobjekts aufgerufen werden.

```js
class Repo {
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName() {
    // Ruft die statische Methode als Eigenschaft des Konstruktors auf
    return this.constructor.getName() + ' and it contains some really important stuff'
  }
}

// Wir müssen die Klasse instanziieren, um nicht-statische Methoden zu verwenden
let r = new Repo()
console.log(r.useName()) // Der Name des Repos ist modern-js-cheatsheet und enthält einige wirklich wichtige Dinge
```

#### Externe Ressourcen
- [static keyword- MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static)
- [Statische Methoden- Javascript.info](https://javascript.info/class#static-methods)
- [Statische Mitglieder in ES6- OdeToCode](http://odetocode.com/blogs/scott/archive/2015/02/02/static-members-in-es6.aspx)

## Glossar

### <a name="scope_def"></a> Scope

Der Kontext, in dem Werte und Ausdrücke "sichtbar" sind oder referenziert werden können. Wenn eine Variable oder ein anderer Ausdruck "nicht im aktuellen Scope" ist, dann ist er nicht zur Verwendung verfügbar.

Quelle: [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

### <a name="mutation_def"></a> Variablenmutation

Von einer Variablen wird gesagt, dass sie mutiert wurde, wenn ihr anfänglicher Wert sich danach geändert hat.

```js
var myArray = [];
myArray.push("firstEl") // myArray wird mutiert
```

Eine Variable wird als *unveränderlich* bezeichnet, wenn sie nicht mutiert werden kann.

[Schau dir den MDN Mutable-Artikel an](https://developer.mozilla.org/en-US/docs/Glossary/Mutable) für weitere Details.
