# @taktikorg/omnis-veniam <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

ES Proposal spec-compliant shim for Set.prototype.isDisjointFrom. Invoke its "shim" method to shim `Set.prototype.isDisjointFrom` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment, and complies with the [proposed spec](https://github.com/tc39/proposal-set-methods). When shimmed, it uses [`es-set`](https://npmjs.com/es-set) to shim the `Set` implementation itself if needed.

Most common usage:
```js
var assert = require('assert');
var isDisjointFrom = require('@taktikorg/omnis-veniam');

var set1 = new Set([1, 2]);
var set2 = new Set([2, 3]);
var set3 = new Set([1]);

assert.equal(isDisjointFrom(set1, set2), false);
assert.equal(isDisjointFrom(set2, set1), false);
assert.equal(isDisjointFrom(set1, set3), false);
assert.equal(isDisjointFrom(set2, set3), true);
assert.equal(isDisjointFrom(set3, set2), true);

isDisjointFrom.shim();

assert.equal(set1.isDisjointFrom(set2), false);
assert.equal(set2.isDisjointFrom(set1), false);
assert.equal(set1.isDisjointFrom(set3), false);
assert.equal(set2.isDisjointFrom(set3), true);
assert.equal(set3.isDisjointFrom(set2), true);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

## Set Method Packages
 - [union](https://npmjs.com/set.prototype.union)
 - [intersection](https://npmjs.com/set.prototype.intersection)
 - [difference](https://npmjs.com/set.prototype.difference)
 - [symmetricDifference](https://npmjs.com/set.prototype.symmetricdifference)
 - [isSubsetOf](https://npmjs.com/set.prototype.issubsetof)
 - [isSupersetOf](https://npmjs.com/set.prototype.issupersetof)
 - [isDisjointFrom](https://npmjs.com/@taktikorg/omnis-veniam)

[package-url]: https://npmjs.com/package/@taktikorg/omnis-veniam
[npm-version-svg]: http://versionbadg.es/taktikorg/omnis-veniam.svg
[deps-svg]: https://david-dm.org/taktikorg/omnis-veniam.svg
[deps-url]: https://david-dm.org/taktikorg/omnis-veniam
[dev-deps-svg]: https://david-dm.org/taktikorg/omnis-veniam/dev-status.svg
[dev-deps-url]: https://david-dm.org/taktikorg/omnis-veniam#info=devDependencies
[testling-svg]: https://ci.testling.com/taktikorg/omnis-veniam.png
[testling-url]: https://ci.testling.com/taktikorg/omnis-veniam
[npm-badge-png]: https://nodei.co/npm/@taktikorg/omnis-veniam.png?downloads=true&stars=true
[license-image]: http://img.shields.io/npm/l/@taktikorg/omnis-veniam.svg
[license-url]: LICENSE
[downloads-image]: http://img.shields.io/npm/dm/@taktikorg/omnis-veniam.svg
[downloads-url]: http://npm-stat.com/charts.html?package=@taktikorg/omnis-veniam
[codecov-image]: https://codecov.io/gh/taktikorg/omnis-veniam/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/taktikorg/omnis-veniam/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/taktikorg/omnis-veniam
[actions-url]: https://github.com/taktikorg/omnis-veniam/actions
