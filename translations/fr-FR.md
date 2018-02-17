# Modern JavaScript Cheatsheet

![Modern JavaScript cheatsheet](https://i.imgur.com/aexPxMb.png)
<small>Crédits de l’image: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</small>

## Introduction

### Motivation

Ce document est un condensé de tout ce que vous devriez savoir sur le JavaScript que vous allez rencontrer dans des projets modernes.

Ce guide n’a pas été conçu pour vous apprendre JavaScript à partir de rien, mais pour aider les développeurs ayant des connaissances basiques qui ont des problèmes avec les codebases modernes (ou pour apprendre React, par exemple) à cause des concepts JavaScript utilisés.

De plus, je vous donnerai parfois des conseils personnels qui pourraient porter à débat, mais je prendrai le soin de le mentionner lorsque je le ferai.

> **Note :** La plupart des concepts introduits ici viennent d’une mise à jour du langage JavaScript (ES2015, souvent appelé ES6. Vous pouvez trouver les nouvelles fonctionnalités. ajoutées par cette mise à jour [ici](http://es6-features.org) (ce site est vraiment bien fait !).

### Ressources complémentaires

Lorsque vous avez de la peine à comprendre une notion, je vous suggère de chercher des réponses dans les ressources suivantes :

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/en-US/search?q=)
- [You don't know JS (livre)](https://github.com/getify/You-Dont-Know-JS)
- [ES6 Features with examples](http://es6-features.org)
- [WesBos blog (ES6)](http://wesbos.com/category/es6/)
- [Javascript Basics for Beginners](https://www.udacity.com/course/javascript-basics--ud804) - a free Udacity course
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) pour trouver des blogs et des ressources spécifiques
- [StackOverflow](https://stackoverflow.com/questions/tagged/javascript)

> **Note :** Presque toutes les ressources externes listées dans ce document sont en anglais, à l’exception des liens menant vers le Mozilla Developer Network (MDN) qui lui est traduit en français.

## Table des matières
* [Modern JavaScript Cheatsheet](#modern-javascript-cheatsheet)
   * [Introduction](#introduction)
      * [Motivation](#motivation)
      * [Ressources complémentaires](#ressources-complémentaires)
   * [Table des matières](#table-des-matières)
   * [Notions](#notions)
      * [Déclaration des variables : var, const, let](#déclaration-des-variables--var-const-let)
         * [Explication brève](#explication-brève)
         * [Code d’exemple](#code-dexemple)
         * [Explication détaillée](#explication-détaillée)
            * [var](#var)
            * [let](#let)
            * [const](#const)
         * [Ressources externes](#ressources-externes)
      * [<a name="user-content-arrow_func_concept"></a> Fonction fléchée](#-fonction-fléchée)
         * [Code d'exemple](#code-dexemple-1)
         * [Explication détaillée](#explication-détaillée-1)
            * [Concision](#concision)
            * [Référence de <em>this</em>](#référence-de-this)
         * [Ressources utiles](#ressources-utiles)
      * [Valeur par défaut d'un paramètre dans une fonction](#valeur-par-défaut-dun-paramètre-dans-une-fonction)
         * [External resource](#external-resource)
      * [Déstructurer des objets et des tableaux](#déstructurer-des-objets-et-des-tableaux)
         * [Explication avec du code](#explication-avec-du-code)
         * [Ressources utiles](#ressources-utiles-1)
      * [Méthodes de tableau : map / filter / reduce](#méthodes-de-tableau--map--filter--reduce)
         * [Code d'exemple](#code-dexemple-2)
         * [Explication](#explication)
            * [Array.prototype.map()](#arrayprototypemap)
            * [Array.prototype.filter()](#arrayprototypefilter)
            * [Array.prototype.reduce()](#arrayprototypereduce)
               * [À la première étape d'itération](#À-la-première-étape-ditération)
               * [À la deuxième étape d'itération](#À-la-deuxième-étape-ditération)
               * [À la troisième étape d'itération](#À-la-troisième-étape-ditération)
               * [À la quatrième étape d'itération](#À-la-quatrième-étape-ditération)
               * [[...] À la dernière étape d'itération](#-À-la-dernière-étape-ditération)
         * [Ressource externe](#ressource-externe)
      * [Opérateur de décomposition "..."](#opérateur-de-décomposition-)
         * [Code d'exemple](#code-dexemple-3)
         * [Explication](#explication-1)
            * [Dans des tableaux (comme des tableaux)](#dans-des-tableaux-comme-des-tableaux)
            * [Paramètre de reste d'une fonction](#paramètre-de-reste-dune-fonction)
            * [Décomposition des propriétés d'un objet](#décomposition-des-propriétés-dun-objet)
         * [Ressources externes](#ressources-externes-1)
      * [Raccourci pour les propriétés d'objet](#raccourci-pour-les-propriétés-dobjet)
         * [Explication](#explication-2)
         * [Ressources externes](#ressources-externes-2)
      * [Promesses](#promesses)
         * [Code d'exemple](#code-dexemple-4)
         * [Explication](#explication-3)
            * [Créer la promesse](#créer-la-promesse)
            * [Utilisation des déclencheurs de promesse](#utilisation-des-déclencheurs-de-promesse)
         * [Ressources externes](#ressources-externes-3)
      * [Littéraux de modèle](#littéraux-de-modèle)
         * [Code d'exemple](#code-dexemple-5)
         * [Ressources externes](#ressources-externes-4)
      * [Littéraux de modèle étiquetés](#littéraux-de-modèle-étiquetés)
         * [Ressources externes](#ressources-externes-5)
      * [Imports / exports](#imports--exports)
         * [Explication avec un code d'exemple](#explication-avec-un-code-dexemple)
            * [Exports nommés](#exports-nommés)
            * [Import/export par défaut](#importexport-par-défaut)
         * [Ressources externes](#ressources-externes-6)
      * [<em>this</em> en JavaScript](#-this-en-javascript)
         * [Ressources externes](#ressources-externes-7)
      * [Classe](#classe)
         * [Exemples](#exemples)
         * [Ressources externes](#ressources-externes-8)
      * [Mots clés extends et <code>super</code>](#mots-clés-extends-et-super)
         * [Code d’exemple](#code-dexemple-6)
         * [Ressources](#ressources)
      * [Async Await](#async-await)
         * [Code d’exemple](#code-dexemple-7)
         * [Explication avec un code d’exemple](#explication-avec-un-code-dexemple-1)
            * [Gestion d’erreur](#gestion-derreur)
         * [Ressources externes](#ressources-externes-9)
      * [Vérité / fausseté](#vérité--fausseté)
         * [Ressources externes](#ressources-externes-10)
      * [Méthodes statiques](#méthodes-statiques)
         * [Explication courte](#explication-courte)
         * [Code d’exemple](#code-dexemple-8)
         * [Explication détaillée](#explication-détaillée-2)
            * [Appeler d’autres méthodes statiques depuis une méthode statique](#appeler-dautres-méthodes-statiques-depuis-une-méthode-statique)
            * [Appeler des méthodes statiques depuis des méthodes non statiques](#appeler-des-méthodes-statiques-depuis-des-méthodes-non-statiques)
               * [En utilisant le nom de la classe](#en-utilisant-le-nom-de-la-classe)
               * [Avec le constructeur](#avec-le-constructeur)
         * [Ressources externes](#ressources-externes-11)
   * [Glossaire](#glossaire)
      * [Portée (<em>scope</em>)](#-portée-scope)
      * [Mutation de variable](#-mutation-de-variable)

## Notions

### Déclaration des variables : var, const, let

En JavaScript, il y a trois mots-clés disponibles pour déclarer une variable, et chacun a ses différences. Ces mots-clés sont ```var```, ```let``` et ```const```.

#### Explication brève

Les variables déclarées avec le mot-clé ```const``` ne peuvent pas être réassignées, alors que celles déclarées avec ```let``` et ```var``` le peuvent.

Je vous recommande de toujours déclarer vos variables avec ```const``` par défaut, et avec ```let``` si vous avez besoin de la *muter* ou de la réassigner plus tard.

<table>
  <tr>
    <th></th>
    <th>Portée</th>
    <th>Réassignable</th>
    <th>Mutable</th>
   <th><a href="#tdz_sample">Temporal Dead Zone</a></th>
  </tr>
  <tr>
    <th>const</th>
    <td>Bloc</td>
    <td>Non</td>
    <td><a href="#const_mutable_sample">Oui</a></td>
    <td>Oui</td>
  </tr>
  <tr>
    <th>let</th>
    <td>Bloc</td>
    <td>Oui</td>
    <td>Oui</td>
    <td>Oui</td>
  </tr>
   <tr>
    <th>var</th>
    <td>Fonction</td>
    <td>Oui</td>
    <td>Oui</td>
    <td>Non</td>
  </tr>
</table>

#### Code d’exemple

```javascript
const person = "Nick";
person = "John" // Déclenchera une erreur, person ne pouvant pas être réassigné
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", le réassignement est permis avec let
```

#### Explication détaillée

La [*portée*](#scope_def) d’une variable définit "où la variable est disponible dans le code".

##### var

La portée des variables déclarées avec ```var``` s’étend à la fonction qui la contient, ce qui signifie que lorsqu‘une variable est créée dans une fonction, tout dans cette fonction peut y accéder. De plus, on ne pourra pas accéder à cette variable de l’extérieur de cette fonction. 

```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - myVar est accessible à l'intérieur de la fonction
}
console.log(myVar); // Émet une ReferenceError, myVar n'est pas accessible en dehors de la fonction
```

Voici un exemple plus subtil, toujours sur la portée des variables :

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // La portée de myVar s'étendant à toute la fonction, nous venons d'écraser la valeur précédente de myVar ("Nick"), qui est devenue "John"
  }
  console.log(myVar); // "John" - les instructions dans le bloc if ont affecté cette valeur
}
console.log(myVar); // Produit une ReferenceError, myVar n'étant pas disponible en dehors de la fonction
```

De plus, les variables déclarées avec *var* sont déplacées tout en haut de leur portée à l'exécution. Ce comportement est appelé [var hoisting](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Instructions/var#La_remontée_de_variables_(hoisting)).

Ce bout de code :

```js
console.log(myVar) // undefined -- aucune erreur produite
var myVar = 2;
```

est compris à l'exécution comme :

```js
var myVar;
console.log(myVar) // undefined -- aucune erreur produite
myVar = 2;
```

##### let

```var``` et ```let ``` sont presque identiques, mais les variables déclarées avec ```let```

- ont leur portée qui est limitée au bloc qui les entoure
- ne sont **pas** accessibles avant d'être assignées
- ne peuvent pas être redéclarées dans la même portée

Observons l'impact de la nouvelle portée dans l'exemple précédent :

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // la portée de myVar étant limitée au bloc if, nous venons de crééer une nouvelle variable myVar.
    // cette variable n'est pas accessible en dehors du bloc if
    // et est totalement indépendante du premier myVar créé.
  }
  console.log(myVar); // "Nick" - les instructions dans le bloc if n'ont PAS affecté cette valeur
}
console.log(myVar); // Produit une ReferenceError, myVar n'étant pas disponible en dehors de la fonction
```

<a name="tdz_sample"></a> Maintenant, observons ce que signifie pour les variables créées avec *let* (et *const*) de ne pas être accessibles avant d'avoir été assignées :

```js
console.log(myVar) // déclenche une ReferenceError !
let myVar = 2;
```

Contrairement aux variables *var*, si vous essayez de lire ou d'écrire dans une variable *let* ou *const* avant d'être assignées une erreur se produira. Ce phénomène est souvent appelé [*Temporal dead zone*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_Dead_Zone_and_errors_with_let) ou *TDZ*.

> **Note :** Techniquement, les déclarations de variables *let* and *const*sont aussi affectées par le *var hoisting*, mais pas leur assignation. Vu qu'elles sont faite pour ne pas pouvoir être utilisées avant l'assignation, on a l'impression qu'il n'y a pas de *hoisting*, mais il y en a un. Si vous voulez en savoir plus, vous pouvez lire cette [explication très détaillée](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified).

Par ailleurs, vous ne pouvez pas re-déclarer une variable *let* :

```js
let myVar = 2;
let myVar = 3; // Produit une SyntaxError
```

##### const

Les variables déclarées avec```const``` se comportent comme des variables *let*, mais elles ne peuvent pas être réassignées.

Pour résumer, les variables *const* :

- ont leur portée qui est limitée au bloc qui les entoure
- ne sont pas accessibles avant leur assignation
- ne peuvent pas être redéclarées dans la même portée
- ne peuvent pas être réassignées

```js
const myVar = "Nick";
myVar = "John" // cause une erreur, le réassignement n'est pas permis
```

```js
const myVar = "Nick";
const myVar = "John" // cause une erreur, la redéclaration n'est pas permise
```

<a name="const_mutable_sample"></a> Mais il y a une subtilité : les variables ```const``` ne sont pas [**immutables**](#mutation_def) ! Concrètement, cela signifie que les *objets* et *tableaux* ```const``` **peuvent** être mutées.

Pour les objets :
```js
const person = {
  name: 'Nick'
};
person.name = 'John' // ceci fonctionnera ! la variable person n'est pas complètement réassignée, mais mutée
console.log(person.name) // "John"
person = "Sandra" // cause une erreur, car le réassignement n'est pas autorisé avec les variables déclarées avec const
```

Pour les tableaux :
```js
const person = [];
person.push('John'); // ceci fonctionnera ! la variable person n'est pas complètement réassignée, mais mutée
console.log(person[0]) // "John"
person = ["Nick"]  // cause une erreur, car le réassignement n'est pas autorisé avec les variables déclarées avec const
```

#### Ressources externes

- [How let and const are scoped in JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Temporal Dead Zone (TDZ) Demystified](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="arrow_func_concept"></a> Fonction fléchée

Avec la mise à jour ES6 de JavaScript, nous pouvons utiliser des *fonctions fléchées*, qui sont un autre moyen de déclarer et d'utiliser des fonctions. Voici les bénéfices qu'elles apportent :

- Plus concis
- *this* se réfère à l'extérieur de la fonction fléchée
- ```return``` implicite

#### Code d'exemple

- Concision et retour implicite

```js
function double(x) { return x * 2; } // Manière traditionnelle
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // Même fonction écrite sous forme de fonction fléchée avec un retour implicite
console.log(double(2)) // 4
```

- Référence de *this*

Dans une fonction fléchée, *this* est égal à la valeur de *this* dans le contexte d'exécution alentour. Basiquement, avec les fonctions fléchées, vous n'êtes plus obligé d'utiliser l'astuce "that = this" avant d'appeler une fonction à l'intérieur d'une fonction.

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### Explication détaillée

##### Concision

Les fonctions fléchées sont plus concises que les fonctions traditionnelles par plusieurs aspects. Voyons tous les cas possibles :

- Retour implicite VS explicite

Un **retour explicite** est une fonction où le mot-clé ```return``` est utilisé dans son corps.

```js
  function double(x) {
    return x * 2; // cette fonction retourne explicitement x * 2, le mot-clé return est utilisé
  }
```

Dans l'écriture de foncitons traditionnelle, le retour était toujours explicite. Mais avec les fonctions fléchées, vous pouvez faire un *retour implicite* ce qui signifie que vous n'êtes pas obligés d'utiliser le mot-clé *return* pour retourner une valeur.

Pour faire un retour implicite, le code doit être écrit en une ligne.

```js
  const double = (x) => {
    return x * 2; // Ce retour est explicite
  }
```

Comme il n'y a qu'un retour de valeur ici, nous pouvons utiliser un retour implicite.

```js
  const double = (x) => x * 2;
```

Pour ce faire, il nous suffit de **supprimer les accolades** et le mot-clé **return**. C'est pour cette raison qu'on qualifie ce retour d'*implicite* : le mot-clé *return* n'est pas là. mais la fonction va bien retourner ```x * 2```.

> **Note :** Si votre fonction ne retourne aucune valeur (avec des *effets secondaires*), elle ne fait ni retour implicite ni explicite.

De plus, si vous voulez retourner un *objet* vous **devez mettre des parenthèses autour** pour éviter un conflit avec les accolades de bloc :

```js
const getPerson = () => ({ name: "Nick", age: 24 })
console.log(getPerson()) // { name: "Nick", age: 24 } -- l'objet est implicitement retourné par la fonction fléchée
```

- Uniquement un argument

Si votre fonction ne prend qu'un paramètre, vous pouvez omettre les parenthèses autour. En reprenant un exemple au dessus :

```js
  const double = (x) => x * 2; // cette fonction fléchée ne prend qu'un paramètre
```

Les parenthèses autour du paramètre peuvent être évitées :

```js
  const double = x => x * 2; // cette fonction fléchée ne prend qu'un paramètre
```

- Pas de paramètres

Lorsqu'une fonction fléchée ne prend aucun paramètre, vous devez obligatoirement mettre des parenthèses pour que la syntaxe soit valide :

```js
  () => { // avec des parenthèses, tout fonctionne
    const x = 2;
    return x;
  }
```

```js
  => { // pas de parenthèses, ceci ne fonctionnera pas !
    const x = 2;
    return x;
  }
```

##### Référence de *this*

Pour comprendre cette subtilité des fonctions fléchées, vous devez savoir comment [this](#this_def) fonctionne en JavaScript.

Dans une fonction fléchée, *this* est égal à la valeur de *this* dans le contexte d'exécution alentour. Cela signifie qu'une fonction fléchée ne créée pas de nouveau *this*, mais le prend autour à la place.

Sans une fonction fléchée, pour accéder à une variable présente dans *this* dans une fonction à l'intérieur d'une fonction, vous deviez utiliser l'astuce de *that = this* ou *self = this*.

Par exemple, voici comment utiliser setTimeout à l'intérieur de myFunc :

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // astuce that = this
  setTimeout(
    function() { // Un nouveau *this* est créé dans la portée de cette fonction
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // undefined -- voir la déclaration de fonction au-dessus
    },
    0
  );
}
```

Mais avec une fonction fléchée, *this* est pris de l'extérieur :

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => { // this pris de l'extérieur, signifiant myFunc ici
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

#### Ressources utiles

- [Arrow functions introduction - WesBos](http://wesbos.com/arrow-functions/)
- [Fonction fléchées - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Fonctions/Fonctions_fl%C3%A9ch%C3%A9es)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

### Valeur par défaut d'un paramètre dans une fonction

À partir de la mise à jour de JavaScript ES2015, vous pouvez assigner une valeur par défaut à un paramètre de fonction en utilisant la syntaxe suivante

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- aucune valeur n'étant donnée, la valeur par défaut est utilisée
console.log(myFunc(5)) // 5 -- une valeur est donnée donc x est égal à 5 dans myFunc

console.log(myFunc(undefined)) // 10 -- la valeur undefined est donnée, donc x est assigné à la valeur par défaut
console.log(myFunc(null)) // null -- une valeur (null) étant donnée, voir plus bas pour plus de détails
```

Le paramètre par défaut est utilisé dans deux et uniquement deux situations :

- Aucun paramètre n'est fourni
- Le paramèter *undefined* est fourni

Autrement dit, si vous passez *null* le paramètre par défaut **ne sera pas appliqué**.

> **Note :** Un assignement de valeur par défaut peut être utilisé avec des paramètres déstructurés également (voyez la notion suivante pour avoir un exemple).

#### External resource

- [Default parameter value - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Valeurs par défaut des arguments - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Fonctions/Valeurs_par_d%C3%A9faut_des_arguments)

### Déstructurer des objets et des tableaux

La *déstructuration* un moyen pratique de créer de nouvelles variables en extrayant des valeurs des données enregistrées dans des objets ou des tableaux.

Pour nommer quelque cas d'utilisation, la *déstructuration* peut être utilisée pour déstructurer des paramètres de fonction ou *this.props* dans des projets React par exemple.

#### Explication avec du code

- Objet

Prenons l'objet suivant pour tous les exemples

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

Sans déstructuration :

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

Avec la déstructuration, tout en une ligne :

```js
const { firstName: first, age, city = "Paris" } = person; // Et voilà !

console.log(age) // 35 -- Une nouvelle variable age est créée et est égale à person.age
console.log(first) // "Nick" -- Une nouvelle variable first est créée et est égale à person.firstName
console.log(firstName) // ReferenceError -- person.firstName existe MAIS la nouvelle variable créée est nommée first
console.log(city) // "Paris" -- Une nouvelle variable city est créée et comme person.city n'est pas défini, city est égal à la valeur par défaut donnée, à savoir "Paris"
```

**Note :** Dans ```const { age } = person;```, les accolades après le mot-clé *const* ne sont pas utilisées pour déclarer un objet ou un bloc, mais font partie de la syntaxe de *déstructuration*.

- Paramètres de fonction

La *destructuring* est souvent utilisée pour déstructurer les paramètres de fonction sous la forme d'objets.

Sans déstructuration :

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

En déstructurant le paramètre objet *person*, nous obtenons une fonction plus concise :

```js
function joinFirstLastName({ firstName, lastName }) { // nous crééons les variables firstName et lastName en déstructurant le paramètre person
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

La déstructuration est encore plus agréable à utiliser avec les [fonctions fléchées](#arrow_func_concept) :

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```

- Tableau

Utilisons le tableau suivant :

```js
const myArray = ["a", "b", "c"];
```

Sans la destructuration :

```js
const x = myArray[0];
const y = myArray[1];
```

Avec :

```js
const [x, y] = myArray; // Et voilà !

console.log(x) // "a"
console.log(y) // "b"
```

#### Ressources utiles

- [ES6 Features - Destructuring Assignment](http://es6-features.org/#ArrayMatching)
- [Destructuring Objects - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destructuring](http://exploringjs.com/es6/ch_destructuring.html)

### Méthodes de tableau : map / filter / reduce

*Map*, *filter* et *reduce* sont des méthodes de tableau qui viennent avec un paradigme de programmation appelé la [*programmation fonctionnelle*](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0).

Pour résumer :

- **Array.prototype.map()** prend un tableau, fait quelque chose sur ses éléments et retourne un tableau contenant les éléments transformés.
- **Array.prototype.filter()** prend un tableau, décide élément par élément s'il faut le garder ou non et retourne un tableau contenant uniquement les éléments conservés.
- **Array.prototype.reduce()** prend un tableau et agrège ses éléments en une seule valeur (qui est retournée).

Je recommande de les utiliser autant que possibles pour suivre les principes de la programmation fonctionelle car ils sont composables, concis et élégants.

Avec toutes ces méthodes, vous pouvez éviter l'utilisation des boucles *for* et *forEach* dans la plupart des situations. Vous pouvez avoir de la peine au début à les utiliser car ils vous obligent à apprendre une nouvelle façon de penser, mais une fois que vous avez compris comment cela fonctionne tout devient plus facile.

#### Code d'exemple

```js
const numbers = [0, 1, 2, 3, 4, 5, 6];
const doubledNumbers = numbers.map(n => n * 2); // [0, 2, 4, 6, 8, 10, 12]
const evenNumbers = numbers.filter(n => n % 2 === 0); // [0, 2, 4, 6]
const sum = numbers.reduce((prev, next) => prev + next, 0); // 21
```

Calculer la somme des notes (```grades```) des étudiants ayant eu plus que 10 en utilisant map, filter et reduce :
```js
const students = [
  { name: "Nick", grade: 10 },
  { name: "John", grade: 15 },
  { name: "Julia", grade: 19 },
  { name: "Nathalie", grade: 9 },
];

const aboveTenSum = students
  .map(student => student.grade) // nous transformons le tableau students en un tableau contenant leurs notes
  .filter(grade => grade >= 10) // nous filtrons le tableau des notes pour ne conserver que celles supérieures ou égales à 10
  .reduce((prev, next) => prev + next, 0); // nous additionnons toutes les notes au dessus de 10 une par une

console.log(aboveTenSum) // 44 -- 10 (Nick) + 15 (John) + 19 (Julia), Nathalie étant ignorée car sa note est inférieure à 10
```

#### Explication

Prenons le tableau de nombres pour nos exemples :

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

Que se passe-t-il ici ? Nous utilisons .map sur le tableau *numbers*, le map itère sur chaque élément du tableau et le passe à notre fonction. Le but de la fonction est de produire et de retourner une nouvelle valeur pour chaque valeur donnée pour que le map puisse la remplacer.

Extrayons cette fonction pour la rendre plus claire, juste pour cette fois-ci :

```js
const doubleN = function(n) { return n * 2; };
const doubledNumbers = numbers.map(doubleN);
console.log(doubledNumbers); // [0, 2, 4, 6, 8, 10, 12]
```

```numbers.map(doubleN)``` produit ```[doubleN(0), doubleN(1), doubleN(2), doubleN(3), doubleN(4), doubleN(5), doubleN(6)]``` ce qui est égal à ```[0, 2, 4, 6, 8, 10, 12]```.

> **Note :** Si vous n'avez pas besoin d'un nouveau tableau et que vous voulant juste avoir une boucle ayant des effets secondaires, vous pourriez juste avoir besoin d'une boucle for / forEach à la place d'un map.

##### Array.prototype.filter()

```js
const evenNumbers = numbers.filter(function(n) {
  return n % 2 === 0; // true si "n" est pair, false si "n" est impair
});
console.log(evenNumbers); // [0, 2, 4, 6]
```

Nous utilisons .filter sur le tableau *numbers* : filter itère sur chaque élément du tableau et le passe à notre fonction. Le but de la fonction est de retourner un booléen qui déterminera si la valeur actuelle sera conservée. Filter retourne ensuite le tableau avec uniquement les valeurs conservées.

##### Array.prototype.reduce()

Le but de la méthode reduce est de réduire tous les éléments du tableau sur lequel elle itère à une seule valeur. Vous décidez de la manière dont les éléments sont agrégés.

```js
const sum = numbers.reduce(
  function(acc, n) {
    return acc + n;
  },
  0 // valeur de l'accumulateur à la première itération
);

console.log(sum) //21
```

Tout comme pour les méthodes .map et .filter, .reduce est appliqué sur un tableau et prend une fonction en premier paramètre.

Cette fois cependant, il y a des changements :

- .reduce prend deux paramètres

Le premier paramètre est une fonction qui sera appelée à chaque étape d'itéraiton.

Le second paramètre est la valeur de la variable d'accumulation (*acc* ici) à la première étape d'itération (lisez le point suivant pour comprendre).

- Paramèters de fonction

La fonction que vous passez comme premier paramètre de .reduce prend deux paramètres. Le premier (*acc* ici) est la variable d'accumulateur, tandis que le second paramètre (*n*) est l'élément actuel.

La variable d'accumulateur est égale à la valeur retournée par votre fonction à l'étape d'itération **précédente**. À la première étape de l'itération, *acc* est égale à la valeur que vous avez passé au second paramètre de .reduce.

###### À la première étape d'itération

```acc = 0``` car nous avons passé 0 comme second paramètre à reduce.

```n = 0``` premier élément du tableau *number*

La fonction retourne *acc* + *n* --> 0 + 0 --> 0

###### À la deuxième étape d'itération

```acc = 0``` car c'est la valeur retournée par la fonction à l'étape d'itération précédente

```n = 1``` deuxième élément du tableau *number*

La fonction retourne *acc* + *n* --> 0 + 1 --> 1

###### À la troisième étape d'itération

```acc = 1``` car c'est la valeur retournée par la fonction à l'étape d'itération précédente

```n = 2``` troisième élément du tableau *number*

La fonction retourne *acc* + *n* --> 1 + 2 --> 3

###### À la quatrième étape d'itération

```acc = 3``` car c'est la valeur retournée par la fonction à l'étape d'itération précédente

```n = 3``` quatrième élément du tableau *number*

La fonction retourne *acc* + *n* --> 3 + 3 --> 6

###### [...] À la dernière étape d'itération

```acc = 15``` car c'est la valeur retournée par la fonction à l'étape d'itération précédente

```n = 6``` dernier élément du tableau *number*

La fonction retourne *acc* + *n* --> 15 + 6 --> 21

Comme c'est la dernière étape d'itération, **.reduce** retourne 21.

#### Ressource externe

- [Understanding map / filter / reduce in JS](https://hackernoon.com/understanding-map-filter-and-reduce-in-javascript-5df1c7eee464)

### Opérateur de décomposition "..."

L'opérateur de décomposition ```...``` existe depuis ES2015 et est utilisé pour décomposer les éléments d'un itérable (comme un tableau) dans des emplacements qui peuvent contenir plusieurs éléments.

#### Code d'exemple

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

#### Explication

##### Dans des tableaux (comme des tableaux)

Si nous avons les deux tableaux suivants :

```js
const arr1 = ["a", "b", "c"];
const arr2 = [arr1, "d", "e", "f"]; // [["a", "b", "c"], "d", "e", "f"]
```

Le premier élément d'*arr2* est un tableau, car *arr1* est injecté tel quel dans *arr2*. Cependant, nous voulons que *arr2* soit un tableau de lettres. Pour ce faire, nous pouvons *décomposer* les éléments d'*arr1* dans *arr2*.

Avec l'opérateur de décomposition :

```js
const arr1 = ["a", "b", "c"];
const arr2 = [...arr1, "d", "e", "f"]; // ["a", "b", "c", "d", "e", "f"]
```

##### Paramètre de reste d'une fonction

Dans les paramètres d'une fonction, nous pouvons utiliser l'opérateur de reste pour injecter les paramètres dans un tableau dans lequel nous pouvons faire une bocle. Il existe déjà un objet **arguments** lié à chaque fonction, qui est un tableau contenant tous les paramètres passés à la fonction.

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

Mais imaginons que nous voulons que cette fonction créée un nouvel édudiant avec ses notes et sa note moyenne. Ne serait-il pas plus pratique d'extraire les deux premiers paramètres dans deux variables séparées, et d'avoir les notes dans un tableau sur lequel nous pourrions effectuer une boucle ?

C'est exactement ce que l'opérateur de reste nous permet de faire !

```js
function createStudent(firstName, lastName, ...grades) {
  // firstName = "Nick"
  // lastName = "Anderson"
  // [10, 12, 6] -- "..." prend tous les autres paramètres passés, créée une variable grades qui contient un tableau contenant les paramètres

  const avgGrade = grades.reduce((acc, curr) => acc + curr, 0) / grades.length; // calculer la note moyenne à partir des notes

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

> **Note :** la fonction createStudent est mauvaise car nous ne vérifions pas si grades.length existe ou est différent de 0. Cependant, je n'ai pas prévu ce cas pour rendre l'exemple plus facile à lire.

##### Décomposition des propriétés d'un objet

Pour celui-ci, je vous recommande de lire les explications précédentes concernant l'opérateur de reste sur les itérables et les paramètres de fonction auparavant.

```js
const myObj = { x: 1, y: 2, a: 3, b: 4 };
const { x, y, ...z } = myObj; // l'objet est déstructuré ici
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

// z est le reste de l'objet déstructuré : c'est myObj sans les propriétés x et y qui ont été déstructurées

const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }

// Ici, les propriétés de l'objet z sont étendues dans n
```

#### Ressources externes

- [TC39 - Object rest/spread](https://github.com/tc39/proposal-object-rest-spread)
- [Spread operator introduction - WesBos](https://github.com/wesbos/es6-articles/blob/master/28%20-%20Spread%20Operator%20Introduction.md)
- [JavaScript & the spread operator](https://codeburst.io/javascript-the-spread-operator-a867a71668ca)
- [6 Great uses of the spread operator](https://davidwalsh.name/spread-operator)

### Raccourci pour les propriétés d'objet

Lorsque l'on assigne une variable à la propriété d'un objet, si le nom de la variable est le même que le nom de la propriété, vous pouvez faire la chose suivante :

```js
const x = 10;
const myObj = { x };
console.log(myObj.x) // 10
```

#### Explication

D'habitude (avant ES2015), lorsque l'on déclare un *litéral d'objet* et que l'on veut utiliser des variables comme propriétés de l'objet, on écrit ce genre de code :

```js
const x = 10;
const y = 20;

const myObj = {
  x: x, // on assigne le contenu de la variable x à myObj.x
  y: y // on assigne le contenu de la variable y à myObj.y
};

console.log(myObj.x) // 10
console.log(myObj.y) // 20
```

Comme vous pouvez le voir, c'est assez répétitif car les noms des propriétés de myObj sont identiques aux noms des variables que vous voulez assigner à ces propriétés.

Avec ES2015, quand le nom de la variable est identique au nom de la propriété, vous pouvez utiliser ce raccourci :

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

#### Ressources externes

- [Property shorthand - ES6 Features](http://es6-features.org/#PropertyShorthand)

### Promesses

Une promesse est un objet qui peut être retourné de manière synchrone depuis une fonction asynchrone ([ref](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261#3cd0)).

Les promesses peuvent être utilisées pour éviter un [enfer de callbacks](http://callbackhell.com/), et elles sont rencontrées de plus en plus fréquemment dans les projets JavaScript modernes.

#### Code d'exemple

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

#### Explication

Quand vous faites une *requête AJAX*, la réponse n'est pas synchrone car vous voulez une ressource qui prend du temps à venir. Elle ne pourriat même jamais arriver si la ressource que vous avez demandée est indisponible pour une raison quelconque (404).

Pour gérer ce type de situations, ES2015 nous a offert les *promesses*. Les promesses peuvent avoir trois états différents :

- En attente
- Complété
- Rejeté

Imagions que nous voulions utiliser les promesses pour gérer une requête AJAX pour récupérer la ressource *X*.

##### Créer la promesse

Nous allons commencer par crééer une promesse. Nous allons utiliser la méthode ```$.get()``` de jQuery pour faire notre requête AJAX vers *X*.

```js
const xFetcherPromise = new Promise( // Créer une promesse avec le mot-clé new et la stocker dans une variable
  function(resolve, reject) { // Le constructeur de Promise prend une fonction comme paramètre qui a elle-même deux paramètres, resolve et reject
    $.get("X") // Démarrer la requête AJAX
      .done(function(X) { // Quand la requête est terminée...
        resolve(X); // ...résoudre la promesse avec la valeur X comme paramètre
      })
      .fail(function(error) { // Si la requête a échoué...
        reject(error); // ...rejeter la promesse avec l'erreur comme paramètre
      });
  }
)
```

Comme vu dans l'exemple ci-dessus, l'objet Promise prend une fonction *exécuteur* qui prend les deux paramètres **resolve** et **reject**. Ces paramètres sont des fonctions qui lorsqu'elles sont appelées, vont modifier l'état de la promesse d'*en attente* à respectivement l'état *complété* et *résolu*.

La promesse est dans l'état *en attente* à sa création et sa fonction *éxécuteur* est appelée immédiatement. Quand une des deux fonctions *resolve* ou *reject* est appelée depuis la fonction *éxécuteur*, la promesse appelera les déclencheurs associés.

##### Utilisation des déclencheurs de promesse

Pour obtenir le résultat (ou l'erreur) de la promesse, nous devons y attacher des déclencheurs en faisant la chose suivante :

```js
xFetcherPromise
  .then(function(X) {
    console.log(X);
  })
  .catch(function(err) {
    console.log(err)
  })
```

Si la promesse réussit, ```resolve()``` sera exécuté et la fonction passée à ```.then``` est appelée.

Si elle échoue, ```reject()``` sera exécuté et la fonction passée à ```.catch``` est appelée.

> **Note : ** Si la promesse a déjà été accomplie ou rejetée lorsqu'un déclencheur y est attaché, le déclencheur sera appelé, afin de ne pas avoir une course entre une opération asynchrone se complétant et ses déclencheurs s'y faisant attacher [(référence: MDN)](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Promise#Description).

#### Ressources externes

- [JavaScript Promises for dummies - Jecelyn Yeen](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [JavaScript Promise API - David Walsh](https://davidwalsh.name/promises)
- [Utiliser les promesses - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Utiliser_les_promesses)
- [What is a promise - Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- [JavaScript Promises: an Introduction - Jake Archibald](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
- [Documentation sur l'objet Promise - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Promise)

### Littéraux de modèle

Les littéraux de modèle (*template literals*) sont une [*interpolation d'expression*](https://en.wikipedia.org/wiki/String_interpolation) pour les chaînes de caractère d'une ligne ou multilignes.

Autrement dit, c'est une nouvelle syntaxe de chaîne de caractère qui est particulièrement pratique pour y utiliser des expressions JavaScript (des variables, par exemple).

#### Code d'exemple

```js
const name = "Nick";
`Bonjour ${name}, l'expression suivante vaut 4 : ${2+2}`;

// Bonjour Nick, l'expression suivante vaut 4 : 4
```

#### Ressources externes

- [String interpolation - ES6 Features](http://es6-features.org/#StringInterpolation)
- [ES6 Template Strings - Addy Osmani](https://developers.google.com/web/updates/2015/01/ES6-Template-Strings)

### Littéraux de modèle étiquetés

Les étiquettes de modèle sont des *fonctions qui peuvent être préfixées à un [littéral de modèle](#litteraux-de-modele)*.  Quand une fonction est appelée ainsi, le premier paramètre est un tableau des *chaînes de caractère* qui apparaissent entre les variables interpolées du modèle, et les paramètres suivants sont les valeurs interpolées. Vous pouuvez utiliser l'opérateur de décomposition `...` pour les récupérer. [(Références: MDN)](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Litt%C3%A9raux_gabarits#Les_littéraux_de_modèle_étiquetés).

> **Note :** Certaines librairies, comme [styled-components](https://www.styled-components.com/), se basent entièrement sur cette fonctionnalité.

Voici un petit exemple de leur fonctionnement :
```js
function highlight(strings, ...values) {
  const interpolation = strings.reduce((prev, current) => {
    return prev + current + (values.length ? "<mark>" + values.shift() + "</mark>" : "");
  }, "");

  return interpolation;
}

const condiment = "confiture";
const meal = "toast";

highlight`J'aime mettre de la ${condiment} sur mon ${meal}.`;
// "J'aime mettre de la <mark>confiture</mark> sur mon <mark>toast</mark>."
```

Un autre exemple plus intéressant :
```js
function comma(strings, ...values) {
  return strings.reduce((prev, next) => {
    let value = values.shift() || [];
    value = value.join(", ");
    return prev + next + value;
  }, "");
}

const snacks = ['pommes', 'bananes', 'cerises'];
comma`J'aime grignoter des ${snacks}.`;
// "J'aime grignoter des pommes, bananes, cerises."
```

#### Ressources externes
- [Wes Bos on Tagged Template Literals](http://wesbos.com/tagged-template-literals/)
- [Library of common template tags](https://github.com/declandewet/common-tags)

### Imports / exports

Les modules ES6 sont utilisés pour accéder à des variables et à des fonctions explicitement exportées depuis les modules importés.

Je vous recommande de regardes la documentation sur MDN concernant import/export (voir les ressources externes plus bas), elles sont à la fois simples et complètes.

#### Explication avec un code d'exemple

##### Exports nommés

Les exports nommés sont utilisés pour exporter plusieurs valeurs d'un module.

> **Note :** Vous ne pouvez exporter avec un nom que des [objets de première classe](https://fr.wikipedia.org/wiki/Objet_de_premi%C3%A8re_classe) qui ont un nom.

```js
// mathConstants.js
export const pi = 3.14;
export const exp = 2.7;
export const alpha = 0.35;

// -------------

// myFile.js
import { pi, exp } from './mathConstants.js'; // Import nommé -- syntaxe ressemblant à la destructuration
console.log(pi) // 3.14
console.log(exp) // 2.7

// -------------

// mySecondFile.js
import * as constants from './mathConstants.js'; // Injecter toutes les valeurs exportées dans la variable constants
console.log(constants.pi) // 3.14
console.log(constants.exp) // 2.7
```

Bien que les imports nommés ressemblent à une *destructuration*, ils ont une syntaxe différente et ne sont pas identiques. Ils ne supportent ni les valeurs par défaut ni la destructuration *profonde*.

De plus, vous pouvez créer des alias mais la syntaxe est différente de celle utilisée avec la destructuration :

```js
import { foo as bar } from 'myFile.js'; // foo est importé et injecté dans une nouvelle variable bar
```

##### Import/export par défaut

Concernant l'export par défaut, il ne peut y en avoir qu'un seul par module. Un export par défaut peut être une fonction, une classe, un objet, ou quoi que ce soit d'autre. Cette valeur est considérée comme étant la valeur exportée "principale" car elle sera la plus simple à importer.
Concerning the default export, there is only a single default export per module. A default export can be a function, a class, an object or anything else. This value is considered the "main" exported value since it will be the simplest to import. [Référence: MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Instructions/export#Description)

```js
// coolNumber.js
const ultimateNumber = 42;
export default ultimateNumber;

// ------------

// myFile.js
import number from './coolNumber.js';
// L'export par défaut, peu importe son nom, est automatiquement injecté dans la variable number
console.log(number) // 42
```

Exporter une fonction :

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

#### Ressources externes

- [ES6 Modules in bulletpoints](https://ponyfoo.com/articles/es6#modules)
- [Export - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
- [Import - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Understanding ES6 Modules](https://www.sitepoint.com/understanding-es6-modules/)
- [Destructuring special case - import statements](https://ponyfoo.com/articles/es6-destructuring-in-depth#special-case-import-statements)
- [Misunderstanding ES6 Modules - Kent C. Dodds](https://medium.com/@kentcdodds/misunderstanding-es6-modules-upgrading-babel-tears-and-a-solution-ad2d5ab93ce0)
- [Modules in JavaScript](http://exploringjs.com/es6/ch_modules.html#sec_modules-in-javascript)

### <a name="this_def"></a> *this* en JavaScript

L'opérateur *this* se comporte différemment que dans d'autres langages et est dans la plupart des cas déterminé par la manière dont une fonction est appelée. ([Ref: MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Op%C3%A9rateurs/L_op%C3%A9rateur_this)).

Cette notion a beaucoup de subtilités et comme elle est assez complexe, je vous recommande donc fortement de lire avec attention les ressources externes ci-dessous. Par conséquent, je vais utiliser l’idée personnelle que j’ai en tête pour déterminer ce qu’est *this*. J’ai appris cette astuce de [cet article écrit par Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/).

```js
function myFunc() {
  ...
}

// Après chaque ligne, vous trouverez la valeur de *this* dans myFunc

myFunc.call("myString", "hello") // "myString" -- la valeur du premier paramètre de .call est injectée dans *this*

// En mode non-strict
myFunc("hello") // window -- myFunc() est un sucre syntaxique pour myFunc.call(window, "hello")

// En mode strict
myFunc("hello") // undefined -- myFunc() est un sucre syntaxique pour myFunc.call(undefined, "hello")
```

```js
var person = {
  myFunc: function() { ... }
}

person.myFunc.call(person, "test") // objet person -- le premier paramètre de call est injecté dans *this*
person.myFunc("test") // objet person -- person.myFunc() est un sucre syntaxique pour person.myFunc.call(person, "test")

var myBoundFunc = person.myFunc.bind("hello") // Créée une nouvelle fonction dans laquelle nous injectons “hello” comme valeur de *this*
person.myFunc("test") // objet Person -- La méthode bind n’a aucun effet sur la méthode originale
myBoundFunc("test") // "hello" -- myBoundFunc est person.myFunc avec “hello” comme valeur de *this*
```

#### Ressources externes

- [Understanding JavaScript Function Invocation and "this" - Yehuda Katz](http://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)
- [L’opérateur this - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Opérateurs/L_opérateur_this)

### Classe

JavaScript est un language [basé sur les prototypes](https://fr.wikipedia.org/wiki/Programmation_orientée_prototype) (alors que Java, par exemple, est [basé sur les classes]((https://en.wikipedia.org/wiki/Prototype-based_programming))). ES6 a introduit les classes JavaScript qui sont un sucre syntaxique pour de l’héritage et **non** un nouveau modèle d’héritage basé sur des classes 

JavaScript is a [prototype-based](https://en.wikipedia.org/wiki/Prototype-based_programming) language (whereas Java is [class-based](https://en.wikipedia.org/wiki/Class-based_programming) language, for instance). ES6 has introduced JavaScript classes which are meant to be a syntactic sugar for prototype-based inheritance and **not** a new class-based inheritance model ([référence : MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Classes)).

Le mot *classe* est évidemment source de confusion si vous êtes habitué aux classes dans d’autres langages. Dans ce cas, évitez de penser que les classes JavaScript fonctionnent de la même manière et considérez-les comme une notion totalement différente.

Comme ce document n’est pas fait pour vous apprendre le langage à partir de zéro, je vais partir du fait que vous savez déjà ce que sont les prototypes et comment ils se comportement. Dans le cas contraire, voyez les ressources externes listées en dessous des exemples.

#### Exemples

Avant ES6, la syntaxe de prototype :

```js
var Person = function(name, age) {
  this.name = name;
  this.age = age;
}
Person.prototype.stringSentence = function() {
  return "Hello, my name is " + this.name + " and I'm " + this.age;
}
```

Avec la syntaxe ES6 de classe :

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

#### Ressources externes

Pour comprendre les prototypes :

- [Understanding Prototypes in JS - Yehuda Katz](http://yehudakatz.com/2011/08/12/understanding-prototypes-in-javascript/)
- [A plain English guide to JS prototypes - Sebastian Porto](http://sporto.github.io/blog/2013/02/22/a-plain-english-guide-to-javascript-prototypes/)
- [Héritage et chaîne de prototypes - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Héritage_et_chaîne_de_prototypes)

Pour comprendre les classes

- [ES6 Classes in Depth - Nicolas Bevacqua](https://ponyfoo.com/articles/es6-classes-in-depth)
- [ES6 Features - Classes](http://es6-features.org/#ClassDefinition)
- [Classes - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Classes)

### Mots clés `extends` et `super`

Le mot-clé `extends` est utilisé dans les déclarations de classe ou les expressions de classe pour créer une classe qui est une fille d’une autre classe ([référence: MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Classes/extends)). La sous-classe hérite de toutes les propriétés de la classe supérieure et peut aussi ajouter de nouvelles propriétés ou modifier celles héritées.

Le mot-clé `super` est utilisé pour appeler des fonctions sur le parent d’un objet, y compris son constructeur.

- Le mot-clé `super` doit être utilisé avant que le mot-clé `this` soit utilisé dans le constructeur
- Invoquer `super()` appelle le constructeur de la classe parente. Si vous voulez passer des arguments au constructeur de la classe parente, vous pouvez l’appeler avec `super(arguments)`.
- Si la classe parente a une méthode (même statique) appelée `X`, vous pouvez utiliser `super.X()` pour l’appeler depuis la classe fille.

#### Code d’exemple

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
    // Ici, le constructeur de la classe parente est appelé avec
    // les longueurs données pour la hauteur et largeur du Polygon
    super(length, length);
    // Note : dans les classes dérivées, super() doit être appelé avant que vous ne
    // puissiez utiliser 'this'. Ne pas respecter cette règle causera une ReferenceError.
    this.name = 'Square';
    this.length = length;
  }

  getCustomHelloPhrase() {
    const polygonPhrase = super.getHelloPhrase(); // accéder à une méthode de la classe parente avec la syntaxe super.X()
    return `${polygonPhrase} with a length of ${this.length}`;
  }

  get area() {
    return this.height * this.width;
  }
}

const mySquare = new Square(10);
console.log(mySquare.area) // 100
console.log(mySquare.getHelloPhrase()) // 'Hi, I am a Square' -- Square hérite de Polygon et a accès à ses méthodes
console.log(mySquare.getCustomHelloPhrase()) // 'Hi, I am a Square with a length of 10'
```

**Note :** Si nous avions essayé d’utiliser `this`avant d’appeler `super()` dans la classe Square, une ReferenceError aurait été déclenchée :

```js
class Square extends Polygon {
  constructor(length) {
    this.height; // ReferenceError, super doit être appelé d’abord !

    // Ici, le constructeur de la classe parente est appelé avec
    // les longueurs données pour la hauteur et largeur du Polygon
    super(length, length);
    
    // Note : dans les classes dérivées, super() doit être appelé avant que vous ne
    // puissiez utiliser 'this'. Ne pas respecter cette règle causera une ReferenceError.
    this.name = 'Square';
  }
}
```

#### Ressources

- [extends - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Classes/extends)
- [super - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Opérateurs/super)
- [L’héritage au sein de JavaScript - MDN](https://developer.mozilla.org/fr/docs/Learn/JavaScript/Objects/Heritage)

### Async Await

En plus des [Promises](#promesses), il y a une nouvelle syntaxe que vous pourriez rencontrer pour gérer le code asynchrone nommée *async / await*.

Le but des fonctions async/await est de simplifier le comportement de l’utilisation des promesses de manière synchrone et d’exécuter un comportemnet sur un groupe de promesses. Tout comme les promesses sont similaires aux callbacks structurés, asnyc/await est similaire à la combinaison de générateurs et de promesses. Les fonctions asynchrones renvoient *toujours* une Promise. ([référence: MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Instructions/async_function))

> **Note :** Vous devez comprendre ce que sont les promesses et comment elles fonctionnent avant d’essayer de comprendre async/await car elles dépendent dessus.

> **Note 2:** [*await* doit être utilisé dans une fonction *async*](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9#f3f0), ce qui signifie que vous ne pouvez pas utiliser await dans le premier niveau de votre code car ce n’est pas une fonction async.

#### Code d’exemple

```js
async function getGithubUser(username) { // le mot-clé async autorise l’utilisation de await dans la fonction et signifie que la fonction retourne une promesse
  const response = await fetch(`https://api.github.com/users/${username}`); // L’exécution est mise en pause ici jusqu’à ce que la Promise retournée par fetch soit résolue
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user)) // afficher dans la console la réponse - on ne peut pas utiliser la syntaxe await car ce code n’est pas une fonction async
  .catch(err => console.log(err)); // si notre fonction async lève une erreur, nous la récupérons ici
```

#### Explication avec un code d’exemple

*Async / Await* fonctionnent avec les promises mais ils permettent d’utiliser un style de code plus impératif.

L’opérateur *async* marque une fonction comme étant asynchrone et retournera toujours une *Promise*. Vous pouvez utiliser l’opérateur *await* dans une fonction *async* pour mettre en pause l’exécution sur cette ligne jusqu’à ce que la promise retournée par l’expression se fasse résoudre ou rejeter.

```js
async function myFunc() {
  // nous pouvons utiliser l’opérateur await car cette fonction est asynchrone
  return "hello world";
}

myFunc().then(msg => console.log(msg)) // "hello world" -- la valeur de retour de myFunc se fait transformer en promesse à cause de l’opérateur async
```

Lorsque l’expression *return* d’une fonction async est atteint, la Promise est remplie avec la valeur retournée. Si une erreur est levée à l’intérieur de la fonction async, la l’état de la promesse passera à *rejeté*. Si aucune valeur n’est retournée par une fonction async, une promesse est quand même retournée et sera résolue sans valeur lorsque l’exécution de la fonction async est terminée.

L’opérateur *await* est utilisé pour attendre qu’une primesse se fasse résoudre et ne peut être utilisé qu’à l’intérieur du corps d’une fonction async. Lorsqu’il est rencontré, l’exécution du code est mise en pause jusqu’à ce que la promise se fasse résoudre.

> **Note :** *fetch* est une fonction qui retourne une Promise qui nous permet de faire une requête AJAX

Voyons d’abord comment nous pourrions récupérer un utilisateur sur GitHub avec des promesses.

```js
function getGithubUser(username) {
  return fetch(`https://api.github.com/users/${username}`).then(response => response.json());
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

Voici l’équivalent avec async/await

```js
async function getGithubUser(username) { // utilisation d’une promesse + du mot-clé await autorisé
  const response = await fetch(`https://api.github.com/users/${username}`); // L’exécution s’arrête ici jusqu’à ce que la promesse fetch soit résolue
  return response.json();
}

getGithubUser('mbeaudru')
  .then(user => console.log(user))
  .catch(err => console.log(err));
```

La syntaxe *async/await* est particulièrement utile lorsque vous avez besoin d’enchaîner des promesses qui sont mutuellement dépendantes.

Par exemple, si vous avez besoin d’obtenir un jeton d’accps pour pouvoir récupérer un post de blog sur une base de données puis les informations sur l’auteur :

> **Note :** les expressions *await* ont besoin d’êtres entourées de parenthèses pour appeler leur valeur résolue et leurs propriétés sur la même ligne.

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

##### Gestion d’erreur

À moins d’ajouter des blocs *try / catch* autour des expressions *await*, les exceptions non gérées – peu importe de si elles ont été levées dans le corps de votre fonction *async* ou lorsque le code est en pause pendant *await* – vont rejeter la promesse retournée par la fonction *async*. Utiliser l’expression `thrown` dans une fonction asynchrone donne le même résultat que retourner une promesse qui se fait rejeter [(référence : PonyFoo)](https://ponyfoo.com/articles/understanding-javascript-async-await#error-handling).

> **Note :** Les promesses se comportent de la même manière !

Avec les promesses, voici comment on gérerait la chaîne d’erreur :

```js
function getUser() { // Cette promesse se fera rejeter !
  return new Promise((res, rej) => rej("Utilisateur non trouvé !"));
}

function getAvatarByUsername(userId) {
  return getUser(userId).then(user => user.avatar);
}

function getUserAvatar(username) {
  return getAvatarByUsername(username).then(avatar => ({ username, avatar }));
}

getUserAvatar('mbeaudru')
  .then(res => console.log(res))
  .catch(err => console.log(err)); // "Utilisateur non trouvé !"
```

Équivalent avec *async / await*:

```js
async function getUser() { // La promesse retournée se fera rejeter
  throw "Utilisateur non trouvé !";
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
  .catch(err => console.log(err)); // "Utilisateur non trouvé !"
```

#### Ressources externes

- [Async/Await - JavaScript.Info](https://javascript.info/async-await)
- [ES7 Async/Await](http://rossboucher.com/await/#/)
- [6 Reasons Why JavaScript’s Async/Await Blows Promises Away](https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9)
- [JavaScript awaits](https://dev.to/kayis/javascript-awaits)
- [Using Async Await in Express with Node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)
- [Async Function](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/async_function)
- [Await](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/await)
- [Using async / await in express with node 8](https://medium.com/@Abazhenov/using-async-await-in-express-with-node-8-b8af872c0016)

### Vérité / fausseté

En JavaScript, une valeur `truthy` ou `falsy` est une valeur qui se fait caster en un booléen lorsqu’elle est évaluée dans un contexte booléen. Un exemple de contexte booléen serait l’évaluation d’une condition ```if```.

Chaque valeur sera transformée en ```true```, à part si elles sont égales à :

- ```false```
- ```0```
- ```""``` (chaîne de caractères vide)
- ```null```
- ```undefined```
- ```NaN```

Voici des exemples de *contexte booléen* :

- Évaluation de condition ```if```

```js
if (myVar) {}
```

```myVar``` peut être n’importe quel [objets de première classe](https://fr.wikipedia.org/wiki/Objet_de_premi%C3%A8re_classe) (variable, fonction, booléen) mais il sera transformé en booléen car il est évalué dans un contexte booléen.

- Après l’opérateur logique **NOT** ```!```

Cet opérateur retourne ```false``` si son opérande peut être converti à ```true``` ; dans le cas contraire, il retourne ```true```

```js
!0 // true -- 0 est falsy, donc retourne true
!!0 // false -- 0 est falsy, donc !0 retourne true, et donc !(!0) retourne false
!!"" // false -- une chaîne vide est falsy donc NOT (NOT false) est égal à false
```

- Avec le constructeur d’objet *Boolean*

```js
new Boolean(0) // false
new Boolean(1) // true
```

- Dans une expression ternaire

```js
myVar ? "truthy" : "falsy"
```

myVar se fait évaluer dans un contexte booléen.

#### Ressources externes

- [Truthy (MDN)](https://developer.mozilla.org/fr/docs/Glossary/Truthy)
- [Falsy (MDN)](https://developer.mozilla.org/fr/docs/Glossary/Falsy)
- [Truthy and Falsy values in JS - Josh Clanton](http://adripofjavascript.com/blog/drips/truthy-and-falsy-values-in-javascript.html)

### Méthodes statiques

#### Explication courte

Le mot-clé `static` est utilisé dans les classes pour déclarer des méthodes statiques. Les méthodes statiques sont des fonctions dans une classe qui appartiennent à l’objet classe et ne sont pas disponible dans les instances de la classe.

#### Code d’exemple

```js
class Repo {
  static getName() {
    return "Le nom du repo est modern-js-cheatsheet"
  }
}

// Notez que nous n’avons pas créé d’instance de la classe Repo
console.log(Repo.getName()) // "Le nom du repo est modern-js-cheatsheet"

let r = new Repo();
console.log(r.getName()) // Uncaught TypeError: repo.getName is not a function
```

#### Explication détaillée

Les méthodes statiques peuvent être appelées à l’intérieur d’une autre méthode statique en utilisant le mot-clé `this`. Ceci ne fonctionne pas avec les méthodes non statiques, qui ne peuvent pas y accéder directement en utilisant le mot-clé `this`.

##### Appeler d’autres méthodes statiques depuis une méthode statique

Pour appeler une méthode statique depuis une autre méthode statique, le mot-clé `this` peut être utilisé comme ceci :

```js
class Repo {
  static getName() {
    return "Le nom du repo est modern-js-cheatsheet"
  }

  static modifyName(){
    return this.getName() + '-ajout'
  }
}

console.log(Repo.modifyName()) // Le nom du repo est modern-js-cheatsheet-ajout
```

##### Appeler des méthodes statiques depuis des méthodes non statiques

Les méthodes non statiques peuvent appeler des méthodes statiques de deux façons :
1. ###### En utilisant le nom de la classe

Pour accéder à une méthode statique depuis une méthode non statique, nous pouvons utiliser le nom de la classe et appeler la méthode statique comme une propriété, par exemple `NomClasse.NomMethodeStatique()`

```js
class Repo {
  static getName() {
    return "Le nom du repo est modern-js-cheatsheet"
  }

  useName() {
    return Repo.getName() + ' et il contient des trucs vraiment importants'
  }
}

// Nous devons instancier la classe pour utiliser les méthodes non statiques
let r = new Repo()
console.log(r.useName()) // Le nom du repo est modern-js-cheatsheet et il contient des trucs vraiment importants
```

2. ###### Avec le constructeur

Les méthodes statiques peuvent être appelées en tant que propriétés sur l’objet constructor

```js
class Repo {
  static getName() {
    return "Repo name is modern-js-cheatsheet"
  }

  useName() {
    // Appelle la méthode statique comme une propriété du constructeur
    return this.constructor.getName() + ' et il contient des trucs vraiment importants'
  }
}

// Nous devons instancier la classe pour utiliser les méthodes non statiques
let r = new Repo()
console.log(r.useName()) // Le nom du repo est modern-js-cheatsheet et il contient des trucs vraiment importants
```

#### Ressources externes
- [static - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Classes/static)
- [Static Methods - Javascript.info](https://javascript.info/class#static-methods)
- [Static Members in ES6 - OdeToCode](http://odetocode.com/blogs/scott/archive/2015/02/02/static-members-in-es6.aspx)

## Glossaire

### <a name="scope_def"></a> Portée (*scope*)

Le contexte dans lequel les valeurs et expressions sont “visibles”, ou peuvent être référencées. Si une variable ou une autre expression n’est pas “dans la portée actuelle”, alors son utilisation ne sera pas possible.

Source : [MDN](https://developer.mozilla.org/fr/docs/Glossaire/Portée)

### <a name="mutation_def"></a> Mutation de variable

On dit d’une variable qu’elle a été *mutée* lorsque sa valeur initiale a été changée après coup.

```js
var myArray = [];
myArray.push("firstEl") // myArray s’est fait muter
```

Une variable est dite *immutable* si elle ne peut être mutée.

Vous pouvez lire [l’article Mutable de MDN](https://developer.mozilla.org/fr/docs/Glossary/Mutable) pour plus de détails.
