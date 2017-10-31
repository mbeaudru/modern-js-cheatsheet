# Modern JavaScript Cheatsheet

![Modern JavaScript cheatsheet](https://i.imgur.com/aexPxMb.png)
<small>Image Credits: [Ahmad Awais ⚡️](https://github.com/ahmadawais)</small>

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
    + [Declaração de variáveis: var, const, let](#variable-declaration-var-const-let)
      - [Breve explicação](#short-explanation)
      - [Exemplo](#sample-code)
      - [Explicação Detalhada](#detailed-explanation)
      - [Material Complementar](#external-resource)
    + [Arrow function](#-arrow-function)
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
