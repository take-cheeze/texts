* Functional system programming language developed my mozilla.
* [Tutorial](http://doc.rust-lang.org/tutorial.html)
* [Manual](http://doc.rust-lang.org/rust.html)
 * Not a specification.
* [Standard library reference](http://doc.rust-lang.org/std/)
* [Rust for C++ programmer](https://github.com/rust-lang/rust/wiki/Rust-for-CXX-programmers)

## Cargo
* Package manager for Rust.
* [Guide](http://crates.io/guide.html)
* [Using non Rust code](http://crates.io/native-build.html)
 * Command written in `build` would be run on package directory.

## [The new-type pattern](http://aturon.github.io/features/types/newtype.html)
Uses tuple type and `match` to take value.

## Using rust from other languages.
Using C library from rust is popular but the opposite is not major.
* [Linking and calling Rust functions from C](http://bluishcoder.co.nz/2013/08/08/linking_and_calling_rust_functions_from_c.html)
  * '-c' flag needs to be replaced with '--emit obj'.
  * `#[crate_type = "lib"]` isn't needed when '--crate-type lib' flag is passed.
  * `#[no_mangle]` attribute is needed when `dlsym`-ing.
* [Embedding Rust in Ruby](http://brson.github.io/2013/03/10/embedding-rust-in-ruby/)
  * Uses FFI.
* [Calling a Rust library from C (or anything else!)](http://mainisusuallyafunction.blogspot.jp/2014/08/calling-rust-library-from-c-or-anything.html)
  * `extern "C"` must be added to make code compatible with C.
