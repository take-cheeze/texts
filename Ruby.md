* by Matsumoto Yukihiro(matz)
* Scripting Language like python, perl
* Famous with Ruby on Rails web framework
* [Github mirror](https://github.com/ruby/ruby)
* [Command line argument](http://ruby.about.com/od/rubyfeatures/a/argv.htm)
* [tricky *star operator](http://d.hatena.ne.jp/kitokitoki/20110228/p1)
* [indenting json](http://ideone.com/ccifmd)
* [basic encodings](http://blog.grayproductions.net/articles/ruby_19s_three_default_encodings)
* [current method name](http://stackoverflow.com/questions/199527/get-the-name-of-the-currently-executing-method-in-ruby)
  * __method__
  * caller[0]
* [checking method or attribute exists](http://d.hatena.ne.jp/conceal-rs/20071109/1194589419)
  * use respond_to?
* [debugging technique](http://secondlife.hatenablog.jp/entry/20061010/1160453355)
* [removing iconv module](http://d.hatena.ne.jp/takehikom/20130224/1361711345)
  * gem is still available
  * iconv module is removed in 2.0
* [optparse usage](http://d.hatena.ne.jp/kk_Ataka/20111221/1324477125)
* [creating Proc from string](http://stackoverflow.com/questions/2459170/create-a-ruby-proc-from-a-string)
  * evaling string enclosed with lambda scope
* [ruby version compatibility](http://www.ownway.info/Ruby/index.php?version)
* [Pull request to use #line directive in ruby script.](https://github.com/ruby/ruby/pull/543)

## Document
* [Ruby Hackers Guide](http://i.loveruby.net/ja/rhg/book/)
* [Document](http://www.ruby-doc.org/)
* [minimum spec](http://www.ipa.go.jp/files/000011432.pdf)
  * mruby is based on this spec
* [RubyDoc](http://www.rubydoc.info/)
  * service that can find most ruby document
  * little slow since it is generated dynamically

## clone vs. dup
* [initialize_copy document](http://doc.ruby-lang.org/ja/2.0.0/method/Object/i/initialize_copy.html)
* clone copies meta info of the object.
* dup doesn't copy meta info.

## rubyspec
* [document](http://rubyspec.org/)
* [repository](https://github.com/rubyspec/rubyspec/)
* can write tests like english grammer

## Rake
* '''make''' like build tool that use ruby to write build script.
* [document](http://rake.rubyforge.org/doc/rakefile_rdoc.html)
* in mruby it use minirake that is a stand alone script that doesn't require any installation.
  * though Rakefile in mruby can be runned with normal rake

## C API Programming
* [Ruby Extension Programming Guide](http://i.loveruby.net/w/RubyExtensionProgrammingGuide.html)
* [Using with C++ guide](http://funktor.org/programming/cpp/embedding-ruby)
* [writing native gem](http://patshaughnessy.net/2011/10/31/dont-be-terrified-of-building-native-extensions)
* [extending ruby 1.9(pdf)](http://media.pragprog.com/titles/ruby3/ext_ruby.pdf)
* It's difficult to use with C++ because methods cannot have free variables.
  * using '''method_missing''' maybe easier but little slow than defining method
  * So it needs to use MACRO like __COUNTER__ or __LINE__
  * [rubybind](http://sourceforge.net/projects/rubybind/)
* what Object.new does
  * rb_obj_alloc(<- calles function specified with rb_define_alloc_func)
  * rb_obj_call_init(<- calles #initalize method)
* using RData
  * allocate object with function passing to rb_define_alloc_func
* official extensions
  * [stringio source](https://github.com/ruby/ruby/tree/trunk/ext/stringio)
  * [zlib source](https://github.com/ruby/ruby/tree/trunk/ext/zlib)
* handling exceptions
  * use rb_protect
  * [example codes](http://clalance.blogspot.jp/2011/01/writing-ruby-extensions-in-c-part-5.html)