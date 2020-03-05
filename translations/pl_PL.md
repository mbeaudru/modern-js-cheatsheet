# <a name="modern-javascript-cheatsheet"></a>Współczesny JavaScript - ściągawka

![Modern JavaScript cheatsheet](https://i.imgur.com/aexPxMb.png)
<small>Image Credits: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</small>

## <a name="introduction"></a>Wstęp

### <a name="motivation"></a>Motywacja

W tym dokumencie zebrane zostały elementy języka JavaScript, z którymi często można się spotkać we współczesnych projektach i najnowszych przykładach kodu.

Celem tego przewodnika nie jest nauka JavaScriptu od zera, ale pomoc posiadającym podstawową wiedzę developerom, którzy pracując ze współczesnymi bazami kodu (powiedzmy, ucząc się React) napotykają trudności, wynikające z użytych tam konceptów języka JavaScript.

Prócz tego, od czasu do czasu będę zamieszczał własne porady, z którymi niekoniecznie trzeba się zgadzać, ale postaram się za każdym razem podkreślać, że chodzi tylko o moja opinię.

> **Uwaga:** Większość omawianych tu pojęć pochodzi z nowej wersji języka JavaScript (ES2015, często nazywanego ES6). Bardzo dobre omówienie nowych możliwości wprowadzonych w tej wersji można znaleźć [tutaj](http://es6-features.org).

### <a name="complementary-resources"></a>Materiały uzupełniające

Jeśli masz problem ze zrozumieniem jakiegoś pojęcia, proponuję poszukać odpowiedzi w poniższych źródłach:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/search?q=)
- [You don't know JS (book)](https://github.com/getify/You-Dont-Know-JS)
- [ES6 Features with examples](http://es6-features.org)
- [WesBos blog (ES6)](http://wesbos.com/category/es6/)
- [Javascript Basics for Beginners](https://www.udacity.com/course/javascript-basics--ud804) - bezpłatny kurs od Udacity
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) - dla znalezienia specjalistycznych blogów i innych źródeł
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)

## <a name="table-of-contents"></a>Spis treści

- [Współczesny JavaScript - ściągawka](#modern-javascript-cheatsheet)
  * [Wstęp](#introduction)
    + [Motywacja](#motivation)
    + [Materiały uzupełniające](#complementary-resources)
  * [Spis treści](#table-of-contents)
  * [Pojęcia](#notions)
    + [Deklaracja zmiennych: var, const, let](#variable-declaration-var-const-let)
      - [Krótkie wyjaśnienie](#short-explanation)
      - [Przykładowy kod](#sample-code)
      - [Szczegółowe wyjaśnienie](#detailed-explanation)
      - [Dodatkowe źródła](#external-resource)
    + [Funkcje strzałkowe (arrow functions)](#-arrow-function)
      - [Przykładowy kod](#sample-code-1)
      - [Szczegółowe wyjaśnienie](#detailed-explanation-1)
        * [Zwięzłość](#concision)
        * [Użycie *this*](#this-reference)
      - [Pomocne źródła](#useful-resources)
    + [Domyślna wartość argumentów funkcji](#function-default-parameter-value)
      - [Dodatkowe źródła](#external-resource-1)
    + [Destrukturyzacja obiektów i tablic](#destructuring-objects-and-arrays)
      - [Wyjaśnienie z przykładowym kodem](#explanation-with-sample-code)
      - [Pomocne źródła](#useful-resources-1)
    + [Metody tablicowe - map / filter / reduce](#array-methods---map--filter--reduce)
      - [Przykładowy kod](#sample-code-2)
      - [Wyjaśnienie](#explanation)
        * [Array.prototype.map()](#arrayprototypemap)
        * [Array.prototype.filter()](#arrayprototypefilter)
        * [Array.prototype.reduce()](#arrayprototypereduce)
      - [Dodatkowe źródła](#external-resource-2)
    + [Operator rozwijania "..."](#spread-operator-)
      - [Przykładowy kod](#sample-code-3)
      - [Wyjaśnienie](#explanation-1)
        * [W obiektach iterowalnych (np. w tablicach)](#in-iterables-like-arrays)
        * [Parametry rest](#function-rest-parameter)
        * [Rozwijanie własności obiektów](#object-properties-spreading)
      - [Dodatkowe źródła](#external-resources)
    + [Skrócony zapis własności obiektów](#object-property-shorthand)
      - [Wyjaśnienie](#explanation-2)
      - [Dodatkowe źródła](#external-resources-1)
    + [Obietnice (promises)](#promises)
      - [Przykładowy kod](#sample-code-4)
      - [Wyjaśnienie](#explanation-3)
        * [Tworzenie obietnicy (promise)](#create-the-promise)
        * [Użycie procedur obsługi](#promise-handlers-usage)
      - [Dodatkowe źródła](#external-resources-2)
    + [Łańcuchy szablonowe (template literals)](#template-literals)
      - [Przykładowy kod](#sample-code-5)
      - [Dodatkowe źródła](#external-resources-3)
    + [Oznaczone łańcuchy szablonowe (tagged template literals)](#tagged-template-literals)
      - [Dodatkowe źródła](#external-resources-4)
    + [Importy / eksporty](#imports--exports)
      - [Wyjaśnienie z przykładowym kodem](#explanation-with-sample-code-1)
        * [Nazwane eksporty (named exports)](#named-exports)
        * [Domyślny import / eksport](#default-import--export)
      - [Dodatkowe źródła](#external-resources-5)
    + [*this* w JavaScript](#-javascript-this)
      - [Dodatkowe źródła](#external-resources-6)
    + [Klasa](#class)`
      - [Przykłady](#samples)
      - [Dodatkowe źródła](#external-resources-7)
    + [Słowa kluczowe extends i super](#extends-and-super-keywords)
      - [Przykładowy kod](#sample-code-6)
      - [Dodatkowe źródła](#external-resources-8)
    + [Składnia async/await](#async-await)
      - [Przykładowy kod](#sample-code-7)
      - [Wyjaśnienie z przykładowym kodem](#explanation-with-sample-code-2)
      - [Obsługa błędów](#error-handling)
      - [Dodatkowe źródła](#external-resources-9)
    + [Prawda / Fałsz](#truthy--falsy)
      - [Dodatkowe źródła](#external-resources-10)
    + [Anamorfizmy i Katamorfizmy](#anamorphisms-and-catamorphisms)
      - [Anamorfizmy](#anamorphisms)
      - [Katamorfizmy](#catamorphisms)
      - [Dodatkowe źródła](#external-resources-11)
    + [Generatory](#generators)
      - [Dodatkowe źródła](#external-resources-12)
    + [Metody statyczne](#static-methods)
      - [Krótkie wyjaśnienie](#short-explanation-1)
      - [Przykładowy kod](#sample-code-8)
      - [Szczegółowe wyjaśnienie](#detailed-explanation-2)
        * [Wzywanie innych metod statycznych z metody statycznej](#calling-other-static-methods-from-a-static-method)
        * [Wzywanie metod statycznych z metod niestatycznych](#calling-static-methods-from-non-static-methods)
      - [Dodatkowe źródła](#external-resources-13)
  * [Słowniczek](#glossary)
    + [Zakres widoczności (scope)](#-scope)
    + [Przekształcenie zmiennej (variable mutation)](#-variable-mutation)

## <a name="notions"></a>Pojęcia

### <a name="variable-declaration-var-const-let"></a>Deklaracja zmiennych: var, const, let
 
W języku JavaScript mamy do dyspozycji trzy słowa kluczowe, za pomocą których deklarowane są zmienne. Są to ```var```, ```let``` and ```const```.

#### <a name="short-explanation"></a>Krótkie wyjaśnienie

Zmienne deklarowane z użyciem ```const``` nie moga być ponownie przypisane, natomiast ```let``` i ```var``` mogą.

Radziłbym zawsze deklarować zmienne za pomocą ```const```, a ```let``` stosować, kiedy zamierzamy *przekształcać* zmienne bądź przypisywać im inną wartość.

<table>
  <tr>
    <th></th>
    <th>Zakres widoczności</th>
    <th>Można nadpisać</th>
    <th>Można zmienić</th>
   <th><a href="#tdz_sample">Czasowo martwa strefa</a></th>
  </tr>
  <tr>
    <th>const</th>
    <td>Blok</td>
    <td>Nie</td>
    <td><a href="#const_mutable_sample">Tak</a></td>
    <td>Tak</td>
  </tr>
  <tr>
    <th>let</th>
    <td>Blok</td>
    <td>Tak</td>
    <td>Tak</td>
    <td>Tak</td>
  </tr>
   <tr>
    <th>var</th>
    <td>Funkcja</td>
    <td>Tak</td>
    <td>Tak</td>
    <td>Nie</td>
  </tr>
</table>

#### <a name="sample-code"></a>Przykładowy kod

```javascript
const person = "Nick";
person = "John" // Wywoła błąd, person nie może być przepisane
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", przepisanie jest dozwolone z let
```

#### <a name="detailed-explanation"></a>Szczegółowe wyjaśnienie

[*Zakres widoczności*] zmiennej oznacza mniej więcej "to, gdzie zmienna jest dostępna w kodzie". 

##### var

Zakresem widoczności zmiennych deklarowanych za pomocą ```var``` jest funkcja. Oznacza to, że jeśli zmienna była stworzona wewnątrz funkcji, to wszystko w ciele tej funkcji ma dostęp do danej zmiennej. Poza tym, zmienna o opisanym zakresie nie jest dostępna poza funkcją.

Można myśleć o tym następująco: jeśli zakres widoczności zmiennej to *X*, to zmienna ta stanowi jak gdyby własność X.

```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - myVar dostępna wewnątrz funkcji.
}
console.log(myVar); // ReferenceError, myVar nie jest dostępna poza funkcją.
```

A oto mniej oczywisty przykład:

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // ponieważ zakresem myVar jest funkcja, zastępujemy wcześniejszą wartość "Nick" wartością "John"
  }
  console.log(myVar); // "John" - zwróć uwagę, jak instrukcje w bloku if wpłynęły na wartość
}
console.log(myVar); // ReferenceError, myVar nie jest dostępna poza funkcją.
```

Poza tym, zmienne zadeklarowane poprzez *var* przy wykonaniu kodu przemieszczają się na początek zakresu widoczności. Proces ten nazywamy [var hoisting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting).

Ten fragment kodu:

```js
console.log(myVar) // undefined -- brak błędu
var myVar = 2;
```

w momencie wykonania rozumiany jest tak:

```js
var myVar;
console.log(myVar) // undefined -- brak błędu
myVar = 2;
```

##### let

```var``` i ```let ``` znaczą mniej więcej to samo, ale w przypadku zmiennych zadeklarowanych za pomocą ```let``` 

- zakres widoczności stanowi blok
- są **niedostępne** przed przypisaniem
- nie mogą być ponownie zadeklarowane w tym samym zakresie widoczności

Przyjrzyjmy się blokowemu zakresu widoczności, używając poprzedniego przykładu:

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // ponieważ zakresem widoczności myVar jest blok, 
    // właśnie stworzyliśmy nową zmienną myVar.
    // zmienna ta jest niedostępna poza blokiem i zupełnie 
    // niezależna od pierwszej zmiennej myVar.
  }
  console.log(myVar); // "Nick", instrukcje bloku if NIE wpłynęły na tę zmienną
}
console.log(myVar); //  ReferenceError, myVar nie jest dostępna poza funkcją.
```

<a name="tdz_sample"></a> A teraz rozpatrzmy, co oznacza, że zmienne zadeklarowane z *let* (i *const*) są niedostępne przed przypisaniem:

```js
console.log(myVar) // wywołuje ReferenceError !
let myVar = 2;
```

W odróżnieniu od zmiennych zadeklarowanych poprzez *var*, próba odczytu bądź nadpisania zmiennej stworzonej za pomocą *let* lub *const* przed przypisaniem wywoła błąd. Zjawisko to nazywane jest często [*Czasowo martwą strefą*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_Dead_Zone_and_errors_with_let) albo *TDZ*

> **Uwaga:** Ściśle rzecz biorąc zmienne zadeklarowane przy pomocy *let* i *const* też są windowane, ale nie przypisywane. Ponieważ nie mogą one być użyte przed przypisaniem, może się wydawać, że nie dochodzi do windowania (hoistingu), co nie jest prawdą. Jeśli chcesz dowiedzieć się więcej, możesz zapoznać się z [dokładnym omówieniem tego zjawiska](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified).

Ponadto nie można ponownie zadeklarować zmiennej stworzonej z *let*

```js
let myVar = 2;
let myVar = 3; // SyntaxError
```

##### const

Zmienne zadeklarowane poprzez słowo kluczowe ```const``` zachowują się, jak te zadeklarowane z *let*, ale nie mogą być ponownie przypisane.

Podsumowując, zmienne stworzone z *const*:

- ich zakresem widoczności jest blok
- nie są dostępne przed przypisaniem
- nie mogą być ponownie zadeklarowane w tym samym zakresie widoczności
- nie mogą być ponownie przypisane

```js
const myVar = "Nick";
myVar = "John" // wywołuje błąd, ponowne przypisanie jest niedozwolone
```

```js
const myVar = "Nick";
const myVar = "John" // wywołuje błąd, ponowna deklaracja jest niedozwolone
```

<a name="const_mutable_sample"></a> Jest jednak pewien szczegół : zmienne zadeklarowane z ```const``` nie są [**niezmienne**](#mutation_def) ! Konkretnie, oznacza to, że *objekty* i *tablice* zadeklarowane poprzez ```const``` **mogą** podlegać modyfikacjom.

W przypadku obiektów:
```js
const person = {
  name: 'Nick'
};
person.name = 'John' // działa! Zmienna person nie jest ponownie przypisywana, ale ulega zmianie.
console.log(person.name) // "John"
person = "Sandra" // wywoła błąd, ponieważ nie można nadpisywać zmiennych deklarowanych poprzez const
```

W przypadku tablic:
```js
const person = [];
person.push('John'); // działa! Zmienna person nie jest ponownie przypisywana, ale ulega zmianie.
console.log(person[0]) // "John"
person = ["Nick"] // wywoła błąd, ponieważ nie można nadpisywać zmiennych deklarowanych poprzez const
```

#### <a name="external-resource"></a>Dodatkowe źródła

- [How let and const are scoped in JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Temporal Dead Zone (TDZ) Demystified](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="-arrow_func"></a> Funkcje strzałkowe (arrow functions)

W wersji ES6 JavaScript wprowadzone zostały *funkcje strzałkowe* (*arrow functions*) - nowy sposób zapisu funkcji. Oto niektóre jego zalety:

- większa zwięzłość
- *this* pobierane jest z otaczającego kontekstu
- niejawny zwrot (implicit return)

#### <a name="sample-code-1"></a>Przykładowy kod

- Zwięzłość i niejawny zwrot

```js
function double(x) { return x * 2; } // Tradycyjny sposób
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // Ta sama funkcja jako funkcja strzałkowa z niejawnym zwrotem
console.log(double(2)) // 4
```

- Użycie *this*

W funkcji strzałkowej *this* jest równe wartości *this* w otaczającym zakresie widoczności. Zasadniczo, dzięki funkcjom strzałkowym, nie ma już potrzeby używania tricku "that = this" przed wywołaniem funkcji wewnątrz funkcji.

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### <a name="detailed-explanation-1"></a>Szczegółowe wyjaśnienie

##### <a name="concision"></a>Zwięzłość

Funkcje strzałkowe są w wielu aspektach bardziej zwięzłe niż tradycyjne funkcje. Rozpatrzmy kilka przypadków:

- Jawny vs niejawny zwrot

**Jawny zwrot** (**explicit return**) to funkcja, w której ciele użyte jest słowo kluczowe *return*. 

```js
  function double(x) {
    return x * 2; // this function explicitly returns x * 2, *return* keyword is used
  }
```

Przy tradycyjnym sposobie pisania funkcji zwrot był zawsze jawny. Jednak arrow functions pozwalają na *niejawny zwrot*, czyli taki, w którym słowo kluczowe *return* nie jest konieczne przy zwrocie wartości.

```js
  const double = (x) => {
    return x * 2; // Jawny zwrot
  }
```

Ponieważ funkcja ta ogranicza się do zwrotu pewnej wartości (poza tym brak innych instrukcji), możemy użyć niejawnego zwrotu.

```js
  const double = (x) => x * 2; // Correct, returns x*2
```

By to zrobić, musimy ***usunąć nawiasy* i słowo **return**. Stąd też nazwa *niejawny* (implicit) zwrot - mimo braku słowa kluczowego **return**, funkcja i tak zwróci ```x * 2```.

> **Uwaga:** Jeśli funkcja nie zwraca żadnej wartości (z *efektami ubocznymi*), nie ma w niej ani jawnego ani niejawnego zwrotu.

Poza tym, jeśli chcemy niejawnie zwrócić *obiekt*, należy **otoczyć go okrągłymi nawiasami**, by nie dopuścić do konfliktu z nawiasami samego bloku.

```js
const getPerson = () => ({ name: "Nick", age: 24 })
console.log(getPerson()) // { name: "Nick", age: 24 } -- obiekt niejawnie zwracany przez arrow function
```

- Tylko jeden argument

Jeśli funkcja posiada tylko jeden argument, możemy ominąć nawiasy wokół niego. Przyjrzyjmy się ponownie funkcji *double* z poprzedniego kodu:

```js
  const double = (x) => x * 2; // arrow function ma jeden argument
```

Nawiasy wokół argumentu można usunąć:

```js
  const double = x => x * 2; // arrow function ma jeden argument
```

- Brak argumentów

Gdy funkcja nie ma argumentu, należy użyć okrągłych nawiasów, jeśli chcemy zachować poprawną składnię.

```js
  () => { // są nawiasy, wszystko w porządku
    const x = 2;
    return x;
  }
```

```js
  => { // brak nawiasów, kod nie będzie działać!
    const x = 2;
    return x;
  }
```

##### <a name="this-reference"></a>Użycie *this*

Aby w pełni zrozumieć działanie funkcji strzałkowych, trzeba wiedzieć, jak w JavaScript zachowuje się [this](#this_def).

W funckji strzałkowej *this* jest równe wartości *this* w otaczającym kontekście. Oznacza to, że funkcja strzałkowa nie tworzy nowego *this*, ale zamiast tego pobiera je z otoczenia.

Bez funkcji strzałkowej, jeśli chcemy otrzymać dostęp do zmiennej przez *this* w funkcji znajdującej się w innej funkcji musimy użyć tricku *that = this* lub *self = this*.

Na przykład, używając funkcji setTimeout w myFunc:

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // that = this trick
  setTimeout(
    function() { // Nowy *this* tworzony w tym zakresie widoczności
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // undefined -- zobacz: deklaracja funkcji wyżej
    },
    0
  );
}
```

Ale w przypadku funkcji strzałkowej, *this* pobierane jest z otoczenia:

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => { // this pobierane z otoczenia. W tym przypadku - z myFunc.
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

#### <a name="useful-resources"></a>Pomocne źródła

- [Arrow functions introduction - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript arrow function - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

### <a name="function-default-parameter-value"></a>Domyślna wartość argumentów funkcji

Począwszy od wersji ES2015, możliwe jest ustawienie domyślnej wartości argumentów funkcji przy użyciu następującej składni: 

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- żadna wartość nie jest podana, x otrzymuje wartość domyślną, czyli 10
console.log(myFunc(5)) // 5 -- wartość podana, więc x otrzymuje wartość 5

console.log(myFunc(undefined)) // 10 -- podana wartość undefined, więc x otrzymuje wartość domyślną, czyli 10
console.log(myFunc(null)) // null -- wartość (null) jest podana, zobacz: niżej.
```

Domyślny argument będzie użyty jedynie w dwóch sytuacjach:

- żaden argument nie jest podany
- jako argument podano *undefined*

Innymi słowami, jeśli jako argument podamy *null*, wartość domyślna **nie zostanie użyta**.

> **Note:** Przypisanie wartości domyślnej można zastować także z destrukturyzowanymi parametrami (patrz: następna sekcja)

#### <a name="external-resource-1"></a>Dodatkowe źródła

- [Default parameter value - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Default parameters - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

### <a name="destructuring-objects-and-arrays"></a>Destrukturyzacja obiektów i tablic

*Destrukturyzacja* to wygodny sposób tworzenia nowych zmiennych poprzez wydobycie pewnych wartości z danych przechowywanych w obiektach i tablicach.

*Destrukturyzacja* może być użyta do przypisania zmiennym rozbitych na części parametrów funkcji lub *this.props* w projektach React.

#### <a name="explanation-with-sample-code"></a>Wyjaśnienie z przykładowym kodem

- Obiekt

We wszystkich przykładach używać będziemy następującego obiektu:

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

Bez destrukturyzacji:

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

Z destrukturyzacją, wszystko w jednej linijce:

```js
const { firstName: first, age, city = "Paris" } = person; // Gotowe !

console.log(age) // 35 -- Stworzono nową zmienną równą person.age
console.log(first) // "Nick" -- Stworzono nową zmienną równą person.firstName
console.log(firstName) // ReferenceError -- person.firstName istnieje, ale nowo stworzona zmienna nazywa się first
console.log(city) // "Paris" -- Stworzono nową zmienną city i, ponieważ person.city jest równe undefined, zmienna jest równa domyślnej wartość "Paris".
```

**Uwaga:** W ```const { age } = person;``` nawiasy po słowie *const* nie są użyte do deklaracji obiektu ani jako blok, ale jako składnia *destrukturyzacji*.

- Argumenty funkcji

*Destrukturyzacja* jest często używana do rozbicia parametrów funkcji na części.

Bez destrukturyzacji:

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

Jeśli destrukturyzujemy parametr *person*, otrzymujemy znacznie bardziej zwięzłą funkcję:

```js
function joinFirstLastName({ firstName, lastName }) { // tworzymy zmienne firstName i lastName z części argumentu person.
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

Destrukturyzacja jest jeszcze przyjemniejsza, gdy użyjemy [funkcji strzałkowych](#arrow_func_concept):

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```

- Tablica

Rozpatrzmy następującą tablicę:

```js
const myArray = ["a", "b", "c"];
```

Bez destrukturyzacji

```js
const x = myArray[0];
const y = myArray[1];
```

Z destrukturyzacją

```js
const [x, y] = myArray; // Gotowe !

console.log(x) // "a"
console.log(y) // "b"
```

#### <a name="useful-resources-1"></a>Pomocne źródła

- [ES6 Features - Destructuring Assignment](http://es6-features.org/#ArrayMatching)
- [Destructuring Objects - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destructuring](http://exploringjs.com/es6/ch_destructuring.html)

### <a name="array-methods---map--filter--reduce"></a>Metody tablicowe - map / filter / reduce

*Map*, *filter* i *reduce* to metody tablicowe zapożyczone z paradygmatu [*programowania funkcyjnego*](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0).

Opiszmy je krótko:

- **Array.prototype.map()** przyjmuje jako argument tablicę, modyfikuje jej elementy i zwraca nową tablicę ze zmienionymi elementami.
- **Array.prototype.filter()** przyjmuje jako argument tablicę, decyduje, które elementy zatrzymać a które usunąć. Zwraca tablicę z zachowanymi elementami.
- **Array.prototype.reduce()** przyjmuje jako argument tablicę, wylicza z jej elementów jedną wspólną wartość, którą zwraca.

Polecam używać ich jak najczęściej, zgodnie z zasadami programowania funkcyjnego, ponieważ metody tablicowe są zwięzłe, eleganckie i można je ze sobą łączyć.

Wykorzystując trzy powyższe metody możemy uniknąć użycia pętli *for* i *forEach* w większości sytuacji. Kiedy następnym razem będziesz chciał skorzystać z pętli *for*, spróbuj zamiast niej użyć kompozycji *map*, *filter* i *reduce*. Z początku może to sprawiać problemy, bo wymaga przyzwyczajenia sie do nowego sposobu myślenia, ale jeśli już go przyswoisz, wszystko będzie prostsze.

#### <a name="sample-code-2"></a>Przykładowy kod

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
const doubledNumbers = numbers.map(n => n * 2); // [0, 2, 4, 6, 8, 10, 12]
const evenNumbers = numbers.filter(n => n % 2 === 0); // [0, 2, 4, 6]
const sum = numbers.reduce((prev, next) => prev + next, 0); // 21
```

Obliczmy sumę ocen wszystkich studentów z oceną powyżej 10 łącząc *map*, *filter* i *reduce*:

```js
const students = [
  { name: "Nick", grade: 10 },
  { name: "John", grade: 15 },
  { name: "Julia", grade: 19 },
  { name: "Nathalie", grade: 9 },
];

const aboveTenSum = students
  .map(student => student.grade) // tworzymy tablicę ocen z tablicy studentów za pomocą map 
  .filter(grade => grade >= 10) // filtrujemy tablicę ocen, by pozostawić większe lub równe 10
  .reduce((prev, next) => prev + next, 0); // sumujemy wszystkie oceny powyżej 10

console.log(aboveTenSum) // 44 -- 10 (Nick) + 15 (John) + 19 (Julia), Nathalie poniżej 10 - ignorowana
```

#### <a name="explanation"></a>Wyjaśnienie

W przykładach wykorzystywać będziemy poniższą tablicę:

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
```

##### <a name="arrayprototypemap"></a>Array.prototype.map()

```js
const doubledNumbers = numbers.map(function(n) {
  return n * 2;
});
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

Co tu się dzieje? Używamy *map* na tablicy *numbers*, *map* iteruje przez każdy element i używa go jako argumentu funkcji. Celem funkcji jest przeprowadzenie kalkulacji i zwrot nowej wartości, która zastąpi wartość użytą jako argument.

Wydzielmy funkcję z tablicy, żeby przyjrzeć się jej bliżej:

```js
const doubleN = function(n) { return n * 2; };
const doubledNumbers = numbers.map(doubleN);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

```numbers.map(doubleN)``` tworzy ```[doubleN(0), doubleN(1), doubleN(2), doubleN(3), doubleN(4), doubleN(5), doubleN(6)]```, które są równe ```[0, 2, 4, 6, 8, 10, 12]```.
.
> **Uwaga:** Jeśli nie potrzebujesz zwrotu nowej tablicy i chcesz po prostu użyć pętli posiadającej efekty uboczne, możesz rozważyć użycie pętli for / forEach zamiast map.

##### <a name="arrayprototypefilter"></a>Array.prototype.filter()

```js
const evenNumbers = numbers.filter(function(n) {
  return n % 2 === 0; // true jeśli n jest parzyste, false jeśli nie jest
});
console.log(evenNumbers); // [0, 2, 4, 6]
```

Używamy *filter* na tablicy *numbers*, *filter* iteruje przez każdy element i używa go jako argumentu funkcji. Celem funkcji jest zwrot zmiennej typu boolowskiego, która określi, czy daną wartość należy zachować, czy też nie. Następnie funkcja zwraca tablicę, zawierającą jedynie zachowane wartości.

##### <a name="arrayprototypereduce"></a>Array.prototype.reduce()

Celem metody *reduce* jest wyliczenie na podstawie tablicy pewnej pojedynczej wartości. Jakie wyliczenia przeprowadzi metoda, zależy tylko od ciebie.

```js
const sum = numbers.reduce(
  function(acc, n) {
    return acc + n;
  },
  0 // wartość zmiennej akumulującej po pierwszej iteracji
);

console.log(sum) //21
```

Tak jak metody .map i .filter, .reduce wykorzystuje tablicę i jako pierwszy argument przyjmuje funkcję.

Są jednak pewne różnice:

- .reduce przyjmuje dwa argumenty

Pierwszy argument to funkcja, która będzie stosowana przy każdej iteracji.

Drugi argument to wartość zmiennej akumulującej (w naszym przypadku *acc*) w pierwszej iteracji (by lepiej zrozumieć, czytaj dalej).

- Argumenty funkcji

Funkcja używana jako pierwszy argument .reduce przyjmuje dwa argumenty. Pierwszy (w naszym przypadku *acc*) to zmienna akumulująca, drugi (*n*) - obecny element.

Zmienna akumulująca równa jest wartości zwróconej przez naszą funkcję w **poprzedniej** iteracji. Na początku każdej iteracji *acc* równa jest wartości, która była przekazana jako drugi argument .reduce.

###### W pierwszej iteracji

```acc = 0``` ponieważ jako drugi element *reduce* podaliśmy 0

```n = 0``` pierwszy element tablicy *array*

Funkcja zwraca *acc* + *n* --> 0 + 0 --> 0

###### W drugiej iteracji

```acc = 0``` ponieważ taką wartość funkcja zwróciła przy poprzedniej iteracji

```n = 1``` drugi element tablicy *array*

Funkcja zwraca *acc* + *n* --> 0 + 1 --> 1

###### W trzeciej iteracji

```acc = 1``` ponieważ taką wartość funkcja zwróciła przy poprzedniej iteracji

```n = 2``` trzeci element tablicy *array*

Funkcja zwraca *acc* + *n* --> 1 + 2 --> 3

###### W czwartej iteracji

```acc = 3``` ponieważ taką wartość funkcja zwróciła przy poprzedniej iteracji

```n = 3``` czwarty element tablicy *array*

Funkcja zwraca *acc* + *n* --> 3 + 3 --> 6

###### [...] W ostatniej iteracji

```acc = 15``` ponieważ taką wartość funkcja zwróciła przy poprzedniej iteracji

```n = 6``` ostatni element tablicy *array*

Funkcja zwraca *acc* + *n* --> 15 + 6 --> 21

Ponieważ to ostatnia iteracja, **.reduce** zwraca 21.

#### <a name="external-resource-2"></a>Dodatkowe źródła

- [Understanding map / filter / reduce in JS](https://hackernoon.com/understanding-map-filter-and-reduce-in-javascript-5df1c7eee464)

### <a name="spread-operator-"></a>Operator rozwijania "..."

Operator rozwijania ```...``` został wprowadzony z ES2015 i przeznaczony jest do "rozwijania" elementów obiektów iterowalnych (np. tablic) tam, gdzie można zmieścić kilka elementów

#### <a name="sample-code-3"></a>Przykładowy kod

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

#### <a name="explanation-1"></a>Wyjaśnienie

##### <a name="in-iterables-like-arrays"></a>W obiektach iterowalnych (np. tablicach)

Jeśli mamy dwie następujące tablice:

```js
const arr1 = ["a", "b", "c"];
const arr2 = [arr1, "d", "e", "f"]; // [["a", "b", "c"], "d", "e", "f"]
```

Pierwszy element tablicy *arr2* jest tablicą, ponieważ *arr1* został wprowadzony do *arr2* bezpośrednio. Co jednak, jeśli chcemy, by *arr2* było tablicą liter? Możemy rozwinąć (*spread*) elementy *arr1* w tablicy *arr2*.

Z operatorem rozwijania

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

##### <a name="function-rest-parameter"></a>Parametry rest

Operator rest pozwala przedstawić dowolna liczbę argumentów w postaci tablicy, po elementach której można iterować. Istnieje już obiekt **arguments** związany z każdą funkcją i równy tablicy wszystkich argumentów przekazanych do danej funkcji.


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

Wyobraźmy sobie teraz, że chcemy, żeby nasza funkcja tworzyła nowego ucznia z ocenami i średnią. Czy nie byłoby wygodniej zapisać dwa pierwsze argumenty jako dwie oddzielne zmienne, a wszystkie oceny umieścić w iterowalnej tablicy?

Właśnie na to pozwala nam operator rest!

```js
function createStudent(firstName, lastName, ...grades) {
  // firstName = "Nick"
  // lastName = "Anderson"
  // [10, 12, 6] -- "..." bierze wszystkie pozostałe argumenty przekazane funkcji i tworzy zmienną "grades" z przechowującą je tablicą 

  const avgGrade = grades.reduce((acc, curr) => acc + curr, 0) / grades.length; // oblicza średnią z ocen

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

> **Uwaga:** funkcja createStudent jest zła, bo nie sprawdzamy, czy grades.length istnieje i czy jest różna od zera. Nie ująłem tej sytuacji w kodzie, żeby funkcja była bardziej czytelna.

##### <a name="object-properties-spreading"></a>Rozwijanie własności obiektów

Aby zrozumieć tę część, polecam najpierw przeczytać poprzednie sekcje dotyczące użycia operatora rest na iterowalnych obiektach i parametrach funkcji.

```js
const myObj = { x: 1, y: 2, a: 3, b: 4 };
const { x, y, ...z } = myObj; // destrukturyzacja obiektu
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

// z to reszta destrukturyzowanego obiektu: myObj object minus destrukturyzowane własności x i y

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }

// Własności obiektu z są rozwinięte w n
```

#### <a name="external-resources"></a>Dodatkowe źródła

- [TC39 - Object rest/spread](https://github.com/tc39/proposal-object-rest-spread)
- [Spread operator introduction - WesBos](https://github.com/wesbos/es6-articles/blob/master/28%20-%20Spread%20Operator%20Introduction.md)
- [JavaScript & the spread operator](https://codeburst.io/javascript-the-spread-operator-a867a71668ca)
- [6 Great uses of the spread operator](https://davidwalsh.name/spread-operator)

### <a name="object-property-shorthand"></a>Skrócony zapis własności obiektów

Kiedy przypisujemy zmienną do własności obiektu, jeśli nazwa zmiennej jest taka sama, jak nazwa własności, możemy zrobić coś takiego:

```js
const x = 10;
const myObj = { x };
console.log(myObj.x) // 10
```

#### <a name="explanation-2"></a>Wyjaśnienie

Dotychczas (przed ES2015), kiedy chcieliśmy przy deklaracji nowego literału obiektowego (*object literal*) zastosować zmienne jako jego własności, zapisalibyśmy to w ten sposób:

```js
const x = 10;
const y = 20;

const myObj = {
  x: x, // przypisanie wartości zmiennej x do myObj.x
  y: y // przypisanie wartości zmiennej y do myObj.y
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```

Jak widać, jest to dość powtarzalne, bo nazwy własności myObj są takie same, jak nazwy zmiennych, które chcemy przypisać do tych własności.

Z ES2015, jeśli nazwa zmiennej jest taka sama jak własności, możemy skorzystać ze skróconego zapisu:

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

#### <a name="external-resources-1"></a>Dodatkowe źródła

- [Property shorthand - ES6 Features](http://es6-features.org/#PropertyShorthand)

### <a name="promises"></a>Obietnice (promises)

Obietnica (promise) to obiekt, który może być zwrócony synchronicznie z asynchronicznej funkcji. ([ref](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261#3cd0)).

Obietnice pozwalają zapobiec tzw. [callback hell](http://callbackhell.com/), i stosowane są coraz częściej we współczesnych projektach tworzonych w języku JavaScript.

#### <a name="sample-code-4"></a>Przykładowy kod

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

#### <a name="explanation-3"></a>Wyjaśnienie

Kiedy wykonujemy **zapytanie Ajax** odpowiedź nie jest synchroniczna, ponieważ żądamy zasobu, którego pobranie wymaga czasu. Może się nawet zdarzyć, że z jakiegoś powodu (404) zasób nigdy nie zostanie pobrany.

Aby radzić sobie w tego typu sytuacjach, ES2015 daje nam obietnice (*promises*). Obietnice mogą mieć trzy różne stany:

- oczekujący (pending)
- zakończony (fulfilled)
- odrzucony (rejected)

Powiedzmy, że chcemy wykorzystać obietnice dla obsługi zapytania Ajax w celu pobrania zasobu X.

##### <a name="create-the-promise"></a>Tworzenie obietnicy

Najpierw musimy stworzyć obietnicę. Dla stworzenia zapytania Ajax do zasobu X użyjemy metody GET jQuery.

```js
const xFetcherPromise = new Promise( // Tworzymy obietnicę poprzez słowo kluczowe new i zapisujemy go do zmiennej 
  function(resolve, reject) { // Konstruktor obietnicy przyjmuje jako argument funkcję, która sama przyjmuje dwa argumenty: resolve i reject
    $.get("X") // Uruchamiamy zapytanie Ajax
      .done(function(X) { // Kiedy zapytanie jest gotowe...
        resolve(X); // ... wypełniamy obietnicę z wartością X jako argumentem
      })
      .fail(function(error) { // Jeśli zapytanie się nie udało...
        reject(error); // ... odrzucamy obietnicę z wartością X jako argumentem
      });
  }
)
```

Jak widać na przykładzie, obiekt Promise przyjmuje funkcję-*executor*, która z kolei przy dwa argumenty **resolve** i **reject**. Argumenty te są funkcjami, które przy wezwaniu zmieniają stan obietnicy oczekujący (*pending*) na, odpowiednio, zakończony (*fulfilled*) i odrzucony (*rejected*). 

Obietnica znajduje się w stanie oczekiwania po stworzeniu instancji, a jej funkcja-*executor* jest natychmiast wykonywana. Kiedy jedna z funkcji *resolve* bądź *reject* zostanie wezwana w funkcji-*executor*, obietnica wywoła związane z nią procedury obsługi.

##### <a name="promise-handlers-usage"></a>Użycie procedur obsługi

By otrzymać rezultat obietnicy (lub błąd), musimy podpiąć ją pod procedury obsługi używając następującego kodu:

```js
xFetcherPromise
  .then(function(X) {
    console.log(X);
  })
  .catch(function(err) {
    console.log(err)
  })
```

Jeśli wszystko przebiegło prawidłowo, zostaje wywołane *resolve* i wykonana zostaje funkcja przekazana jako argument ```.then```. 

Jeśli zapytanie się nie udało, zostaje wywołane *reject* i wykonana zostaje funkcja przekazana jako argument ```.catch```. 
 
> **Uwaga:** Jeśli obietnica została już wypełniona lub odrzucona w momencie podpięcia odpowiedniej procedury obsługi, procedura będzie wywołana, tak więc nie wyniknie wyścig (race condition) między wykonaniem operacji asynchronicznej i wyznaczeniem procedur obsługi. [(Ref: MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise#Description)

#### <a name="external-resources-2"></a>Dodatkowe źródła

- [JavaScript Promises for dummies - Jecelyn Yeen](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [JavaScript Promise API - David Walsh](https://davidwalsh.name/promises)
- [Using promises - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [What is a promise - Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- [JavaScript Promises: an Introduction - Jake Archibald](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
- [Promise documentation - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

### <a name="template-literals"></a>Łańcuchy szablonowe (template literals)

Łańcuchy szablonowe to [*interpolacja wyrażenia*](https://en.wikipedia.org/wiki/String_interpolation) dla jedno- i wieloliniowych stringów.

Inaczej mówiąc, jest to nowa składnia stringów, pozwalająca na wygodne użycie dowolnych wyrażeń JavaScript (np. zmiennych).

#### <a name="sample-code-5"></a>Przykładowy kod

```js
const name = "Nick";
`Hello ${name}, następujące wyrażenie jest równe czterem: ${2+2}`;

// Hello Nick, następujące wyrażenie jest równe czterem: 4
```

#### <a name="external-resources-3"></a>Dodatkowe źródła

- [String interpolation - ES6 Features](http://es6-features.org/#StringInterpolation)
- [ES6 Template Strings - Addy Osmani](https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

### <a name="tagged-template-literals"></a>Oznaczone łańcuchy szablonowe

Tagi szablonowe to *funkcje które mogą być prefiksem dla [łańcucha szablonowego](#template-literals)*. Kiedy funkcja zostaje wezwana w ten sposób, pierwszy argument stanowi tablica *stringów*, które pojawiają się między interpolowanymi zmiennymi, a kolejne parametry to znaczenia wyrażeń wstawionych w string. Dla przechwycenia ich wszystkich można użyć operatora rozwijania. [(Ref: MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#Tagged_template_literals).

> **Uwaga :** Słynna biblioteka [styled-components](https://www.styled-components.com/) w dużej mierze polega na tej funkcjonalności.

Poniżej znajduje się przykład działania tagów szablonowych:
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

I jeszcze jeden - ciekawszy - przykład:
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

#### <a name="external-resources-4"></a>Dodatkowe źródła
- [Wes Bos on Tagged Template Literals](http://wesbos.com/tagged-template-literals/)
- [Library of common template tags](https://github.com/declandewet/common-tags)

### <a name="imports--exports"></a>Importy / eksporty

Moduły ES6 są używane dla otrzymania dostępu do zmiennych lub funkcji z drugich modułów, przy czym eksport powinien być jasno oznaczony w wyjściowym module.

Bardzo polecam zapoznać się z zasobami MDN dotyczącymi importów i eksportów (zobacz: Dodatkowe materiały), znajdziecie tam dokładne i przystępne wyjaśnienie.

#### <a name="explanation-with-sample-code-1"></a>Wyjaśnienie z przykładowym kodem

##### <a name="named-exports"></a>Nazwane eksporty (named exports)

Nazwane eksporty są używane do eksportu kilku wartości z modułu.

> **Uwaga :** W nazwanych eksportach można stosować jedynie [typy pierwszoklasowe](https://en.wikipedia.org/wiki/First-class_citizen), które posiadają nazwę.


```js
// mathConstants.js
export const pi = 3.14;
export const exp = 2.7;
export const alpha = 0.35;

// -------------

// myFile.js
import { pi, exp } from './mathConstants.js'; // Nazwany import - składnia podobna do destrukturyzacji
console.log(pi) // 3.14
console.log(exp) // 2.7

// -------------

// mySecondFile.js
import * as constants from './mathConstants.js'; // Wszystkie eksportowane wartości przypisane są do stałych
console.log(constants.pi) // 3.14
console.log(constants.exp) // 2.7
```

Chociaż nazwane importy przypominają *destrukturyzację*, posiadają inną składnią i nie są tym samym. Nie wspierają ani wartości domyślnych, ani *głębokiej* destrukturyzacji.

Poza tym, można tworzyć aliasy, ale składnia wygląda inaczej niż przy destrukturyzacji:

```js
import { foo as bar } from 'myFile.js'; // foo jest importowane i przypisane do nowej zmiennej bar
```

##### <a name="default-import--export"></a>Domyślny import / export

W przypadku domyślnego eksportu na jeden moduł przypada jeden domyślny eksport. Domyślny eksport może być funkcją, klasą, obiektem itp. Wartość ta jest traktowana jako "główna" eksportowana wartość, ponieważ importowanie jej jest najprostsze. [Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description)

```js
// coolNumber.js
const ultimateNumber = 42;
export default ultimateNumber;

// ------------

// myFile.js
import number from './coolNumber.js';
// Eksport domyślny, niezależnie od swojej nazwy w wyjściowym module, automatycznie przypisywany jest do zmiennej number;
console.log(number) // 42
```

Eksport funkcji:

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

#### <a name="external-resources-5"></a>Dodatkowe źródła

- [ES6 Modules in bulletpoints](https://ponyfoo.com/articles/es6#modules)
- [Export - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
- [Import - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Understanding ES6 Modules](https://www.sitepoint.com/understanding-es6-modules/)
- [Destructuring special case - import statements](https://ponyfoo.com/articles/es6-destructuring-in-depth#special-case-import-statements)
- [Misunderstanding ES6 Modules - Kent C. Dodds](https://medium.com/@kentcdodds/misunderstanding-es6-modules-upgrading-babel-tears-and-a-solution-ad2d5ab93ce0)
- [Modules in JavaScript](http://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript)

### <a name="-javascript-this"></a> *this* w JavaScript

Operator *this* zachowuje się inaczej niż w innych językach. W większości przypadków jego zachowanie zależy od tego, jak wywoływana jest funkcja.

Zagadnienie to może być dość trudne do zrozumienia, dlatego polecam zapoznać się dokładnie z dodatkowymi materiałami podanymi niżej. Postaram się wyjaśnić, jak sam rozumiem działanie *this*. Nauczyłem się tego z [artykułu Yehudy Katza](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/).

```js
function myFunc() {
  ...
}

// Po każdym wyrażeniu postaramy się określić znaczenie this w myFunc

myFunc.call("myString", "hello") // "myString" -- pierwszy parametr .call zapisywany jest w *this*

// W trybie non-strict
myFunc("hello") // window -- myFunc() to cukier syntaktyczny dla myFunc.call(window, "hello")

// W trybie strict
myFunc("hello") // undefined -- myFunc() to cukier syntaktyczny dla myFunc.call(undefined, "hello")
```

```js
var person = {
  myFunc: function() { ... }
}

person.myFunc.call(person, "test") // person Object -- pierwszy parametr .call zapisywany jest w *this*
person.myFunc("test") // person Object -- person.myFunc() to cukier syntaktyczny dla person.myFunc.call(person, "test")

var myBoundFunc = person.myFunc.bind("hello") // Tworzy nową funkcję, w której "hello" zapisywane jest w *this*
person.myFunc("test") // person Object -- Metoda bind nie ma wpływu na oryginalną metodę
myBoundFunc("test") // "hello" -- myBoundFunc to person.myFunc z "hello" przywiązanym do *this*
```

#### <a name="external-resources-6"></a>Dodatkowe źródła

- [Understanding JavaScript Function Invocation and "this" - Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)
- [JavaScript this - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

### <a name="class"></a>Klasa

JavaScript jest językiem [opartym na prototypach](https://en.wikipedia.org/wiki/Prototype-based_programming) (podczas gdy, na przykład, Java jest [oparta na klasach](https://en.wikipedia.org/wiki/Class-based_programming)). ES6 wprowadza klasy JavaScript, które mają być cukrem syntaktycznym dla dziedziczenia opartego na prototypach a *nie* nowym modelem dziedziczenia opartego na klasach ([ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)).

Użycie słowa *class* może istotnie prowadzić do błędów, jeśli jesteśmy przyzwyczajeni do klas stosowanych w innych językach. Dlatego też klasy w JavaScript lepiej traktować jak zupełnie odrębne zagadnienie.

Ponieważ nasz przewodnik nie ma na celu nauki języka od podstaw, zakładam, że wiesz, czym są prototypy i jak działają. Jeśli nie, zapoznaj się z dodatkowymi materiałami znajdującymi się pod kodem przykładowym.

#### <a name="samples"></a>Przykłady

Składnia prototypu sprzed ES6:

```js
var Person = function(name, age) {
  this.name = name;
  this.age = age;
}
Person.prototype.stringSentence = function() {
  return "Hello, my name is " + this.name + " and I'm " + this.age;
}
```

Składnia klasy z ES6:

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

#### <a name="external-resources-7"></a>Dodatkowe źródła

Omówienie prototypów:

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Inheritance and the prototype chain - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

Omówienie klas:

- [ES6 Classes in Depth - Nicolas Bevacqua](https://ponyfoo.com/articles/es6-classes-in-depth)
- [ES6 Features - Classes](http://es6-features.org/#ClassDefinition)
- [JavaScript Classes - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

### <a name="extends-and-super-keywords"></a>Słowa kluczowe `extends` i `super`

Słowo kluczowe `extends` używane jest w deklaracji klas w celu stworzenia klasy dziedziczącej od innej klasy ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends)). Klasa pochodna dziedziczy wszystkie własności klasy bazowej, może dodawać nowe lub modyfikować odziedziczone własności.

Słowo kluczowe `super` służy do wzywania funkcji na klasie bazowej obiektu, włącznie z jej konstruktorem. 

- słowo kluczowe `super` musi być użyte przed słowem `this` w konstruktorze
- Wezwanie `super()` wywołuje konstruktor klasy bazowej. Jeśli chcesz przekazać argumenty w konstruktorze klasy do konstruktora klasy bazowej, użyj `super(arguments)`.
- Jeśli klasa bazowa posiada metodę (także statyczną) o nazwie `X`, można użyć `super.X()`, by wywołać ją w klasie pochodnej.

#### <a name="sample-code-6"></a>Przykładowy kod

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
    // Wzywany jest konstruktor klasy bazowej z szerokością i długością przekazanymi przez Polygon
    super(length, length);
    // Uwaga: W klasach pochodnych super() musi zostać wezwane przed 'this'. W przeciwnym razie pojawi się błąd.
    this.name = 'Square';
    this.length = length;
  }

  getCustomHelloPhrase() {
    const polygonPhrase = super.getHelloPhrase(); // super.X() daje dostęp do metody klasy bazowej
    return `${polygonPhrase} with a length of ${this.length}`;
  }

  get area() {
    return this.height * this.width;
  }
}

const mySquare = new Square(10);
console.log(mySquare.area) // 100
console.log(mySquare.getHelloPhrase()) // 'Hi, I am a Square' -- Square dziedziczy od Polygon i ma dostęp do jego metod
console.log(mySquare.getCustomHelloPhrase()) // 'Hi, I am a Square with a length of 10'
```

**Uwaga :** Jeśli spróbujemy użyć `this` przed wezwaniem `super()` w klasie Square, pojawi się ReferenceError 

```js
class Square extends Polygon {
  constructor(length) {
    this.height; // ReferenceError, najpierw trzeba wezwać super!

    // Wzywany jest konstruktor klasy bazowej z szerokością i długością przekazanymi przez Polygon
    super(length, length);

    // Uwaga: W klasach pochodnych super() musi zostać wezwane przed 'this'. W przeciwnym razie pojawi się błąd.
    this.name = 'Square';
  }
}
```

#### <a name="external-resources-8"></a>Dodatkowe źródła

- [Extends - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends)
- [Super operator - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super)
- [Inheritance - MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance)

### <a name="async-await"></a>Składnia async/await

Oprócz [Obietnic (Promises)](#promises), możesz spotkać jeszcze jeden rodzaj składni dla obsługi kodu asynchronicznego, a mianowicie *async / await*.
 
Rolą funkcji async/await jest uproszczenie zachowania używanych synchronicznie obietnic oraz by używać grup Obietnic. Async/await przypomina połączenie generatorów i obietnic. Funkcje async *zawsze* zwracają Obietnicę ([Ref: MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function))

> **Uwaga :** Ponieważ funkcje async / await bazują na obietnicach, aby prawidłowo stosować wspomniane funkcje, musisz najpierw dobrze rozumieć działanie obietnic.

> **Uwaga 2:** [*await* musi zostać użyte w funkcji *async*](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9#f3f0), co oznacza, że await nie można użyć na wyższym poziomie kodu, nie znajdującym się wewnątrz funkcji async.

#### <a name="sample-code-7"></a>Przykładowy kod

```js
async function getGithubUser(username) { // słowo kluczowe async pozwala użyć await w funkcji i oznacza, że funkcja zwraca obietnicę
  const response = await fetch(`https://api.github.com/users/${username}`); // Czeka na obietnicę przed przejściem do reszty kodu
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user)) // logowanie użytkownika - nie można użyć await, bo nie znajduje się w funkcji async
  .catch(err => console.log(err)); // jeśli w funkcji async pojawi się błąd, wyłapujemy go tutaj
```

#### <a name="explanation-with-sample-code-2"></a>Wyjaśnienie z przykładowym kodem

*Async / Await* jest zbudowany na obietnicach, ale pozwala na bardziej imperatywny styl kodu.

Operator *async* oznacza funkcję jako asynchroniczną. Dana funkcja zawsze zwraca Obietnicę. W funkcji *async* można użyć operatora *async*, aby zatrzymać wykonanie kodu na danej linijce dopóki zwracana Obietnica nie zostanie wypełniona bądź odrzucona.

```js
async function myFunc() {
  // ponieważ to funkcja async, możemy użyć operatora await
  return "hello world";
}

myFunc().then(msg => console.log(msg)) // "hello world" -- wartość zwracana przez myFunc jest przekształcana w obietnicę ze względu na operator async
```

Kiedy zostaje osiągnięte wyrażenie *return* w funkcji async, Obietnica zostaje wypełniona ze zwracaną wartością. Jeśli wewnątrz funkcji async pojawia się błąd, stan Obietnicy zmienia się na *odrzucony* (*rejected*). Jeśli funkcja async nie zwraca żadnej wartości, Obietnica zostanie zwrócona i wypełniona bez wartości, kiedy zakończy się wykonanie funkcji async.


Operator *await* jest używany do oczekiwania na wypełnienie Obietnicy i może być użyty jedynie w ciele funkcji *async*. Kiedy zostanie osiągnięty, następuje wstrzymanie wypełnienia kodu do chwili wypełnienia obietnicy.

> **Uwaga :** *fetch* to funkcja, która zwraca Obietnicę i pozwala na wykonania zapytania Ajax.

Rozpatrzmy przykład użycia fetch z obietnicami:

```js
function getGithubUser(username) {
  return fetch(`https://api.github.com/users/${username}`).then(response => response.json());
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

A oto ekwiwalent z *async / await*:

```js
async function getGithubUser(username) { // dozwolone użycie obietnicy + await
  const response = await fetch(`https://api.github.com/users/${username}`); // Wykonanie wstrzymane do czasu wypełnienia obietnicy fetch
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

Składnia *async / await* jest wyjątkowo użyteczna, gdy chcemy połączyć w łańcuch wzajemnie zależne od siebie obietnice.

Na przykład, kiedy potrzebujemy tokena, by pobrać z bazy danych post na blogu i informacje o autorze:

> **Uwaga :** wyrażenia *await* muszą być otoczone nawiasami, aby można było wezwać wartości ich metod i własności w jednej linijce.

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

##### <a name="error-handling"></a>Obsługa błędów

Jeśli nie dodamy bloków *try / catch* wokół wyrażeń *await*, nieschwytane wyjątki - niezależnie od tego, czy pojawią się w ciele funkcji *async*, czy zostaną wstrzymane w czasie *await* - doprowadzą do odrzucenia obietnicy zwracanej przez funkcję *async*. Użycie wyrażenia `throw` w funkcji async sprowadza się do tego samego, co zwrot odrzuconej obietnicy. [(Ref: PonyFoo)](https://ponyfoo.com/articles/understanding-javascript-async-await#error-handling).  

> **Uwaga :** Obietnice zachowują się tak samo!

Oto jak obsługujemy błędy z pomocą obietnic:

```js
function getUser() { // Obietnica będzie odrzucona!
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

Ekwiwalent z *async / await*:

```js
async function getUser() { // Zwrócona obietnica zostanie odrzucona!
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

#### <a name="external-resources-9"></a>Dodatkowe źródła

- [Async/Await - JavaScript.Info](https://javascript.info/async-await)
- [ES7 Async/Await](http://rossboucher.com/await/#/)
- [6 Reasons Why JavaScript’s Async/Await Blows Promises Away](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9)
- [JavaScript awaits](https://dev.to/kayis/javascript-awaits)
- [Using Async Await in Express with Node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)
- [Async Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
- [Using async / await in express with node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)

### <a name="truthy--falsy"></a>Prawda / fałsz

W JavaScript wartości "prawda" lub "fałsz" określane są w kontekście boolowskim. Przykładem kontekstu boolowskiego może być określenie warunku ```if```: 

Jako prawda (```true```) określona będzie każda wartość, jeśli nie jest równa:

- ```false```
- ```0```
- ```""``` (empty string)
- ```null```
- ```undefined```
- ```NaN```

Przykłady *kontekstu boolowskiego*:

- określenie warunku ```if```

```js
if (myVar) {}
```

```myVar``` może być dowolnym [obiektem pierwszoklasowym](https://en.wikipedia.org/wiki/First-class_citizen) (zmienna, funkcja, typ boolowski) ale będzie przekształcona w typ boolowski, ponieważ określana jest w kontekście boolowskim.

- Po operatorze logicznym **NOT** ```!```

This operator returns false if its single operand can be converted to true; otherwise, returns true.
Operator ten zwraca "fałsz" jeśli jego jedyny operand może być przekształcony w znaczenie "prawda"; w przeciwnym razie zwraca "prawdę"

```js
!0 // true -- 0 to "fałsz", więc zwraca "prawdę"
!!0 // false -- 0 to "fałsz", więc !0 zwraca "prawdę", więc !(!0) zwraca "fałsz"
!!"" // false -- pusty string to "fałsz", więc NOT (NOT false) równe jest "fałszowi"
```

- Z konstruktorem obiektu *Boolean*

```js
new Boolean(0) // false
new Boolean(1) // true
```

- Z operatorem warunkowym

```js
myVar ? "prawda" : "fałsz"
```

myVar jest określana w kontekście boolowskim.

```

#### <a name="external-resources-10"></a>Dodatkowe źródła

- [Truthy (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
- [Falsy (MDN)](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
- [Truthy and Falsy values in JS - Josh Clanton](http://adripofjavascript.com/blog/drips/truthy-and-falsy-values-in-javascript.html)

### <a name="anamorphisms-and-catamorphisms"></a>Anomorfizmy i katamorfizmy

#### <a name="anamorphisms"></a>Anamorfizmy

Anamorfizmy to funkcje, które mapują pewien obiekt to bardziej złożonej struktury zawierającej typ tego obiektu. Jest to proces *rozwijania* (*unfolding*) prostej struktury do bardziej złożonej. Rozpatrzmy rozwijanie liczby całkowitej do listy liczb całkowitych. Początkowym obiektem jest liczba całkowita, bardziej złożoną strukturą - lista liczb całkowitych.

**Przykładowy kod**

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

#### <a name="catamorphisms"></a>Katamorfizmy

Katamorfizmy to przeciwieństwo anamorfizmów - "zwijają" bardziej skomplikowane struktury do prostszych. Przyjrzyjmy się funkcji `product`, która przyjmuje listę liczb całkowitych i zwraca pojedynczą liczbę całkowitą. 

**Przykładowy kod**

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

#### <a name="external-resources-11"></a>Dodatkowe źródła

* [Anamorphisms in JavaScript](http://raganwald.com/2016/11/30/anamorphisms-in-javascript.html)
* [Anamorphism](https://en.wikipedia.org/wiki/Anamorphism)
* [Catamorphism](https://en.wikipedia.org/wiki/Catamorphism)

### <a name="generators"></a>Generatory

Innym sposobem zapisania funkcji `downToOne` jest użycie Generatora. Stworzenie instancji obiektu `Generator` wymaga użycia deklaracji funkcji `function *`. Generatory to funkcje, które mogą być zamknięte i później uruchomione ponownie z zachowaniem kontekstu między kolejnymi uruchomieniami.

Na przykład funkcja `downToOne` może być zapisana tak:

```js
function * downToOne(n) {
  for (let i = n; i > 0; --i) {
    yield i;
  }
}

[...downToOne(5)] //[ 1, 2, 3, 4, 5 ]
```

Generatory zwracają obiekt iterowalny. Kiedy wzywana jest funkcja iteratora `next()`, jest ona wykonywana aż do perwszego wyrażenia `yield`, które określa wartość, jaka zostanie zwrócona przez iterator lub z `yield*`, które odsyła do kolejnej funkcji-generatora. Jeśli w generatorze wezwane jest wyrażenie `return`, generator zostanie oznaczony jako wyczerpany i przekazany jako wartość do zwrotu. Kolejne wezwania `next()` nie zwrócą żadnych nowych wartości. 

**Przykładowy kod**

```js
// Przykład Yield
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

Wyrażenie `yield*` pozwala generatorowi wzywać inną funkcję-generator w czasie iteracji. 

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
// Przykład Generator Return
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

#### <a name="external-resources-12"></a>Dodatkowe źródła

* [Mozilla MDN Web Docs, Iterators and Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Generators)

### <a name="static-methods"></a>Metody statyczne

#### <a name="short-explanation-1"></a>Krótkie wyjaśnienie

Słowo kluczowe `static` jest używane w klasach dla deklaracji metod statycznych. Metody statyczne to funkcje klasy, które należą do obiektu klasy, ale nie są dostępne dla instancji tej klasy.

#### <a name="sample-code-8"></a>Przykładowy kod

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }
}

//Zauważ, że nie musieliśmy tworzyć instancji klasy Repo
console.log(Repo.getName()) //Repo name is modern-js-cheatsheet

let r = new Repo();
console.log(r.getName()) //Nieprzechwycony TypeError: repo.getName nie jest funkcją
```

#### <a name="detailed-explanation-2"></a>Szczegółowe wyjaśnienie

Metody statyczne mogą być wezwane z innych metod statycznych za pomocą słowa kluczowego `this`, co nie działa w przypadku metod niestatycznych. Metody niestatyczne nie mają bezpośredniego dostępu do metod statycznych z użyciem `this`.

##### <a name="calling-other-static-methods-from-a-static-method"></a>Wzywanie innych metod statycznych z metod statycznych

Aby wezwać metodę statyczną z innej metody statycznej, należy użyć słowa kluczowego `this`:

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

##### <a name="calling-static-methods-from-non-static-methods"></a>Wzywanie metod statycznych z metod niestatycznych

Metody niestatyczne mogą wzywać metody statyczne na dwa sposoby;
1. ###### Używając nazwy klasy.

Aby zyskać dostęp do metody statycznej z metody niestatycznej używamy nazwy klasy i wzywamy metodę statyczną jak własność, np. `ClassName.StaticMethodName`

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName(){
    return Repo.getName() + ' and it contains some really important stuff'
  }
}

// musimy stworzyć instancję klasy, by mieć dostęp do metod niestatycznych
let r = new Repo()
console.log(r.useName()) //Repo name is modern-js-cheatsheet and it contains some really important stuff
```

2. ###### Używając konstruktora

Metody statyczne mogą być wzywane jak własności na obiekcie konstruktora.

```js
class Repo{
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName(){
    //Wzywa metodę statyczną jako własność konstruktora
    return this.constructor.getName() + ' and it contains some really important stuff'
  }
}

// musimy stworzyć instancję klasy, by mieć dostęp do metod niestatycznych
let r = new Repo()
console.log(r.useName()) //Repo name is modern-js-cheatsheet and it contains some really important stuff
```

#### <a name="external-resources-13"></a>Dodatkowe źródła
- [static keyword- MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static)
- [Static Methods- Javascript.info](https://javascript.info/class#static-methods)
- [Static Members in ES6- OdeToCode](http://odetocode.com/blogs/scott/archive/2015/02/02/static-members-in-es6.aspx)

## <a name="glossary"></a>Słowniczek

### <a name="-scope"></a>Zakres widoczności (scope)

Kontekst, w którym wartości i wyrażenia są "widoczne" lub można się do nich odwoływać. Jeśli zmienna lub inne wyrażenie "nie znajduje się w aktualnym zakresie widoczności", oznacza to, że jest niedostępna do użytku.

Źródło: [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Scope)

### <a name="-variable-mutation"></a>Przekształcenie zmiennej (variable mutation)

Mówimy, że zmienna została przekształcona, kiedy jej wartość jest inna niż wartość początkowa.

```js
var myArray = [];
myArray.push("firstEl") // myArray została przekształcona
```

Zmienna jest określana jako "niemodyfikowalna" (*immutable*), kiedy nie może być przekształcana.

[Zobacz artykuł](https://developer.mozilla.org/en-US/docs/Glossary/Mutable).
