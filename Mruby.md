* Light weight ruby
* [Repository URL](https://github.com/mruby/mruby)
* [emscripten changes](https://github.com/replit/emscripted-ruby/commit/c78f8457817e1fd57f7f464ae9a8158b13dac371)
* [mruby to c parser](https://github.com/mrbrdo/mruby_cc)
* [related projects](https://github.com/mruby/mruby/wiki/Related-Projects)

==Exceptions==
* Uses longjmp/setjmp internally.
* When C++ code is mixed it will use C++ exception instead.
  * [Exception patch that was used in emscripten(removed since longjmp/setjmp was supported now).](https://github.com/xxuejie/webruby/blob/19365625b1a2e215af69e8196053a17a33bebfed/patches/01-mruby-use-exception.patch)

==PNaCl/Emscripten==
* [Primitive boxing.](https://github.com/mruby/mruby/pull/1660)
  * Use primitive type as mrb_value.

==mruby-require==
* iij version
  * requires mruby-env/io/dir/tempfile
  * only supports script loading
* mattn version
  * supports dynamic library loading

==user defined object allocation==
* use MRB_SET_INSTANCE_TT
  * equivalent to rb_define_alloc_func
  * though it just sets allocating ruby object type
* need to allocate data if MRB_TT_DATA is set.
  * type and pointer must be set
  * DATA_PTR and DATA_TYPE is just a macro so the return of it can be assigned

==mrbgems==
* [document](https://github.com/mruby/mruby/blob/master/doc/mrbgems/README.md)
* [enabling](http://d.hatena.ne.jp/iamsandman/20121207/1354890750)
* [mgem](https://github.com/bovi/mgem)
  * [how to use](http://mruby.sh/201301040627.html)
  * command to add mrbgems
  * [mgem-list](https://github.com/bovi/mgem-list)
* MRuby::Build#gem
  * String is treated as mrbgem path
  * Hash(order is the priority)
    * :core : mrbgem path "${MRUBY_ROOT}/mrbgems/#{value of :core}"
      * example "conf.gem :core => 'mruby-time'"
    * :github : git url of "https://github.com/#{value of :github}.git"
      * example "conf.gem :github => 'take-cheeze/mruby-msgpack'"
    * :bitbucket: git url of "https://bitbucket.org/#{value of :bitbucket}"
      * example "conf.gem :bitbucket => 'masahino/mruby-skkdic'"
    * :git : git url. cloned when cleaned
      * example "conf.gem :git => 'https://github.com/take-cheeze/mruby-msgpack.git'"
    * :branch : used with repository URL. specifies with branch to use in repository
  * If a block is passed it will be called after the gem spec's block
* MRuby::Build#gembox
  * mrbgem set to import multiple mrbgems
  * by default 'default' and 'full-core' is available
    * 'default': default gembox. mruby-strintg-utf8 is not included in this
    * 'full-core': gembox of all gems that can be added with ":core"

===gems===
* [mruby zlib](https://github.com/viking/mruby-zlib)
  * zlib binding
  * Zlib.inflate/deflate

==Block==
* One of the most powerful feature of ruby.
* to call given block to function use **yield**.

==Garbage Collector==
* root_scan_phase scans marks root
* "mrb_iv_set"ed children(is in iv_tbl) will be marked if parent is marked
* All the mrb_value in RStruct will be marked.
* to mark mrb_value use mrb_gc_mark_value
* to mart RBasic* use mrb_gv_mark
* built-in type(e.g. int, float) is ignored
* Unable to have mark function(currently)

==Data type==
* mrb_sym
  * string reference like flyweight pattern. pooled string pointer
  * get it from mrb_intern(mrb, sym_str)
  * mrb_intern2 has string length argument
* mrb_irep
  * VM codes of mruby? Symbol table?
  * mrb_dump_irep/mrb_bdump_irep outputs mruby binary
  * mrb_cdump_irep outputs C code
  * to load binary outputed by "mrb -B" use mrb_read_irep, use mrb_load_irep to load if "-C","-B" wasn't passed.

==mrb_get_args() format==
{|
! char !! mruby type !! C type
|-
| o || Object || mrb_value
|-
| S || String || mrb_value
|-
| A || Array || mrb_value
|-
| H || Hash || mrb_value
|-
| s || String || char*, int
|-
| z || String || char*
|-
| a || Array || mrb_value*, mrb_int
|-
| f || Float || mrb_float
|-
| i || integer || mrb_int
|-
| b || boolean || mrb_bool
|-
| n || Symbol || mrb_sym
|-
| d || Data || void*, mrb_data_type
|-
| & || Block || mrb_value
|-
| * || rest argument || mrb_value*, int
|-
| ｜ || optional || after this character the following argument will be optional
|-
| ? ||  optional argument retrieved || mrb_bool
|}

==Built-in Classes==
* RBasic
  * base of all built-in classes
  * use RBASIC to get pointer from mrb_value
  * To create mrb_value use mrb_obj_value(p)
* RStruct
  * Tuple
  * able to access with index and symbol
* RData
  * C struct wrapper.
  * pointer getting
    * mrb_get_datatype: if error returns NULL
    * mrb_check_datatype: if error throws exception

==C language translater==
* [How to use.](http://d.hatena.ne.jp/MrShoz/20120423/1335194837)
* mrbc -C${symbol} ${file}.rb: outputs C function
  * ${file}.c: extern void ${symbol}(mrb_state* mrb) {}
* mrbc -B${symbol} ${file}.rb: outputs C array mruby binary
  * ${file}.c: extern const char hello[= {}
* mrbc ${file}.rb: outputs mruby binary
  * ${file}.mrb: mruby binary

==Native Client==
* How to build mruby

==Fiber==
* [https://github.com/mruby/mruby/issues/80 Not implemented](])
* [CRuby Fiber API](http://www.ruby-doc.org/core-1.9.3/Fiber.html)
* If single argument is passed to Fiber.yield that argument is returned.
* When multiple arguments is passed to Fiber.yield array of arguments is returned.
* ['''impelemented'''](https://github.com/mruby/mruby/commit/5c0b9b703c9d1a08d7219b057b809bda4bc89f8a)

==Weak Reference==
* Seems not implemented.
* [CRuby implemetation](http://d.hatena.ne.jp/authorNari/20081108/1226138174)
* In ruby 1.9 there is weak map so no special code is needed now.
* [weakref implementation using c++ shared_ptr/weak_ptr](https://github.com/take-cheeze/mruby-weakref)
  * don't know how much it's safe from GC.

==Native Client==
* [Example](http://akasata.hatenablog.com/entry/2012/05/29/163851)
* Use [with cmake](https://github.com/seichter/CMake-Toolchain-Collection/blob/master/toolchain-nacl.cmake) will be better

==Emscripten==
* [webruby](https://github.com/xxuejie/webruby)
* [patch to replace longjmp with exception throwing](https://github.com/xxuejie/webruby/commit/19365625b1a2e215af69e8196053a17a33bebfed)