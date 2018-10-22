Ramda
=============

Uma biblioteca funcional prática para programadores de Javascript.

[![Build Status](https://travis-ci.org/ramda/ramda.svg?branch=master)](https://travis-ci.org/ramda/ramda)
[![npm module](https://badge.fury.io/js/ramda.svg)](https://www.npmjs.org/package/ramda)
[![dependencies](https://david-dm.org/ramda/ramda.svg)](https://david-dm.org/ramda/ramda)
[![Gitter](https://badges.gitter.im/Join_Chat.svg)](https://gitter.im/ramda/ramda?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


Por que Ramda?
----------

<img src="https://ramdajs.com/ramdaFilled_200x235.png" 
     width="170" height="190" align="right" hspace="12" />

Já existem diversas bibliotecas excelentes com um enfoque funcional. Típicamente, elas têm o objetivo de serem ferramentas de uso comum, adequadas ao trabalho em múltiplos paradigmas. Ramda é mais focado em seu objetivo. Nós queremos uma biblioteca projetada específicamente para um estilo de programação funcional, um que torne fácil canalizar funções, um que nunca altere dados do usuário.


O que é diferente?
-----------------

As características primárias do Ramba são:

* Ramda emfatiza um estilo funcional mais puro. Imutabilidade e funções sem efeitos colaterais
  são o centro de sua filosofia. Isso pode ajudar-lo a fazer o trabalho com código simples e elegante.

* As funções do Ramda tem Curry automático. Isso permite a construção de novas funções a partir de outras
  funções suprimindo os parâmetros finais.

* Os parâmetros das funções Ramda são ordenados de forma conveniente para o Curry. Os dados a serem operados
  são geralmente fornecidos por último.
  
  
Os últimos dois pontos, juntos, tornam muito fácil construir funções a partir de sequências de funções mais simples, cada uma delas transforma os dados e os passa adiante. Ramda foi projetado para esse tipo te código.


Introduções
-------------

* [Introducing Ramda](http://buzzdecafe.github.io/code/2014/05/16/introducing-ramda) by Buzz de Cafe
* [Why Ramda?](http://fr.umio.us/why-ramda/) by Scott Sauyet
* [Favoring Curry](http://fr.umio.us/favoring-curry/) by Scott Sauyet
* [Why Curry Helps](https://hughfdjackson.com/javascript/why-curry-helps/) by Hugh Jackson
* [Hey Underscore, You're Doing It Wrong!](https://www.youtube.com/watch?v=m3svKOdZijA&app=desktop) by Brian Lonsdorf
* [Thinking in Ramda](http://randycoulman.com/blog/categories/thinking-in-ramda) by Randy Coulman


Filosofia
----------
A sensação de usar Ramda deve ser assim como a de usar Javascript.
O JavaScript prático, funcional. Não estamos introduzindo
expressões Lamda em texto, não estamos pegando emprestado ["listas
consed"](http://www.expressionsofchange.org/hash-consing/), 
nem estamos portando todas as ["Clojure functions"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures).

Nossas estruturas básicas de dados são simples [objetos de JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object),
e nossas coleções são ["arrays" de JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). Nós também usamos outras propriedades nativas de JavaScript, 
como o uso de funções como objetos com propriedades.

Programação funcional é em boa parte sobre objetos imutáveis e
funções livres de efeitos colaterais. Ramba não *obriga* isso,
enquanto permite esse estilo com o mínimo de atrito possível.

Nós buscamos uma implementação ao mesmo tempo limpa e elegante, mas a API reina.
Nós sacrificamos uma boa parte da elegância na implementação por uma API mesmo levemente mais limpa.

Por último, mas não menos importante, Ramda prima por performance. Uma
implementação confiável e rápida ganha de qualquer noção de pureza funcional.


Instalação
------------

Para usar com [NodeJs](https://nodejs.org):

```bash
$ npm install ramda
```

Depois no console, ou no código:

```javascript
const R = require('ramda');
```

Para usar diretamente no navegador:

```html
<script src="path/to/yourCopyOf/ramda.js"></script>
```

ou a versão minificada:

```html
<script src="path/to/yourCopyOf/ramda.min.js"></script>
```

ou a partir de uma rede CDN, Seja da cdnjs:

```html
<script src="//cdnjs.cloudflare.com/ajax/libs/ramda/0.25.0/ramda.min.js"></script>
```

ou de um dos links abaixo fornecidos por [jsDelivr](http://jsdelivr.com):

```html
<script src="//cdn.jsdelivr.net/npm/ramda@0.25.0/dist/ramda.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/ramda@0.25/dist/ramda.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/ramda@latest/dist/ramda.min.js"></script>
```

(note que usar `latest` é aceitar um risco significativo que as mudanças na API Ramda quebrem seu código.)

Esses scripts adicionam a variável `R` ao [escopo global do navegador](https://developer.mozilla.org/en-US/docs/Web/API/Window).

Ou você pode injetar Ramda em virtualmente qualquer site usando o [bookmarklet](https://github.com/ramda/ramda/blob/master/BOOKMARKLET.md).

**Notas das versões > 0.25**
As versões Ramda abaixo da 0.25 não tem `export`.
Então em vez de `import R from 'ramda';`, é preciso usar `import * as R from 'ramda';`
Ou melhor ainda, importe somente as funções necessárias através de `import { nomeDaFunção } from 'ramda';`


### Build

`npm run build` cria os diretórios `es`, `src` e atualiza ambos arquivos __dist/ramda.js__ e __dist/ramda.min.js__


#### Builds Parciais

É possível selecionar somente um subconjunto das funcionalidades para reduzir o tamanho do arquivo. O sistema suporta essa redução
através de opções na linha de comando. Por exemplo, se você só está usando as funções `R.compose`, `R.reduce`, e `R.filter` é possível 
criar a Build Parcial com:

    npm run --silent partial-build compose reduce filter > dist/ramda.parcial.js

Isso requer ter NodeJs e as dependências do Ramda instalados (basta usar `npm install` antes de criar a Build parcial).


Documentação
-------------

Por favor leia a [documentação API](https://ramdajs.com/docs/).

Também disponível o nosso [Cookbook](https://github.com/ramda/ramda/wiki/Cookbook) com funções feitas para Ramda
que você pode considerar útil.


O nome
--------

Ok, é que nós gostamos de ovelhas.  Só isso.  É um nome curto, e que
ainda não tinha sido usado. Poderia ser `eweda` facilmente, mas daí 
seríamos forçados a dizer _eweda lamb!_, e niinguém quer isso. Para quem
não fala inglês, _lambs_ são cordeirinhos, _ewes_ são ovelhas, e _rams_ são 
carneiros. Logo Ramda talvez seja um lambda crescido... mas provavelmente não.


Realizando testes
----------------------

**Console:**

Para rodar os testes a partir do console, é preciso ter o `mocha` instalado:

    npm install -g mocha

Depois, na raíz do projeto você pode executar:

    mocha

Alternativamente, se você instalou as dependências com:

    npm install

Então você pode realizar os testes (com detalhamento) executando:

    npm test

**Navegador:**

Você pode usar o [testem](https://github.com/airportyh/testem) para
testar em diferentes navegadores, com atualização automática de testes.
Instale testem (`npm install -g testem`) e rode `testem`. Abra o link
fornecido no seu navegador e você verá o resultado no seu terminal.

Se você tem _PhantomJS_ instalado, você pode testar diretamente com o comando `testem -l phantomjs`


Uso
-----------------

Para versão `v0.25` e superior, importe toda a biblioteca ou selecione os modulos diretamente:

```js
import * as R from 'ramda'

const {identity} = R
R.map(identity, [1, 2, 3])
```

Importações destruturadas *não previnem necessariamente importar toda a biblioteca*. Você pode selecionar manualmente os métodos
com o seguinte comando, que só usa as partes necessárias para a função `identity`:

```js
import identity from 'ramda/src/identity'

identity()
```

Porém, selecionar os métodos manualmente é trabalhoso. A maior parte dos módulos que gerenciam pacotes, como Webpack e Rollup oferecem ["tree shaking"](https://developer.mozilla.org/en-US/docs/Glossary/Tree_shaking) como uma forma de remover código não usado e reduzir o tamanho do arquivo, mas a performance varia (discussão [aqui](https://github.com/scabbiaza/ramda-webpack-tree-shaking-examples).
Essa lista resume cada configuração de acordo com a tecnologia usada:

1. Webpack + Babel - use [`babel-plugin-ramda`](https://github.com/megawac/babel-plugin-ramda) para selecionar os métodos automaticamente. Discussão [aqui](http://www.andrewsouthpaw.com/2018/01/19/ramda-tree-shaking-not-supported-out-of-the-box/), exemplo [aqui](https://github.com/AndrewSouthpaw/ramda-webpack-tree-shaking-examples/blob/master/07-webpack-babel-plugin-ramda/package.json)
1. Somente Webpack - use o plugin `UglifyJS` para "treeshaking" junto com o `ModuleConcatenationPlugin`. Discussão [aqui](https://github.com/ramda/ramda/issues/2355), exemplo [aqui](https://github.com/scabbiaza/ramda-webpack-tree-shaking-examples/blob/master/06-webpack-scope-hoisted/webpack.config.js)
1. Rollup - faz um bom trabalho de "treeshaking", sem trabalho extra necessário; exemplo [aqui](https://github.com/scabbiaza/ramda-webpack-tree-shaking-examples/blob/master/07-rollup-ramda-tree-shaking/rollup.config.js)


Tipagem
-----------------

- [TypeScript](https://github.com/types/npm-ramda/)
- [Flow](https://github.com/flowtype/flow-typed/tree/master/definitions/npm/ramda_v0.x.x)



Traduções
-----------------

- [Chinese(中文)](http://ramda.cn/)
- [Ukrainian(Українська)](https://github.com/ivanzusko/ramda)
- [Portuguese(Brasil)](https://github.com/rafaelcastrocouto/ramda)



Agradecimentos
-----------------

Obrigado a [J. C. Phillipps](http://www.jcphillipps.com) pela logo.
Ramda logo artwork &copy; 2014 J. C. Phillipps. Licensed Creative Commons 
[CC BY-NC-SA 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/).
