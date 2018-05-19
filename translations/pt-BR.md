# Cheatsheet de JavaScript Moderno

![Modern JavaScript cheatsheet](https://i.imgur.com/aexPxMb.png)
<small>Crédito da Imagem: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</small>

## Introdução

### Motivação

Esse documento é um conjunto de "cheatsheet" para javascript que você frequentemente encontrará em projetos modernos e na maioria de exemplos de códigos atuais.

Esse guia não tem a intenção de te ensinar Javascript do zero, mas sim ajudar desenvolvedores com conhecimentos básicos a se familiarizarem com códigos modernos.

Além disso, eu @mbeaudru ocasionalmente forneço dicas que podem ser discutidas, mas tomarei o cuidado de avisar quando eu fizer uma recomendação pessoal.

> **Nota:** Muito dos conceitos apresentados aqui vem de uma atualização do Javascript (ES2015, chamada também de ES6). Você pode achar as novas funcionalidades adicionadas nessa atualização [aqui](http://es6-features.org).

### Material Complementar

Se você estiver com dificuldades em entender alguma coisa, eu sugiro que você procure por respostas nos seguintes lugares:

- [MDN (Mozilla Developer Network)](https://developer.mozilla.org/fr/search?q=)
- [You don't know JS (livro)](https://github.com/getify/You-Dont-Know-JS)
- [ES6 Funcionalidades e exemplos](http://es6-features.org)
- [WesBos blog (ES6)](http://wesbos.com/category/es6/)
- [Reddit (JavaScript)](https://www.reddit.com/r/javascript/)
- [Google](https://www.google.com/) para encontrar blogs e recursos específicos

## Sumário

- [Modern JavaScript cheatsheet](#modern-javascript-cheatsheet)
  * [Introdução](#Introdução)
    + [Motivação](#Motivação)
    + [Material Complementar](#Material-Complementar)
  * [Tabela de Conteúdos](#Sumário)
  * [Noções](#Noções)
    + [Declaração de variáveis: var, const, let](#declaração-de-variáveis-var-const-let)
      - [Breve explicação](#breve-explicação)
      - [Exemplo](#exemplo)
      - [Explicação Detalhada](#explicação-detalhada)
      - [Material Complementar](#material-complementar)
    + [Função de Seta](#função-de-seta)
      - [Exemplo](#exemplo-de-codigo)
      - [Explicação Detalhada](#detailed-explanation-1)
        * [Concisão](#concisão)
        * [Referência *this*](#referência-this)
      - [Material Útil](#material-útil)
    + [Parametros padrão de uma Function](#parametros-padrão-de-uma-function)
      - [Material Complementar](#material-complementar)
    + [Desestruturação de objetos e arrays](#desestruturação-de-objetos-e-arrays)
      - [Explicação com exemplo de código](#explicação-com-exemplo-de-código)
      - [Material Útil](#material-útil-1)
    + [Metodos de lista - map / filter / reduce](#array-methods---map--filter--reduce)
      - [Exemplo](#sample-code-2)
      - [Explicação](#explanation)
        * [Array.prototype.map()](#arrayprototypemap)
        * [Array.prototype.filter()](#arrayprototypefilter)
        * [Array.prototype.reduce()](#arrayprototypereduce)
      - [Material Complementar](#external-resource)
    + [Spread operator "..."](#spread-operator-)
      - [Exemplo](#sample-code-3)
      - [Explicação](#explanation-1)
        * [Em interações (como arrays)](#in-iterables-like-array)
        * [Function rest parameter](#function-rest-parameter)
        * [Object properties spreading](#object-properties-spreading)
      - [Material Complementar](#external-resources)
    + [Object property shorthand](#object-property-shorthand)
      - [Explicação](#explanation-2)
      - [Material Complementar](#external-resources-1)
    + [Promises](#promises)
      - [Exemplo](#sample-code-4)
      - [Explicação](#explanation-3)
        * [Criando uma promise](#create-the-promise)
        * [Usando uma promise](#use-the-promise)
      - [External Resources](#external-resources)
    + [Template literals](#template-literals)
      - [Sample code](#sample-code-5)
      - [External resources](#external-resources-2)
    + [Imports / Exports](#imports--exports)
      - [Explanation with sample code](#explanation-with-sample-code-1)
      - [External resources](#external-resources-3)
    + [JavaScript *this*](#-javascript-this)
      - [External resources](#external-resources-4)
    + [Class](#class)
      - [Samples](#samples)
      - [External resources](#external-resources-5)
    + [Async Await](#async-await)
      - [Sample code](#sample-code-6)
      - [Explanation](#explanation-4)
      - [External resources](#external-resources-7)
  * [Glossary](#glossary)
    + [Scope](#-scope)
    + [Variable mutation](#-variable-mutation)

## Noções

### Declaração de variáveis: var, const, let

Em JavaScript, existem três palavras-chave disponíveis para declarar uma variável, e cada uma tem suas diferenças. São elas ```var```, ```let``` e ```const```.

#### Breve explicação

Variáveis declaradas com a palavra-chave ```const``` não podem ser reatribuídas, enquanto ```let``` e ```var``` podem.

Eu recomendo sempre declarar suas variáveis com ```const``` por padrão, e com ```let``` se você precisar *modifica-lo* ou reatribuí-lo mais tarde.

<table>
  <tr>
    <th></th>
    <th>Escopo</th>
    <th>Reatribuível</th>
    <th>Mutável</th>
   <th><a href="#tdz_sample">Zona Temporal Inoperante</a></th>
  </tr>
  <tr>
    <th>const</th>
    <td>Bloco</td>
    <td>Não</td>
    <td><a href="#const_mutable_sample">Sim</a></td>
    <td>Sim</td>
  </tr>
  <tr>
    <th>let</th>
    <td>Bloco</td>
    <td>Sim</td>
    <td>Sim</td>
    <td>Sim</td>
  </tr>
   <tr>
    <th>var</th>
    <td>Função</td>
    <td>Sim</td>
    <td>Sim</td>
    <td>Não</td>
  </tr>
</table>

#### Exemplo

```javascript
const person = "Nick";
person = "John" // Irá ocorrer um erro, person não pode ser reatribuída
```

```javascript
let person = "Nick";
person = "John";
console.log(person) // "John", a reatribuição é permitida com let
```

#### Explicação Detalhada

O [*escopo*](#scope_def) de uma variável grosseiramente significa "onde esta variável está disponível no código".

##### var

Variáveis declaradas com ```var``` são *função escopada*, significando que quando uma variável é criada em uma função, tudo naquela função pode acessar essa variável. Além disso, uma variável de *função escopada* criada em uma função não pode ser acessada fora desta função.

Eu recomendo que você imagine isso, como se uma variável *X escopada* significasse que essa variável era uma propriedade de X.

```javascript
function myFunction() {
  var myVar = "Nick";
  console.log(myVar); // "Nick" - myVar é acessível dentro da função.
}
console.log(myVar); // Lança um ReferenceError, myVar não está acessível fora da função.
```

Ainda focado na variável de escopo, aqui está um exemplo mais sutil:

```javascript
function myFunction() {
  var myVar = "Nick";
  if (true) {
    var myVar = "John";
    console.log(myVar); // "John"
    // na verdade, sendo myVar do escopo da função, nós simplesmente apagamos o valor anterior do myVar "Nick" para "John"
  }
  console.log(myVar); // "John" - veja como as instruções no bloco if afetaram esse valor
}
console.log(myVar); // Lança um ReferenceError, myVar não é acessível fora da função.
```

Além disso, variáveis declaradas *var* são movidas para o topo do escopo na execução. É o que chamamos de [içando a var](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting).

Esta parte do código:

```js
console.log(myVar) // undefined -- sem erro lançado
var myVar = 2;
```

é entendido na execução como:

```js
var myVar;
console.log(myVar) // undefined -- sem erro lançado
myVar = 2;
```

##### let

```var``` e ```let ``` são quase os mesmos, mas variáveis declaradas com ```let```

- são *escopado em bloco*
- **não** são acessíveis antes de serem atribuídas
- não podem ser re-declaradas no mesmo escopo

Vamos ver o impacto do escopo em bloco em nosso exemplo anterior:

```javascript
function myFunction() {
  let myVar = "Nick";
  if (true) {
    let myVar = "John";
    console.log(myVar); // "John"
    // na verdade, myVar sendo escopada em bloco, nós criamos uma nova variável myVar.
    // essa variável não é acessível fora do bloco e é totalmente independente
    // da primeira myVar criada !
  }
  console.log(myVar); // "Nick", veja como as instruções no bloco IF NÃO afetou este valor
}
console.log(myVar); // lançado um ReferenceError, myVar não é acessível fora da fucnção.
```

<a name="tdz_sample"></a> Agora, o que significa para as variáveis *let* (e *const*) não estarem acessíveis antes de serem atribuídas:

```js
console.log(myVar) // lança um ReferenceError !
let myVar = 2;
```

Em contraste com as variáveis *var*, se você tentar ler ou escrever em uma variável *let* ou *const* antes de serem atribuídos, um erro será gerado. Esse fenômeno é freqüentemente chamado [*Zona Temporal Inoperante*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_Dead_Zone_and_errors_with_let) ou *TDZ*.

> **Nota:** Tecnicamente, as declarações de *let* e *const* também estão sendo içadas, mas não a sua atribuição. Uma vez que elas são feitas para que elas não possam ser usados antes da atribuição, ela intuitivamente parece que não há içamento, mas existe. Saiba mais sobre isso [explicação muito detalhada aqui](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified) se quiser saber mais.

Além disso, você não pode re-declarar uma variável *let*:

```js
let myVar = 2;
let myVar = 3; // Retorna um SyntaxError
```

##### const

Variáveis declaradas ```const``` agem como variáveis *let*, mas elas não podem ser reatribuídas.

Para resumir, variáveis *const*:

- são *escopado em bloco*
- não são acessíveis antes de serem atribuídos
- não podem ser re-declaradas no mesmo escopo
- não podem ser reatribuídas

```js
const myVar = "Nick";
myVar = "John" // lança um erro, reatribuição não é permitido
```

```js
const myVar = "Nick";
const myVar = "John" // lança um erro, re-declaração não é permitida
```

<a name="const_mutable_sample"></a> Mas há uma sutileza : variáveis ```const``` não são [**imutáveis**](#mutation_def) ! Concretamente, Isto significa que variáveis *objetos* e *arrays* declaradas com ```const``` **podem** ser mutadas.

Para objetos:
```js
const person = {
  name: 'Nick'
};
person.name = 'John' // isto irá funcionar! A variável objeto person não é completamente reatribuída, mas mutada
console.log(person.name) // "John"
person = "Sandra" // lança um erro, porque a reatribuição não é permitida com variáveis declaradas com const
```

Para arrays:
```js
const person = [];
person.push('John'); // isto irá funcionar! A variável array person não é completamente reatribuída, mas mutada
console.log(person[0]) // "John"
person = ["Nick"] // lança um erro, porque a reatribuição não é permitida com variáveis declaradas com array
```

#### Material Complementar

- [Como let e const são escopados em JavaScript - WesBos](http://wesbos.com/javascript-scoping/)
- [Zona temporal Inoperante (TDZ) desmistificada](http://jsrocks.org/2015/01/temporal-dead-zone-tdz-demystified)

### <a name="função-de-seta"></a> Função de seta

A atualização do JavaScript ES6 introduziu *funções de seta*, que é outra maneira de declarar e usar funções. Aqui estão os benefícios que elas trazem:

- Mais conciso
- *this* é retirado dos arredores
- retorno implícito

#### Exemplo de código

- Concisão e retorno implícito

```js
function double(x) { return x * 2; } // Forma tradicional
console.log(double(2)) // 4
```

```js
const double = x => x * 2; // A mesma função escrita como uma função de seta com retorno implícito
console.log(double(2)) // 4
```

- Referência *this*

Em uma função de seta, *this* é igual ao valor *this* do contexto de execução envolvente. Basicamente, com as funções de seta, você não precisa fazer o truque "that/self = this" antes de chamar uma função dentro de uma função.

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(() => {
    this.myVar++;
    console.log(this.myVar) // 1
  }, 0);
}
```

#### Explicação detalhada

##### Concisão

As funções de seta são mais concisas do que as funções tradicionais em diversas maneiras. Vamos rever todos os casos possíveis:

- Retorno implícito VS explícito

Um **retorno explícito** é uma função em que a palavra-chave *return* é usada em seu corpo.

```js
  function double(x) {
    return x * 2; // esta função retorna explicitamente x * 2, a palavra-chave *retorno*  é usada
  }
```

Na maneira tradicional de escrever funções, o retorno sempre foi explícito. Mas com funções de seta, você pode fazer *retorno implícito*, o que significa que você não precisa usar a palavra-chave *return* para retornar um valor.

```js
  const double = (x) => {
    return x * 2; // um retorno explícito aqui
  }
```

Uma vez que esta função apenas retorna algo (sem instruções antes da palavra-chave *return*), podemos fazer um retorno implícito.

```js
  const double = (x) => x * 2; // Correto, retorna x*2
```

Para fazer isso, só precisamos **remover os colchetes** e a palavra-chave **return**. É por isso que é chamado de *retorno implícito*, a palavra-chave *return* não existe, mas essa função retornará ```x * 2```.

> **Nota:** Se sua função não retornar um valor (com *efeitos colaterais*), ele não faz um retorno explícito nem implícito.

Além disso, se você quiser retornar implicitamente um *objeto*, você **deve ter parênteses em torno dele**, pois isso entrará em conflito com as chaves do bloco:

```js
const getPerson = () => ({ name: "Nick", age: 24 })
console.log(getPerson()) // { name: "Nick", age: 24 } -- objeto implicitamente retornado pela função de seta
```

- Só um argumento

Se a sua função apenas tiver um parâmetro, você pode omitir os parênteses à sua volta. Se pegarmos o código *double* acima:

```js
  const double = (x) => x * 2; // esta função de seta apenas leva um parâmetro
```

Parênteses ao redor do parâmetro podem ser evitados:

```js
  const double = x => x * 2; // esta função de seta tem apenas um parâmetro
```

- Nenhum argumento

Quando não há argumento fornecido para uma função de seta, você precisa fornecer parênteses, ou não será uma sintaxe válida.

```js
  () => { // parênteses são fornecidos, tudo está ok
    const x = 2;
    return x;
  }
```

```js
  => { // Sem parênteses, isso não funcionará!
    const x = 2;
    return x;
  }
```

##### Referência *this*

Para entender essa sutileza introduzida com funções de seta, você deve saber como [this](#this_def) se comporta em JavaScript.

Em funções de seta, *this* é igual ao valor *this* do contexto de execução envolvente. O que significa que uma função de seta não cria um novo *this*, Ela pega do seu entorno em vez disso.

Sem uma função de seta, se você quisesse acessar uma variável de *this* em uma função dentro de outra função, você tinha que usar *that = this* ou *self = this*.

Por exemplo, usando a função setTimeout dentro de myFunc:

```js
function myFunc() {
  this.myVar = 0;
  var that = this; // that = this (truque)
  setTimeout(
    function() { // Um novo *this* é criado neste escopo de função
      that.myVar++;
      console.log(that.myVar) // 1

      console.log(this.myVar) // undefined -- veja a declaração da função acima
    },
    0
  );
}
```

Mas com função de seta, *this* é retirado do seu entorno:

```js
function myFunc() {
  this.myVar = 0;
  setTimeout(
    () => { // this é retirado do entorno, o que significa de myFunc aqui
      this.myVar++;
      console.log(this.myVar) // 1
    },
    0
  );
}
```

#### Material Útil

- [Arrow functions introduction (Introdução à Funções de Seta) - WesBos](http://wesbos.com/arrow-functions/)
- [JavaScript arrow function - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Arrow function and lexical *this*](https://hackernoon.com/javascript-es6-arrow-functions-and-lexical-this-f2a3e2a5e8c4)

### Parametros padrão de uma Function

A partir da atualização do JavaScript ES2015, você pode definir um valor padrão para os parâmetros da função usando a seguinte sintaxe:

```js
function myFunc(x = 10) {
  return x;
}
console.log(myFunc()) // 10 -- nenhum valor é fornecido então o valor padrão de x que é 10 será atribuído a x em myFunc
console.log(myFunc(5)) // 5 -- um valor é fornecido então x é igual a 5 em myFunc

console.log(myFunc(undefined)) // 10 -- um valor undefined é fornecido então o valor padrão é atribuído para x
console.log(myFunc(null)) // null -- um valor (null) é fornecido, veja abaixo para mais detalhes neste caso
```

O valor de parâmetro padrão é aplicado em duas e somente duas situações:

- Nenhum parâmetro fornecido
- *undefined* parâmetro fornecido

Em outras palavras, se você passar um *null* o parâmetro padrão **não irá ser aplicado**.

> **Nota:** Atribuição de valor padrão também pode ser usada com parâmetros desestruturados (veja o próximo conceito para ver um exemplo)

#### Material Complementar

- [Default parameter value - ES6 Features](http://es6-features.org/#DefaultParameterValues)
- [Default parameters - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)

### Desestruturação de objetos e arrays

*Desestruturação* é uma maneira conveniente de criar novas variáveis extraindo alguns valores de dados armazenados em objetos ou arrays (matrizes).

Para nomear alguns casos de uso, *desestruturação* pode ser usado para desestruturar parâmetros de função ou *this.props* em projetos React, por exemplo.

#### Explicação com exemplo de código

- Objeto

Vamos considerar o seguinte objeto para todos os exemplos:

```js
const person = {
  firstName: "Nick",
  lastName: "Anderson",
  age: 35,
  sex: "M"
}
```

Sem desestruturação

```js
const first = person.firstName;
const age = person.age;
const city = person.city || "Paris";
```

Com desestruturação, tudo em uma única linha:

```js
const { firstName: first, age, city = "Paris" } = person; // É isso ! :)

console.log(age) // 35 -- uma nova variável age é criada e é igual a person.age
console.log(first) // "Nick" -- uma nova variável first é criada e é igual person.firstName
console.log(firstName) // ReferenceError -- person.firstName existe MAS a nova variável criada é nomeada primeiro
console.log(city) // "Paris" -- uma nova variável city é criada e uma vez que person.city é indefinida, city é igual ao valor padrão fornecido "Paris".
```

**Nota :** Em ```const { age } = person;```, os colchetes depois da palavra-chave *const* não são usados para declarar um objeto nem um bloco, mas é a sintaxe da *desestruturação*.

- Parâmetros de função

*Desestruturação* é freqüentemente usado para desestruturar parâmetros de objetos em funções.

Sem desestruturação

```js
function joinFirstLastName(person) {
  const firstName = person.firstName;
  const lastName = person.lastName;
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

Ao desestruturar o parâmetro de objeto *person*, obtemos uma função mais concisa:

```js
function joinFirstLastName({ firstName, lastName }) { // criamos variáveis firstName e lastName por desestruturação person parameter
  return firstName + '-' + lastName;
}

joinFirstLastName(person); // "Nick-Anderson"
```

A desestruturação é ainda mais agradável para usar com [funções de seta] (#função-de-seta):

```js
const joinFirstLastName = ({ firstName, lastName }) => firstName + '-' + lastName;

joinFirstLastName(person); // "Nick-Anderson"
```

- Array (Matriz)

Vamos considerar a seguinte array:

```js
const myArray = ["a", "b", "c"];
```

Sem desestruturação

```js
const x = myArray[0];
const y = myArray[1];
```

Com desestruturação

```js
const [x, y] = myArray; // É isso !

console.log(x) // "a"
console.log(y) // "b"
```

#### Material Útil

- [ES6 Features - Destructuring Assignment (Funcionalidades ES6 - Atribuição de Destruturação)](http://es6-features.org/#ArrayMatching)
- [Destructuring Objects - WesBos](http://wesbos.com/destructuring-objects/)
- [ExploringJS - Destructuring](http://exploringjs.com/es6/ch_destructuring.html)