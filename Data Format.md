* [detecting endianness using C union](http://stackoverflow.com/questions/1001307/detecting-endianness-programmatically-in-a-c-program)
* [Variable-length quantity](http://en.wikipedia.org/wiki/Variable-length_quantity)
 * Used in MIDI.
 * Other name BER compressed integer.

## [Dalvik executable format](http://source.android.com/devices/tech/dalvik/dex-format.html)
* Codes used in android.
* `.dex` is the extension of the file.
* [Uses LEB128 to store integer.](http://en.wikipedia.org/wiki/LEB128)
 * The order is opposite from BER compressed integer.

## Ruby Marshaling
* [usage of Marshal module](http://www.ruby-doc.org/core-2.0/Marshal.html)
* [old draft](http://www.ruby-lang.org/ja/old-man/html/Marshal_A5D5A5A9A1BCA5DEA5C3A5C8.html)
* [ruby-doc.org](http://ruby-doc.org/core-2.0/doc/marshal_rdoc.html)
* [document inside ruby repository](https://github.com/ruby/ruby/blob/trunk/doc/marshal.rdoc)
* [format spec](http://doc.ruby-lang.org/ja/2.0.0/doc/marshal=2dformat.html)
  * fixnum format doesn't include 'i'
  * symbol format includes identifier since it can be real symbol(':') or symbol link(';')
  * until 1.8
  * 1.9 has encodings and there is no description about it.
* [latest implementation](https://github.com/ruby/ruby/blob/trunk/marshal.c)
* [gem to inspect marshal structure](https://github.com/drbrain/marshal-structure)
* [request of marshal module to mruby](https://github.com/mruby/mruby/issues/53)
  * like Fiber will not be implemented for a while
* there is undocumented identifier 'e' that dumps class extending
* class name is class path so needs path_to_class api to get the class from it

### binary examples
* [motivation of the articles writer](https://github.com/jruby/jruby/issues/456)
* [part 1](http://jakegoulding.com/blog/2013/01/15/a-little-dip-into-rubys-marshal-format/)
* [part 2](http://jakegoulding.com/blog/2013/01/16/another-dip-into-rubys-marshal-format/)
* [part 3](http://jakegoulding.com/blog/2013/01/20/a-final-dip-into-rubys-marshal-format/)

### reading Marshal module
* [basic](http://blog.nhiroki.me/?p=132)
* [functions](http://blog.nhiroki.me/?p=183)
* [version and binary](http://blog.nhiroki.me/?p=249)

### symbol table
* array of unique symbols
* when a unique symbol is defined with ':' identifier it is appended to the array
* symbol id of ';' identifier is index of the array

### object table
* array of unique objects
* untracked identifier during loading
  * nil, true, false
  * fixnum
  * extended
  * symbol
  * instance variables
  * link
  * sub class instance variables of string, regexp, array, hash
* untracked data types during dumping
  * nil, true, false, fixnum, symbol
  * note that float is tracked

### "\004\b"
* means the marshal version
* the phrase is commonly used in marshaling tests.
* \b is 0x08 so "\004\b" is equivalent to "\x04\x08"

### RubySpec
* [basic tests](https://github.com/rubyspec/rubyspec/blob/master/core/marshal/fixtures/marshal_data.rb)
* [load](https://github.com/rubyspec/rubyspec/blob/master/core/marshal/shared/load.rb)
* [float](https://github.com/rubyspec/rubyspec/blob/master/core/marshal/float_spec.rb)

## MessagePack
* binary serialization format
* has problem with string handling
* [format spec](http://wiki.msgpack.org/display/MSGPACK/Format+specification)
* [header only C++ implementation](https://code.google.com/p/msgpack-cpp-lite/)

## YAML
* [home page](http://www.yaml.org/)

## TOML
* YAML replacement
* like JSON+INI
* [toml](https://github.com/mojombo/toml)

## INI
* used in windows config files
* wine registry use similar format
* [wikipedia page](http://en.wikipedia.org/wiki/INI_file)
  * escape sequence list
* [simpleini](https://code.google.com/p/simpleini/)
* [header only C++ parser](https://github.com/Poordeveloper/ini-parser)

## XML
* [expat](http://expat.sourceforge.net/)
  * fast C XML parser
  * [repository](http://expat.cvs.sourceforge.net/viewvc/expat/expat/)

## [JSON](http://json.org/)
* JavaScript Object Notation
* type list
  * Object
  * Array
  * Number
  * Boolean
  * String
  * Null
* [JSON Template](http://json-template.googlecode.com/svn/trunk/doc/Introducing-JSON-Template.html)
  * HTML Template language using JSON.
  * Golang has support.
* [json tester](http://jsonlint.com/)
* [json-diff](https://github.com/andreyvit/json-diff)
  * command to check json changes
  * implemented with node.js
* [JsonDiffPatch](https://github.com/benjamine/JsonDiffPatch)
  * Diff & Patch for JSON (from project page)
  * implemented with node.js
  * [main algorithm code](https://github.com/benjamine/JsonDiffPatch/blob/master/src/jsondiffpatch.js)
* [jsondiff](https://github.com/francois2metz/jsondiff)
  * ruby json patch module
* [yajl](https://github.com/lloyd/yajl)
  * json library written in C
