* [repository](https://github.com/joyent/libuv)
* famous as I/O library of in node.js
* used as modern I/O library backend like rust
* [About serial port support.](https://github.com/joyent/node/issues/4092)
* [Simple HTTP server using libuv](https://github.com/mattn/http-server/blob/master/server.c)
* [API/ABI Changes Tracker](https://abi-laboratory.pro/?view=timeline&l=libuv)

## Taking benchmark
* In [mruby-uv#56](https://github.com/mattn/mruby-uv/issues/56) there is an example of a benchmark.
* In [this page](http://www.techempower.com/benchmarks/#section=code) there is a spec of benchmark.
 * There is 6 benchmarks. 1 json, 4 database, 1 plaintext test.
 * Seems like MySQL is preferred in the database test.

## Document
* [Official documentation](http://libuv.readthedocs.org/en/latest/)
 * uv.h documentation will be deprecated.
* [uv.h](https://github.com/joyent/libuv/blob/master/include/uv.h)
* [uvbook](http://nikhilm.github.io/uvbook/)
* [libuv-dox](https://github.com/thlorenz/libuv-dox)
 * Better documentation of uv.h .
* [learnuv](https://github.com/thlorenz/learnuv)
 * [learnuv gitbook](http://thlorenz.github.io/learnuv/book)
 * libuv tutorial implemented with node.js.

## Bindings
* [mruby binding](https://github.com/mattn/mruby-uv)

## OS X(iOS) framework dependencies
* In latest unstable release(0.11.x) OS X's framework dependencies is removed
* Thanks to the following 2 patches:
  * [CoreServices dependency remove](https://github.com/joyent/libuv/pull/243)
  * [CoreFoundation dependency remove](https://github.com/joyent/libuv/pull/898)

## Version notes

### libuv-v1.0.0-rc1
* Release candidate of v1.0.0(New major stable release).
* Basically it's based on 0.11.x libuv.
* New API [`uv_fileno`](https://github.com/joyent/libuv/commit/4ca9a363897cfa60f4e2229e4f15ac5abd7fd103).
