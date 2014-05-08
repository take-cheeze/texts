* [Speeding up compile](http://nippondanji.blogspot.jp/2011/04/mysql-5530.html)
* [generating iOS binary without Xcode](http://d.hatena.ne.jp/kazuhooku/20130129/1359452808)
* [generating static library with Makefile](https://gist.github.com/j0sh/895945)

==ABI==
* Application Binary Interface
* [pass by value ABI](https://github.com/AndrejMitrovic/dgen/wiki/Pass-By-Value-ABI)

==EABI==
* Embedded ABI
* Used in ARM
* [EABI and OABI](http://www.oidon.net/linux/arm-eabi-oabi)
* [Using EABI](http://jr0bak.homelinux.net/~imai/linux/arm_gcc_badknowhow/arm_gcc_badknowhow-8.html)

==Predefined macro==
* [getting GCC's predefined macro](http://mkosaki.blog46.fc2.com/blog-entry-232.html)
* [wiki](http://sourceforge.net/p/predef/wiki/Home/)
* [Apple macro](http://www.opensource.apple.com/source/CarbonHeaders/CarbonHeaders-18.1/TargetConditionals.h)

==TCC==
* [old page](http://bellard.org/tcc/)
* [Current Repository](http://repo.or.cz/w/tinycc.git)
* libtcc: tiny C compiler that allows C as a scripting language.

==GCC==
* [link options](http://gcc.gnu.org/onlinedocs/gcc/Link-Options.html)

===g++===
* static linking libstdc++
  * pass '''-static-libstcc++''' in executable output
  * it may break some C++ project using '''dlopen'''
  * [mailing list patch](http://gcc.gnu.org/ml/gcc-patches/2009-06/msg01635.html)
  * [about dlopen](http://gcc.gnu.org/ml/gcc-help/2009-12/msg00186.html)
  * [dependency comparison](http://www.trilithium.com/johan/2005/06/static-libstdc/)

==Finding default compiler options==
* clang++/g++
  * regex the output of following command
  * "${COMPILER} -v -x c++ /dev/null -fsyntax-only"

==COINS==
* Compiler infrastructure written in Java
* [Project Page](@http://sourceforge.net/projects/coins-project/)

==LLVM==
* Famous compiler infrastructure written in C++
* [Project Page](@http://llvm.org/)
* Has debugger called LLDB

===clang===
* C/C++/Obj-C compiler
* sub project of LLVM
* GPL free licensed
* Options
  * -x
    * Used to force clang input file type.
    * For example if you are passing C++ header pass "-x c++-header"
  * -cc1
    * Use front end only.
* Pre-Tokenized Header
  * [Official Document](http://clang.llvm.org/docs/PTHInternals.html)
  * Parses file and cache them
  * It is effective in C++/Objective-C++ compiling.
* Pre-Compiled Header
  * [Official Document](http://clang.llvm.org/docs/PCHInternals.html)
  * To see stats of PCH use pass "-print-stats" option to clang
* auto-complete-clang
  * emacs script to use clang as a completion candidate generator
  * it is allowed to use PCH. But I think PTH is more efficient.
  * little heavy in C++ completion
* [Repository mirror](https://github.com/llvm-mirror/clang)
* [clang selecting](http://d.hatena.ne.jp/fu7mu4/20120217)
  * sudo port select clang $version

===[ELLCC](http://ellcc.org/)===
* The Embedded LLVM Compiler Collection
* [Manual](http://ellcc.org/ellcc/libecc/doc/)

==mingw==
* Windows GCC compiler.
* Can be used as cross compiler.

===mingw-w64===
* [Home page](http://mingw-w64.sourceforge.net/)
* [releases](http://sourceforge.net/projects/mingw-w64/files/mingw-w64/mingw-w64-release/)
* mingw fork that supports win64

===Package===
* [mingwのパッケージマネージャ](http://textt.net/take_cheeze/20110413083050/9)
* https://github.com/mkbosmans/download-mingw-rpm
にあるPythonスクリプトです．なぜか，python3を使っているみたいなので，ちゃんとpython3を入れましょう．   
使い方は
* ./download-mingw-rpm.py $(パッケージ名)
ってな感じで使えます．--depsを指定すると依存するパッケージも入れてくれます．   
一つ注意点があって
* ./download-mingw-rpm.py $(パッケージ名)
してから
* ./download-mingw-rpm.py zlib
みたいなことをすると結果的にzlibしか展開されてない状況になるので，必要なパッケージは全部一度に指定してください．   
それから，ヘッダが欲しい場合は，パッケージ名に"-devel"を付けるといいみたいです．   
で，これらのパッケージはどこから来ているのか？という疑問は当然あると思うんですが，ぶっちゃけopenSUSEのrpmパッケージから抽出しています．なので，Debian系使いとしては少々複雑な気分にさせられます．   
因みに，インストールできるパッケージは
* https://build.opensuse.org/project/packages?project=windows%3Amingw%3Awin32
に書いてあるものだけです．無いものは自分でビルドするなりしないといけないとおもいます．

===CMake toolchain script===

* http://www.cmake.org/Wiki/CmakeMingw
にあるtoolchain scriptを
* https://gist.github.com/2835996
ってな風にCMakeForceCompiler使ってるだけなんですけど，ちょっと改良してみました．使ってみたところそれほど問題はありませんでした．   
で，試しにWindows向けにクロスコンパイルしてみたかったプロジェクトをビルドしてみたんですけど，ライブラリがなかったりで，ビルドできませんでした．いくつか試しに入れてみたんですが，なんというかとても小さいなスクリプトではできないような感じなので，そのプロジェクトの人と相談してゴニョゴニョ…（ノ゜д゜（；￣Д￣）しないといけないかもしれません．
* https://launchpad.net/~tobydox/+archive/mingw
* https://launchpad.net/~clazzes.org/+archive/ppa
* https://launchpad.net/~mingw-packages/+archive/ppa
というふうにいくつか，Ubuntuのパッケージ化がなされているライブラリはあるんですが，いくつか足りないライブラリがあったりで，時前でやるしかない感じです．  
[Mac OS X](http://textt.net/take_cheeze/20110413083050/7)
* mingwなんてのがあるから調べてみた。
* http://ubuntuforums.org/showthread.php?t=838356
* http://www.sandroid.org/imcross/
[ruby-1.9.2](http://textt.net/take_cheeze/20110413083050/6)
* http://www.ruby-lang.org/ja/downloads/
* http://blade.nagaokaut.ac.jp/cgi-bin/scat.rb/ruby/ruby-talk/119413
* http://sourceware.org/ml/ecos-discuss/2000-04/msg00214.html

==Ruby on PSP==
extとかがまだ不完全だけどpushした。
* https://github.com/take-cheeze/psplibraries/commit/6e70df33dfd04f318f7eb0103352783458baaa97
* seekdirとtelldirがない環境だと不便。
* rubyがないとmakeが進まない。（apt-get install rubyが事前に必要になる）
* 本家に取り込んでもらった。
-* https://github.com/pspdev/psplibraries/commits/master

===pthreads-emb===
[pthreads-emb](http://textt.net/take_cheeze/20110413083050/5)
* pthread-embによく間違える。

* 組み込み環境向けのpthread。psp用のがあったりして便利。
* http://sourceforge.net/projects/pthreads-emb/files/pthreads-emb/1.0/
* Makefileを使ってインストールしてもpthread.hはインストールされないみたい。
* Makefileビルドしてインストールして、ヘッダをコピーする必要がありそう。
* pthread.hを上書きするのもアレなのでinclude/pthreads-embみたいなディレクトリをつくってそこにヘッダをおいたほうがいいかも

pthreads-embのpthread_tをvoid*にする。   
なんかrubyはポインタじゃないと不都合らしい…。
* どうやら、pthreads-embはpthreads-win32がベース。
* テストコードが動かなくて困った。
* https://sourceforge.net/projects/pthreads-emb/develop gitでcloneする
* https://github.com/blog/12-tarball-downloads tarballの落とし方
* https://github.com/take-cheeze/pthreads-emb

===expat===
psplibrariesにexpatをインストールした時のメモ
* sourceforge.netからファイルを落とす方法
* http://d.hatena.ne.jp/pikio/20090915/1253052588
* http://sourceforge.net/projects/expat/files/expat/2.0.1/
* http://expat.sourceforge.net/
* http://d.hatena.ne.jp/nakamura001/20101119/1290190954
* http://centossrv.com/bbshtml/webpatio/1732.shtml

sourceforge.netからのダウンロード   
-一回、余計にダウンロードしてからChromeのダウンロード履歴を見るとわかる。   
ライブラリがうまくリンクされない   
-LIBSじゃなくてLDFLAGSに"-lc -lpspuser"を渡す。

==CMake toolchain script==
本家
* http://www.cmake.org/Wiki/CMake_Cross_Compiling
自分の試み
* http://takecheeze.blog47.fc2.com/blog-entry-470.html
* http://takecheeze.blog47.fc2.com/blog-entry-496.html
iOS
* https://sites.google.com/site/michaelsafyan/coding/resources/how-to-guides/cross-compile-for-the-iphone/how-to-cross-compile-for-the-iphone-using-cmake
* https://sites.google.com/site/michaelsafyan/coding/resources/how-to-guides/cross-compile-for-the-iphone/how-to-cross-compile-for-the-iphone-using-cmake/faq
* https://sites.google.com/site/michaelsafyan/coding/resources/how-to-guides/cross-compile-for-the-iphone/how-to-construct-iphone-framework-bundles-for-cross-compiled-iphone-libraries

==psptoolchain==

* https://github.com/pspdev/psptoolchain
* https://github.com/pspdev/psplibraries
が開発の主流っぽい。

* http://misakalab.mithria.net/top/ptc-patch
* https://github.com/take-cheeze/psptoolchain/tree/gcc-4.6.0
が今のところ最先端

* https://github.com/pspdev/psplibraries
* https://github.com/take-cheeze/psplibraries
はメジャーなライブラリの移植版とか。   
生Makefileとか./configureを使うようなのなら対応できると思う。   
cmakeは問題山積。

ptc-patchのgcc-4.5.2がマージされたっぽい。
* https://github.com/pspdev/psptoolchain/commit/dbabf2c7e78303197680595e02c02996865fb789
[iconv](http://textt.net/take_cheeze/20110413083050/1)
newlibのconfigureに--enable-newlib-iconvを渡すとiconvが使える