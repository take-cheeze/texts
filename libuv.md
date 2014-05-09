* [repository](https://github.com/joyent/libuv)
* famous as I/O library of in node.js
* used as modern I/O library backend like rust
* [About serial port support.](https://github.com/joyent/node/issues/4092)

## Document
* [uv.h](https://github.com/joyent/libuv/blob/master/include/uv.h)
* [uvbook](http://nikhilm.github.io/uvbook/)
* [libuv-dox](https://github.com/thlorenz/libuv-dox)
  * Better documentation of uv.h .

## Bindings
* [mruby binding](https://github.com/mattn/mruby-uv)

## OS X(iOS) framework dependencies
* In latest unstable release(0.11.x) OS X's framework dependencies is removed
* Thanks to the following 2 patches:
  * [CoreServices dependency remove](https://github.com/joyent/libuv/pull/243)
  * [CoreFoundation dependency remove](https://github.com/joyent/libuv/pull/898)
