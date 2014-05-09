* [Table](http://ash.jp/code/unitbl21.htm)
 
## Ruby
* [Encoding](http://www.ruby-doc.org/core/Encoding.html)
* [Encoding::Converter](http://www.ruby-doc.org/core/Encoding/Converter.html)
* [Encoding::CompatibilityError](http://www.ruby-doc.org/core/Encoding/CompatibilityError.html)
* [Encoding::ConverterNotFoundError](http://www.ruby-doc.org/core/Encoding/ConverterNotFoundError.html)
* [Encoding::InvalidByteSequenceError](http://www.ruby-doc.org/core/Encoding/InvalidByteSequenceError.html)
* [Encoding::UndefinedConversionError](http://www.ruby-doc.org/core/Encoding/UndefinedConversionError.html)

## convmv
* file name encoding converter
* [man page](http://www.j3e.de/linux/convmv/man/)

## iconv
* command and library to convert character encoding
* library
  * [windows libiconv](http://gnuwin32.sourceforge.net/packages/libiconv.htm)
  * [japanese man page](http://linuxjm.sourceforge.jp/html/LDP_man-pages/man3/iconv.3.html)
  * [man page](http://pubs.opengroup.org/onlinepubs/009695399/functions/iconv.html)
  * has problem with iconv()'s 2nd argument type. some API has const but in standard non-const. so needs C++ template technique to remove error.

## Locale
* [UTF-8 setting](http://developer.momonga-linux.org/wiki/?UTF-8)
* [linux locale](http://www.linuxdocs.org/HOWTOs/Unicode-HOWTO-3.html)

## Literal
* [GCC](http://gcc.gnu.org/onlinedocs/cpp/Implementation_002ddefined-behavior.html)
* [msvc utf-8 literal](http://stackoverflow.com/questions/688760/how-to-create-a-utf-8-string-literal-in-visual-c-2008)
* Most of the time use ASCII only in source code.
* Use UTF-8 as possible.

## [ASCII](http://en.wikipedia.org/wiki/ASCII)
* Most basic character encoding.
* Most of the modern character encoding is based on this.
* 0x00 to 0x7F

## JIS
* [Shift_JIS table](http://charset.7jp.net/sjis.html)
* [Japanese character encoding table](http://charset.7jp.net/)
* [Shift_JIS and Ku,Ten](http://slashdot.jp/journal/476584/%E5%8C%BA%E7%82%B9%E3%82%B3%E3%83%BC%E3%83%89%E3%81%A8-Shift_JIS)
* [English wikipedia article](http://en.wikipedia.org/wiki/Shift_JIS)
  * has JIS X 0208 to Shift_JIS converting formula
* [Calculation ten and ku](https://code.google.com/p/rpg2kemu/source/browse/trunk/rpg2kLib/Font.cpp#22)
* [overview](http://www.bugbearr.jp/?Shift_JIS)
* JIS X 0208
  * [+ ku, 0x20 + ten](0x20)
  * kanji encoding
* JIS X 0201
  * ASCII extension with *kana* and japanese symbols
* Shift_JIS
  * encoding that can allow JIS X 0208 and JIS X 0201
  * was popular until UTF-8 gain status

## Latin
* ISO/IEC 8859-1(usually "Latin-1")
* codepage 1252
* Shinonome font has the support.
* [Accent in ASCII](http://cosmoshouse.com/tools/acc-conv-j.htm)
* [unix FAQ](http://www.cl.cam.ac.uk/~mgk25/unicode.html)

## Windows
* [code page table](http://msdn.microsoft.com/en-us/library/windows/desktop/dd317756(v=vs.85).aspx)
* If "_UNICODE" or "UNICODE" isn't defined local code page is used in string passing.
  * unicode api has "W" suffix
  * code page api has "A" suffix
  * to support either of API use <tchar.h>
* [mingw main function](http://sourceforge.net/apps/trac/mingw-w64/wiki/Unicode%20apps)
* [Windows macro](http://www.ruche-home.net/program/tips/unicode)
* [No wchar_t in Windows](http://cppcms.com/files/nowide/html/)

## Unicode
* [concept](http://marigold.sakura.ne.jp/devel/unicode/concept.html)

### Normalization
* use to compare unicode string
* has 4 type
* [utf8proc](http://www.public-software-group.org/utf8proc)
  * C library for utf-8 normalization.
  * supports all 4 normalization
  * returned string is allocated with malloc() so needs to be deallocated with free()
  * has ruby, posgresql binding

### Encoding

#### UTF-8
* encoding to use unicode in "const char*" or std::string.
* newer encoding but well used.
* needs little complex decode but is easier to use in conventional string system.
* no duplication with ASCII
* widely used to exchange string.
* [http://blog.clouder.jp/archives/001017.html screen utf-8 settings](http://www.firstobject.com/wchar_t-string-on-linux-osx-windows.htm)
* [using UTF-8 in windows](http://www.utf8everywhere.org/)
* [unix utf-8 filename](http://unix.stackexchange.com/questions/38055/utf-8-filenames)
* [python utf-8 filename](http://nedbatchelder.com/blog/201106/filenames_with_accents.html)

#### UTF-16
* Mostly used in Windows.
* needs to decode to use as Unicode so use UTF-32 as possible.

#### UTF-32
* uint32_t array of unicode.
* good for internal use but not good for exchanging.
* endian matters.

### [Unicode Iterator](http://www.boost.org/doc/libs/release/libs/regex/doc/html/boost_regex/ref/internal_details/uni_iter.html)
* Used to convert unicode encoding.
* Most of the time it needs to be converted to UTF-32 first.
* Older API(before 1.48.0) doesn't have range check so use the header that has range check.
* [test code](https://github.com/boostorg/regex/blob/master/test/unicode/unicode_iterator_test.cpp)
* [source code](https://github.com/boostorg/regex/blob/master/include/boost/regex/pending/unicode_iterator.hpp)
