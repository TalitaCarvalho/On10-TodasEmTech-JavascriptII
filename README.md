# JavaScript - II - Estruturas de Dados

---
## Instruções Iniciais:

1. Forkem o repositório para a conta pessoal de vocês.
2. Clonem no computador de vocês o repositório forkado em suas contas particulares.

**_ATENÇÃO_: Não modifiquem o conteúdo do projeto original forkado, apenas a que você copiou e renomeou!**

### Façam suas perguntas através do DontPad

[http://dontpad.com/On10-JSI](http://dontpad.com/On10-JSII)

---

## **1. Mas, afinal, qual é a importância da estrutura de dados?**

O trabalho de uma desenvolvedora front-end passa por uma função de extrema importância: o entendimento, manipulação e tratamento de dados.

Um fato que exalta a importância do estudo da estrutura de dados é **a atuação da desenvolvedora front-end dentro do projeto**. 

![front-endxback-end](assets/frontendxbackend.gif)

Normalmente, a desenvolvedora back-end desenvolve endpoints que encaminham os dados do banco de dados à desenvolvedora front-end. Assim, cabe à desenvolvedora front-end administrar e manipular os dados para serem exibidos na aplicação que está sendo construída, e também tratar os dados que serão enviados ao back-end.

![front-endxback-end2](assets/frontendxbackend2.gif)

A administração e manipulação dos dados passam pelo entendimento das estruturas de dados e dos métodos que podem ser utilizados para trabalhar com esses dados.

Logo, **Estrutura de Dados - ou *Data Structure*, é um meio de coletar e organizar informações de uma certa forma em que seja possível realizar operações com essas informações de um jeito efetivo.**

![data-structure](assets/data-structure.gif)

---

## **2. Então, o que são Arrays?**

Explicação Concisa: arrays são estruturas de dados que contêm uma lista ordenada de elementos.

```Javascript
const fruits = ['Apple', 'Banana', 'Pear'];

const numbers = [1, 2, 10, -2, -3, 7];
```

Mas, calma. Nós podemos aprofundar essa definição.

Um dos benefícios do array é que ele possibilita que, ao invés de declarar três variáveis diferentes, você pode declarar um array de variáveis:

```Javascript
let sanduicheQueijo = "Queijo";
let sanduichePresunto = "Rosbife";
let sanduicheVegetariano = "Vegetariano";

let sanduiches = ["Queijo", "Presunto", "Vegetariano"];
```

**Arrays são comumente utilizados para organizar dados de uma forma que os seus valores possam ser facilmente encontrados e manipulados.**

Normalmente, os dados armazenados são do mesmo tipo, como `integer` ou `strings`, ou, ainda, `objects` - que veremos mais para frente. Contudo, cabe mencionar que um array pode ser composto por elementos de tipos diversos.

```Javascript
let miscData = [1, "abajur", {index: "zero"}, 7, "beijinho", 5.6]
```

Bom, foi mencionado que o array engloba uma lista **ordenada** de dados. Ele é **ordenado** pois é possível acessar cada elemento através da sua posição dentro de um array:

```Javascript
const fruits = ['Apple', 'Banana', 'Pear'];

console.log(fruits[0]) 
// retorna a primeira posição do array: 'Apple'

const numbers = [1, 2, 10, -2, -3, 7];

console.log(fruits[1]) 
// retorna a segunda posição do array: 2
```

Essa posição é chamada comumente de **index** do elemento no array. E aqui é importante destacar que **a contagem do index** - ou da posição do elemento no array - **sempre se inicia em 0**.

![array-index](assets/arrayindex.gif)

### **Array.length**

Um array é um agrupamento de dados ordenado, onde é possível acessar um elemento de acordo com a sua posição.

Se é possível acessar a um elemento de acordo com a sua posição, logo se conclui que é possível saber quantos elementos existem dentro de um array.

Para isso existe a propriedade `length` -  que mostra o número de elementos contidos dentro de um array.

```Javascript
const clothing = ['shoes', 'shirts', 'socks', 'sweaters'];

console.log(clothing.length); // 4
```

Podemos usa-lo também para realizar uma operação de subtração com o tamanho total do array e, assim, pegar o último elemento de um array:

```Javascript
const clothing = ['shoes', 'shirts', 'socks', 'sweaters'];

console.log(clothing[clothing.length - 1]); // 'sweaters'
```
---
## **3. E os Objetos?**

Objetos também são um agrupamento de dados, mas que são organizados de forma diferente. Isso porque os dados são agrupados **sempre** contendo uma **propriedade** e um **valor**.



---
## **4. E como eu faço para obter informações localizadas dentro de um array ou um objeto?**

**Resposta: iteração!**

E o que seria iterar um array? Significa utilizar um método que percorre todos os elementos de um array para realizar operações com ele - seja para pegar um dos valores contidos no array, ordenar os dados em um array para serem exibidos em tela, ou, ainda, para realizar operações matemáticas, dentre outros.

Um dos jeitos de se iterar um array é por meio de um laço (também conhecido como *loop*). *Loops* permitem que você execute um único trecho de código por multiplas vezes, **possuindo sempre uma condição que resulta no seu encerramento, que é checada continuamente**.

### **Tipos de loops**

**1) For**

`For` é a construção de *loop* mais usual. Ela permite que você execute um único trecho de código continuamente, até que se alcance a condição que resulta no seu encerramento.

Ou seja, o `for` possui:

-  um **mecanismo de partida** - um inicializador, que inicia a contagem dos elementos do array 
-  uma **condição de encerramento** da execução do *loop* e que é validada a cada *loop*. É opcional.
-  uma **expressão final**, que será validada no final de cada iteração, para atualizar ou incrementar o contador inicializador.

Sintaxe: 

```Javascript
for ([inicialização]; [condição]; [expressão final]) {
   declaração
}
```

Vamos supor que eu tenha um conjunto de cupcakes que eu precise decorar. No caso, todos os cupcakes estão contidos no array `cupcakes`.

```Javascript
const cupcakes = [cupcake1, cupcake2, cupcake3, ...];
```

Assim, eu criei uma função para decorar os cupcakes, que eu chamei de `frostCupcake()`.

Eu poderia chamar essa função toda vez que um cupcake aparece para ser decorado. Contudo, esse método não funcionaria por muito tempo: além de ser ineficaz, a  quantidade de cupcakes que eu preciso decorar pode mudar e, assim, alguns cupcakes poderiam ficar sem decoração.

E aqui que podemos utilizar o `for` para iterar o array `cupcakes` e, assim, garantir que todos os cupcakes serão decorados:

![for-loop](assets/Intro_to_Programming_Loops.gif)

E como esse meu for ficaria no código?

```Javascript
const cupcakes = Array[];

for (const bolinhos = 0; bolinhos < cupcakes.length; bolinhos++) {
   frostCupcake()
}

```

Assim, com esse `for`, eu garanto que todos os meus cupcakes serão decorados.

**2) While**
No `while`, a diferença é que o *loop* ocorrerá até que uma condição deixe de ser verdadeira.

Sintaxe: 

```Javascript
while (condição) {
  rotina
}
```

Ou seja, o `while` é composto por:

-  uma **condição** que será sempre avaliada antes da passagem pelo laço. Se ela for `true`, o laço é executado. Se ela for `false`, a execução do while é finalizada.  
-  uma **rotina**, que será executada enquanto a condição do while for `true`.

Exemplo:

``` Javascript
while (i < 10) {
  text += "The number is " + i;
  i++;
}
```

**3) do...while**

É uma variante do `while`. Aqui, o bloco do loop será executado pelo menos uma vez, mesmo que a condição seja `false`, porque o bloco de código é executado antes da condição ser testada.

``` Javascript
const text = "";
const i = 0;
do {
  text += "The number is " + i;
  i++;
}
while (i < 5);
```

---
## **5. Métodos de iteração do Array**

Existem vários métodos já prontinhos que o JS nos dá para manipular dados de arrays. Eles são extremamente úteis e muito utilizados diariamente por pessoas desenvolvedoras. 

A lista completa dos métodos é encontrado nesse link: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array

Nessa semana, infelizmente, não conseguiremos ver todos os métodos, mas veremos alguns dos métodos mais utilizados.

## Métodos para adicionar e remover elementos

### **a) array.push()**

O método push() adiciona um ou mais elementos ao final de um array e retorna o novo comprimento desse array.

![array-push](assets/array-push.gif)

Exemplo de código:

``` Javascript
const numeros = [1, 2, 3];

numeros.push(4);

console.log(numeros); // [1, 2, 3, 4]

numeros.push(5, 6, 7);

console.log(numeros); // [1, 2, 3, 4, 5, 6, 7]
```

### **b) array.pop()**
O método pop remove o último elemento de um array e retorna aquele valor, modificando o tamanho do array.

![array-pop](assets/array-pop.gif)

Exemplo de código:

``` Javascript
const meuPeixe = ['acara-bandeira', 'palhaco', 'mandarim', 'esturjao'];

const meuPeixePop = meuPeixe.pop();

console.log(meuPeixe); // ['acara-bandeira', 'palhaco', 'mandarim' ]

console.log(meuPeixePop); // 'esturjao'

```

### **c) array.shift()**

O método shift()remove o primeiro elemento de um array e retorna esse elemento. Este método também muda o tamanho do array. 

![array-shift](assets/array-shift.gif)

Exemplo de código:

``` Javascript
const array1 = [1, 2, 3];

const firstElement = array1.shift();

console.log(array1);
// expected output: Array [2, 3]

console.log(firstElement);
// expected output: 1

```

### **d) array.unshift()**

O método unshift() adiciona um ou mais elementos no início de um array e retorna o número de elementos (a propriedade `length`) atualizado.

![array-unshift](assets/array-unshift.gif)

Exemplo de código:

``` Javascript

const arr = [1, 2];

arr.unshift(0); // result of call is 3, the new array length
// arr is [0, 1, 2]

arr.unshift(-2, -1); // = 5
// arr is [-2, -1, 0, 1, 2]

arr.unshift([-3]);
// arr is [[-3], -2, -1, 0, 1, 2]

```

## Métodos para extrair partes de um array

### **a) array.slice()**

Esse método retorna os elementos selecionados de um array em um novo array. Essa seleção é feita a partir do index dos itens.

**Importante: esse método não remove do array original os elementos selecionados**

Exemplo de código:

``` Javascript

const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1, 3);
console.log(fruits) // Banana, Orange, Lemon, Apple, Mango
console.log(citrus) // Orange, Lemon
```


### **b) array.splice()**

Já o splice() é diferente. Ele mexe no conteúdo do array original, adicionando itens novos enquanto remove itens selecionados.

Sintaxe:

``` Javascript

array.splice(indice[, deleteCount[, elemento1[, ...[, elementoN]]]);

```
 1. **indice:** Índice o qual deve iniciar a alterar a lista - ou seja, a partir de qual posição serão acrescentados itens, ou a partir de qual posição serão excluídos itens. 
   
 2. **deleteCount:** indicador de quantos itens devem ser removidos de um array. Se está em 0, então nenhum elemento/item deverá ser removido. É opcional.

 3. **elemento1, ..., elementoN:** Os elementos que serão adicionados no array. É opcional - caso não exista, o splice apenas removerá itens.


Exemplo de código:

``` Javascript

const myFish = ["angel", "clown", "mandarin", "surgeon"];
let removed = myFish.splice(2, 0, "drum");
//myFish é ["angel", "clown", "drum", "mandarin", "surgeon"]
//removed é [], nenhum elemento removido

removed = myFish.splice(3, 1);
//myFish é ["angel", "clown", "drum", "surgeon"]
//removed é ["mandarim"]

removed = myFish.splice(2, 1, "trumpet");
//myFish é ["angel", "clown", "trumpet", "surgeon"]
//removed é ["drum"]

removed = myFish.splice(0, 2, "parrot", "anemone", "blue");
//myFish é ["parrot", "anemone", "blue", "trumpet", "surgeon"]
//removed é ["angel", "clown"]

```

### **slice() x splice()**

Principal diferença: **o `slice()` não alterará o array original!** Ele apenas vai retornar a você um novo array contendo a seleção passada.

Por sua vez, o `splice()` tem o poder tanto de remover elementos, quanto de adicionar novos elementos ao array original.

![slicexsplice](assets/slicexsplice.gif)


## Métodos de manipulação do array - ES6

### **a) array.map()**

### **b) array.forEach()**

### **c) array.filter()**

### **d) array.reduce()**


---
## **6. Por último, mas não menos importante... arrow functions!**

Você sabia que é possível declarar uma função de um jeito diferente? Sim, para isso nós utilizamos as arrows functions!

Uma expressão arrow function possui uma sintaxe mais curta quando comparada a uma expressão de função. 

A sua sintaxe mais comum é essa:

``` Javascript
const minhaFuncao = (param1, param2, ...) => {
  //passos da minha função

  return meuResultado
}
```

E ela pode ser ainda mais diminuta! Se a função tem apenas um único parâmetro e esse parâmetro retorna um valor, você pode remover as chaves e a palavra `return`.


``` Javascript
const minhaFuncao = (param1) => meuResultado;
```

---

## **Links Úteis:**

### **Arrays e Objetos**

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array

https://www.w3schools.com/js/js_array_methods.asp

https://developer.mozilla.org/pt-BR/docs/Learn/JavaScript/Objects/Basics

### **Loops:**

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/for

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/while

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/do...while

**for...of / for...in**

https://imasters.com.br/front-end/diferenca-entre-for-of-e-for-in

https://www.devmedia.com.br/javascript-for-for-in-for-of/41018

https://woliveiras.com.br/posts/la%C3%A7os-de-repeti%C3%A7%C3%A3o-for-for-in-for-of/

### **Arrow Functions**

https://www.w3schools.com/js/js_arrow_function.asp

https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Functions/Arrow_functions

### **Vídeos**

- MasterClass Manipulação do DOM com mais ou menos 1h de duração [rocketseat](https://www.youtube.com/watch?v=UftSB4DaRU4&ab_channel=Rocketseat)
- Introdução ao DOM [Curso em Vídeo](https://www.youtube.com/watch?v=WWZX8RWLxIk&ab_channel=CursoemV%C3%ADdeo): *ps recomendo todos os vídeos dessa playlist sobre javascript!*
- Arrays: [Curso grátis da Trybe](https://www.youtube.com/watch?v=defBuY0nLrc)