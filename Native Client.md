* Mechanism to run native code in browser.
* Only Chromium supports it.
* IA32, x86_64, ARM binary is supported.
* [howto use naclsdk command](https://developers.google.com/native-client/sdk/download)
* [Running LISP on NaCl](http://blog.jmuk.org/2014/01/nacl.html)
  * Has notes about nacl_io.
* [lua interpreter example](https://code.google.com/p/naclports/source/browse/trunk/src/ports/lua-ppapi)

==Documentation== 
* [Tutorial](https://developers.google.com/native-client/dev/devguide/tutorial)
* [Installation Manual](https://developers.google.com/native-client/dev/sdk/download)
* [Chromium Reference](http://www.chromium.org/nativeclient)
* [Pepper API Reference](https://developers.google.com/native-client/dev/peppercpp/inherits)
* [SDL Porting reference](https://developers.google.com/native-client/dev/community/porting/SDLgames)
* [Writing Manifest File](https://developers.google.com/native-client/devguide/coding/application-structure)
* [FileIO coding](https://developers.google.com/native-client/dev/devguide/coding/FileIO)

==Portable Native Client== 
* acronym: PNaCl
* Uses LLVM bitcode in executable to make executable more portable.
* When executing native client it will generate machine code with LLVM.
* [Chromium page](http://www.chromium.org/nativeclient/pnacl/building-and-testing-portable-native-client)
* [Handling struct in va_arg.](http://lists.cs.uiuc.edu/pipermail/cfe-commits/Week-of-Mon-20140106/096991.html)
* [Stability of PNaCl bitcode ABI.](http://www.chromium.org/nativeclient/pnacl/stability-of-the-pnacl-bitcode-abi)