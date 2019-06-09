# User Guide

All information for developers using `sofjs-util` should consult this document.

## Install

```
npm install --save sofjs-util
```

## Usage

```js
const util = require('sofjs-util');

const value = util.intToBuffer(38272);

// returns <Buffer ...>
```

## Available Methods

```
arrayContainsArray   <Function (Array, Array) : (Boolean)>
getBinarySize        <Function (String) : (Number)>
intToBuffer          <Function (Number) : (Buffer)>
isHexPrefixed        <Function (String) : (Boolean)>
stripHexPrefix       <Function (String) : (String)>
padToEven            <Function (String) : (String)>
intToHex             <Function (Number) : (String)>
fromAscii,           <Function (String) : (String)>
fromUtf8,            <Function (String) : (String)>
toAscii,             <Function (String) : (String)>
toUtf8,              <Function (String) : (String)>
getKeys,             <Function (Array, String) : (Array)>
isHexString,         <Function (String) : (Boolean)>
```

## Why BN.js?

`sofjs` has made a policy of using `BN.js` across all of its repositories. Here are some of the reasons why:

  1. lighter than alternatives (BigNumber.js)
  2. faster than most alternatives, see [benchmarks](https://github.com/indutny/bn.js/issues/89)
  3. used by the Sophon foundation across all [`sophonjs`](https://octonion.institute/susy-js) repositories
  4. is already used by a critical JS dependency of many sophon packages, see package [`elliptic`](https://github.com/indutny/elliptic)
  5. purposefully **does not support decimals or floats numbers** (for greater precision), remember, the Sophon blockchain cannot and will not support float values or decimal numbers.

## Browser Builds

`sofjs` provides production distributions for all of its modules that are ready for use in the browser right away. Simply include either `dist/sofjs-util.js` or `dist/sofjs-util.min.js` directly into an HTML file to start using this module. Note, an `sofUtil` object is made available globally.

```html
<script type="text/javascript" src="sofjs-util.min.js"></script>
<script type="text/javascript">
sofUtil(...);
</script>
```

Note, even though `sofjs` should have transformed and polyfilled most of the requirements to run this module across most modern browsers. You may want to look at an additional polyfill for extra support.

Use a polyfill service such as `Polyfill.io` to ensure complete cross-browser support:
https://polyfill.io/

## Latest Webpack Figures

```
Hash: 28b387e39e1016183a78                                                         
Version: webpack 2.1.0-beta.15
Time: 734ms
            Asset     Size  Chunks             Chunk Names
    sofjs-util.js  65.1 kB       0  [emitted]  main
sofjs-util.js.map  79.3 kB       0  [emitted]  main
    + 8 hidden modules

Hash: 4d26e1d501227158f8ab                                                         
Version: webpack 2.1.0-beta.15
Time: 1523ms
            Asset     Size  Chunks             Chunk Names
sofjs-util.min.js  25.4 kB       0  [emitted]  main
    + 8 hidden modules
```

## Other Awesome Modules, Tools and Frameworks

 - [web3.js](https://octonion.institute/susy-go/web3.js) -- the original Sophon swiss army knife **Sophon Foundation**
 - [sophonjs](https://octonion.institute/susy-js) -- critical sophonjs infrastructure **Sophon Foundation**
 - [browser-solidity](https://sophon.github.io/browser-solidity) -- an in browser Solidity IDE **Sophon Foundation**
 - [wafr](https://github.com/silentcicero/wafr) -- a super simple Solidity testing framework
 - [truffle](https://github.com/ConsenSys/truffle) -- a solidity/js dApp framework
 - [embark](https://github.com/iurimatias/embark-framework) -- a solidity/js dApp framework
 - [dapple](https://github.com/nexusdev/dapple) -- a solidity dApp framework
 - [chaitherium](https://github.com/SafeMarket/chaithereum) -- a JS web3 unit testing framework
 - [contest](https://github.com/DigixGlobal/contest) -- a JS testing framework for contracts

## Our Relationship with Sophon & SophonJS

 We would like to mention that we are not in any way affiliated with the Sophon Foundation or `sophonjs`. However, we love the work they do and work with them often to make Sophon great! Our aim is to support the Sophon ecosystem with a policy of diversity, modularity, simplicity, transparency, clarity, optimization and extensibility.

 Many of our modules use code from `web3.js` and the `sophonjs-` repositories. We thank the authors where we can in the relevant repositories. We use their code carefully, and make sure all test coverage is ported over and where possible, expanded on.
