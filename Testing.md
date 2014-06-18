* Writing test and running it improves software.
* There is many tools for it.
* "Design by Contract" is similar to testing

## [Catch](https://github.com/philsquared/Catch)
* Header only C++ test library.
* [Documentation.](https://github.com/philsquared/Catch/tree/master/docs)
* Doesn't have `*_EQUALS` or `*_GREATER_THAN` kind of macro. Prefers C++ syntax instead.
* Has two family of macro:
 * `REQUIRE`: when failed stops execution.
 * `CHECK`: continue executing although it failed.

## Boost 
* Boost has test library but not useful as others. It's just better than assert() macro
* Boost.Contract provides "Design by Contract"

## CMake 
* call "enable_testing()" in CMakeLists.txt for testing
* To use google test use FindGTest
* test added by "add_test()" can be run from "make test" if it generated Makefile

## Google Test 
* [Project Page](http://code.google.com/p/googletest/)
* [Documentation](http://code.google.com/p/googletest/wiki/Documentation)
* [Solving library not installed in ubuntu](http://askubuntu.com/questions/145887/why-no-library-files-installed-for-google-test-on-12-04)
* Add "--gtest_output=xml:${output_file}" to output JUnit test result.
* Problem in tr1/tuple in libc++
  * Since libc++(at least in Xcode 4.5.1) has no tr1 they will have compile error with it.
  * According to this [README](http://googletest.googlecode.com/svn/trunk/README) passing "-DGTEST_USE_OWN_TR1_TUPLE=1" to compiler will fix this.

## GDB 
* gdb may be used to auto test
* [Example](http://www.fireproject.jp/feature/gdb/advanced/auto-test.html)
