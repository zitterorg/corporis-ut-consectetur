# @zitterorg/corporis-ut-consectetur <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Robustly `.call.bind()` a function.

## Getting started

```sh
npm install --save @zitterorg/corporis-ut-consectetur
```

## Usage/Examples

```js
const assert = require('assert');
const callBind = require('@zitterorg/corporis-ut-consectetur');
const callBound = require('@zitterorg/corporis-ut-consectetur/callBound');

function f(a, b) {
	assert.equal(this, 1);
	assert.equal(a, 2);
	assert.equal(b, 3);
	assert.equal(arguments.length, 2);
}

const fBound = callBind(f);

const slice = callBound('Array.prototype.slice');

delete Function.prototype.call;
delete Function.prototype.bind;

fBound(1, 2, 3);

assert.deepEqual(slice([1, 2, 3, 4], 1, -1), [2, 3]);
```

## Tests

Clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@zitterorg/corporis-ut-consectetur
[npm-version-svg]: https://versionbadg.es/ljharb/@zitterorg/corporis-ut-consectetur.svg
[deps-svg]: https://david-dm.org/ljharb/@zitterorg/corporis-ut-consectetur.svg
[deps-url]: https://david-dm.org/ljharb/@zitterorg/corporis-ut-consectetur
[dev-deps-svg]: https://david-dm.org/ljharb/@zitterorg/corporis-ut-consectetur/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@zitterorg/corporis-ut-consectetur#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@zitterorg/corporis-ut-consectetur.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@zitterorg/corporis-ut-consectetur.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@zitterorg/corporis-ut-consectetur.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@zitterorg/corporis-ut-consectetur
[codecov-image]: https://codecov.io/gh/ljharb/@zitterorg/corporis-ut-consectetur/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@zitterorg/corporis-ut-consectetur/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@zitterorg/corporis-ut-consectetur
[actions-url]: https://github.com/zitterorg/corporis-ut-consectetur/actions
