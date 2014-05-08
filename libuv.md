* [repository](https://github.com/joyent/libuv)
* famous as I/O library of in node.js
* used as modern I/O library backend like rust

# Document
* [uv.h](https://github.com/joyent/libuv/blob/master/include/uv.h)
* [uvbook](http://nikhilm.github.io/uvbook/)

# Bindings
* [mruby binding](https://github.com/mattn/mruby-uv)
  * not memory efficient
  * doesn't use MRB_SET_INSTANCE_TT for RData

# OS X(iOS) framework dependencies
* In latest unstable release(0.11.x) OS X's framework dependencies is removed
* Thanks to the following 2 patches:
  * [CoreServices dependency remove](https://github.com/joyent/libuv/pull/243)
  * [CoreFoundation dependency remove](https://github.com/joyent/libuv/pull/898)
