<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

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

# Standard Error

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> [Standard error][standard-streams].



<section class="usage">

## Usage

To use in Observable,

```javascript
stderr = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/streams-node-stderr@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var stderr = require( 'path/to/vendor/umd/streams-node-stderr/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/streams-node-stderr@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.stderr;
})();
</script>
```

#### stderr

[Standard error][standard-streams] as a [Writable stream][writable-stream].

```javascript
// Write to the terminal...
stderr.write( 'Oh no!', 'utf8' );
// e.g., => 'Oh no!'
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   Unlike other streams, `stderr` can **never** be closed and, thus, never emits a `'finish'` event.
-   Although rare, writes can block when output is redirected to a file. 

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- run-disable -->

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript">
(function () {
var proc = require( 'process' );
var stdin = require( '@stdlib/streams-node-stdin' );
var stderr = require( '@stdlib/streams-node-stderr' );

// Set the encoding:
stdin.setEncoding( 'utf8' );

// Create an echo stream:
stdin.pipe( stderr );

// Push data to `stdin`:
stdin.push( 'beep' );
stdin.push( ' ' );
stdin.push( 'boop' );
stdin.push( '\n' );

// End the stream:
stdin.push( null );

// Ensure the process closes:
setTimeout( proc.exit, 1000 );

})();
</script>
</body>
</html>
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

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/streams-node-stderr.svg
[npm-url]: https://npmjs.org/package/@stdlib/streams-node-stderr

[test-image]: https://github.com/stdlib-js/streams-node-stderr/actions/workflows/test.yml/badge.svg?branch=v0.1.1
[test-url]: https://github.com/stdlib-js/streams-node-stderr/actions/workflows/test.yml?query=branch:v0.1.1

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/streams-node-stderr/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/streams-node-stderr?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/streams-node-stderr.svg
[dependencies-url]: https://david-dm.org/stdlib-js/streams-node-stderr/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/streams-node-stderr/tree/deno
[umd-url]: https://github.com/stdlib-js/streams-node-stderr/tree/umd
[esm-url]: https://github.com/stdlib-js/streams-node-stderr/tree/esm
[branches-url]: https://github.com/stdlib-js/streams-node-stderr/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/streams-node-stderr/main/LICENSE

[standard-streams]: https://en.wikipedia.org/wiki/Standard_streams

[writable-stream]: https://nodejs.org/api/stream.html#stream_class_stream_writable

</section>

<!-- /.links -->
