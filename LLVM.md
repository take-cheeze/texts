## Book
* [きつねさんでもわかるLLVM](http://tatsu-zine.com/books/llvm)

## Document
* [portal](http://llvm.org/docs/)
* [Programmers Manual](http://llvm.org/docs/ProgrammersManual.html)
  * good document to read before reading LLVM code

## Repository
* [github mirror](https://github.com/chapuni/llvm-project)
  * Owned by developer of LLVM.

## bitcode
* binary expression of LLVM IR

## LLVM IR
* language used in LLVM
* has few kind of expression
* [Japanese langauge reference](http://www.h3.dion.ne.jp/~mu-ra/llvm/LangRefJ.html)

## clang
* Sub project of LLVM.
* C/C++/Objective-C compiler that use LLVM as a backend.
* Grown to a compiler that can be compared with GCC because of GPL 3 update.
* [Class reference](http://clang.llvm.org/doxygen/classes.html)
* [C API](http://clang.llvm.org/doxygen/group__CINDEX.html)
  * [patch](http://www.mail-archive.com/cfe-commits@cs.uiuc.edu/msg43766.html) to add function to check whether class is abstract
  * used from script language FFI
  * [ruby ffi of libclang](http://rubydoc.info/gems/ffi-clang/frames)
* [Cling](http://root.cern.ch/drupal/content/cling)
  * C++ interpreter using LLVM/Clang

### Plugin
* [llvm.org document](http://clang.llvm.org/docs/ClangPlugins.html)
* [Official plugin examples.](https://github.com/llvm-mirror/clang/tree/master/examples)
  * [Tutorial of it.](http://kevinaboos.wordpress.com/2013/07/29/clang-tutorial-part-iii-plugin-example/)
* [About clang plugin used in Document foundation.](https://wiki.documentfoundation.org/Development/Clang_plugins)
* [Const analysis plugin](https://github.com/rizsotto/Constantine)
* [List of projects extending clang.](http://clang.llvm.org/docs/ExternalClangExamples.html)
  * Useful for reading it as example of clang plugin.
  * [ToyClangPlugin.cpp](https://github.com/AlexDenisov/ToyClangPlugin/blob/master/ToyClangPlugin.cpp)
    * Good example for diagnostic engine(printing error message).
* [Document of Recursive AST Visitor.](https://github.com/chapuni/llvm-project/blob/master/clang/docs/RAVFrontendAction.rst)
* [How to create clang plugin for Xcode clang.](http://railsware.com/blog/2014/02/28/creation-and-using-clang-plugin-with-xcode/)
