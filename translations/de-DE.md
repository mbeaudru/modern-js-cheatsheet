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
    + [Pfeilfunktion](#pfeilfunktion)
      - [Beispielcode](#beispielcode-1)
      - [Ausführliche Erklärung](#ausführliche-erklärung-1)
        * [Prägnanz](#prägnanz)
        * [*this* Referenz](#this-referenz)
      - [Nützliche Ressourcen](#nützliche-ressourcen)
    + [Standardparameterwert für Funktionen](#standardparameterwert-für-funktionen)
      - [Externe Ressource](#externe-ressource-1)
    + [Destructuring von Objekten und Arrays](#destructuring-von-objekten-und-arrays)
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
        * [Objekteigenschaften verbreiten](#objekteigenschaften-verbreiten)
      - [Externe Ressourcen](#externe-ressourcen)
    + [Eigenschaftskurzschrift in Objekten](#eigenschaftskurzschrift-in-objekten)
      - [Erklärung](#erklärung-2)
      - [Externe Ressourcen](#externe-ressourcen-1)
    + [Promises](#promises)
      - [Beispielcode](#beispielcode-4)
      - [Erklärung](#erklärung-3)
        * [Das Promise erstellen](#das-promise-erstellen)
        * [Verwendung von Promise-Handlern](#verwendung-von-promise-handlern)
      - [Externe Ressourcen](#externe-ressourcen-2)
    + [Template literals](#template-literals)
      - [Beispielcode](#beispielcode-5)
      - [Externe Ressourcen](#externe-ressourcen-3)
    + [Tagged Template Literals](#tagged-template-literals)
      - [Externe Ressourcen](#externe-ressourcen-4)
    + [Importe / Exporte](#importe--exporte)
      - [Erklärung mit Beispielcode](#erklärung-mit-beispielcode-1)
        * [Benannte Exporte](#benannte-exporte)
        * [Standardimport / -export](#standardimport--export)
      - [Externe Ressourcen](#externe-ressourcen-5)
    + [JavaScript *this*](#javascript-this)
      - [Externe Ressourcen](#externe-ressourcen-6)
    + [Klasse](#klasse)
      - [Beispiele](#beispiele)
      - [Externe Ressourcen](#externe-ressourcen-7)
    + [Extends und super Schlüsselwörter](#extends-und-super-schlüsselwörter)
      - [Beispielcode](#beispielcode-6)
      - [Externe Ressourcen](#externe-ressourcen-8)
    + [Async Await](#async-await)
      - [Beispielcode](#beispielcode-7)
      - [Erklärung mit Beispielcode](#erklärung-mit-beispielcode-2)
      - [Fehlerbehandlung](#fehlerbehandlung)
      - [Externe Ressourcen](#externe-ressourcen-9)
    + [Truthy / Falsy](#truthy--falsy)
      - [Externe Ressourcen](#externe-ressourcen-10)
    + [Anamorphisms / Catamorphisms](#anamorphisms-und-catamorphisms)
      - [Anamorphisms](#anamorphisms)
      - [Catamorphisms](#catamorphisms)
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
    + [Scope](#scope)
    + [Variablenmutation](#variablenmutation)

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

#### Detaillierte Erklärung

##### Kürze

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
