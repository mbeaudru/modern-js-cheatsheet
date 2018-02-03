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
      - [Material Complementar](#external-resource)
    + [Função de Seta](#-função-de-seta)
      - [Exemplo](#sample-code-1)
      - [Explicação Detalhada](#detailed-explanation-1)
        * [Concision](#concision)
        * [*this* reference](#this-reference)
      - [Material Útil](#useful-resources)
    + [Parametros padrão de uma Function](#function-default-parameter-value)
      - [Material Complementar](#external-resource-1)
    + [Desestruturação de objetos e listas](#destructuring-objects-and-arrays)
      - [Explicação com Exemplo](#explanation-with-sample-code)
      - [Material Útil](#useful-resources-1)
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
