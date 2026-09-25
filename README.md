<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# dfillEqual

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Replace elements in a one-dimensional double-precision floating-point ndarray equal to a provided search element with a specified scalar constant.

<section class="intro">

</section>

<!-- /.intro -->



<section class="usage">

## Usage

```javascript
import dfillEqual from 'https://cdn.jsdelivr.net/gh/stdlib-js/blas-ext-base-ndarray-dfill-equal@deno/mod.js';
```

#### dfillEqual( arrays )

Replaces elements in a one-dimensional double-precision floating-point ndarray equal to a provided search element with a specified scalar constant.

```javascript
import Float64Vector from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-vector-float64@deno/mod.js';
import scalar2ndarray from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-from-scalar@deno/mod.js';

var x = new Float64Vector( [ 0.0, -2.0, 3.0, 0.0, 4.0, -6.0 ] );

var searchElement = scalar2ndarray( 0.0, {
    'dtype': 'float64'
});

var alpha = scalar2ndarray( 5.0, {
    'dtype': 'float64'
});

var start = scalar2ndarray( 0, {
    'dtype': 'generic'
});

var end = scalar2ndarray( 2, {
    'dtype': 'generic'
});

dfillEqual( [ x, searchElement, alpha, start, end ] );
// x => <ndarray>[ 5.0, -2.0, 3.0, 0.0, 4.0, -6.0 ]
```

The function has the following parameters:

-   **arrays**: array-like object containing the following ndarrays:

    -   a one-dimensional input ndarray.
    -   a zero-dimensional ndarray containing the search element.
    -   a zero-dimensional ndarray containing the scalar constant.
    -   a zero-dimensional ndarray containing the starting index (inclusive).
    -   a zero-dimensional ndarray containing the ending index (exclusive).

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   The input ndarray is modified **in-place** (i.e., the input ndarray is **mutated**).
-   If a specified `start` or `end` index is negative, the function resolves the respective index by counting backward from the last element (where `-1` refers to the last element).
-   When comparing elements, the function checks for equality using the strict equality operator `===`. As a consequence, `NaN` values are considered distinct and `-0` and `+0` are considered the same.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
import discreteUniform from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-discrete-uniform@deno/mod.js';
import scalar2ndarray from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-from-scalar@deno/mod.js';
import ndarray2array from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-to-array@deno/mod.js';
import ndarraylike2scalar from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-ndarraylike2scalar@deno/mod.js';
import dfillEqual from 'https://cdn.jsdelivr.net/gh/stdlib-js/blas-ext-base-ndarray-dfill-equal@deno/mod.js';

var opts = {
    'dtype': 'float64'
};

var x = discreteUniform( [ 20 ], 0, 3, opts );
console.log( ndarray2array( x ) );

var searchElement = scalar2ndarray( 1.0, opts );
console.log( 'Search Element: %d', ndarraylike2scalar( searchElement ) );

var alpha = scalar2ndarray( 5.0, opts );
console.log( 'Alpha: %d', ndarraylike2scalar( alpha ) );

var start = scalar2ndarray( 5, {
    'dtype': 'generic'
});
console.log( 'Start Index: %d', ndarraylike2scalar( start ) );

var end = scalar2ndarray( 15, {
    'dtype': 'generic'
});
console.log( 'End Index: %d', ndarraylike2scalar( end ) );

dfillEqual( [ x, searchElement, alpha, start, end ] );
console.log( ndarray2array( x ) );
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/blas-ext-base-ndarray-dfill-equal.svg
[npm-url]: https://npmjs.org/package/@stdlib/blas-ext-base-ndarray-dfill-equal

[test-image]: https://github.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/blas-ext-base-ndarray-dfill-equal/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/blas-ext-base-ndarray-dfill-equal?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/blas-ext-base-ndarray-dfill-equal.svg
[dependencies-url]: https://david-dm.org/stdlib-js/blas-ext-base-ndarray-dfill-equal/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/tree/deno
[deno-readme]: https://github.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/tree/umd
[umd-readme]: https://github.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/tree/esm
[esm-readme]: https://github.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/blas-ext-base-ndarray-dfill-equal/main/LICENSE

</section>

<!-- /.links -->
