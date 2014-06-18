* [cppreference.com](http://en.cppreference.com/w/cpp/header)
  * Has many description of C++11
  * Maybe the best in current C++ reference
* [cpprefjp](https://sites.google.com/site/cpprefjp/)
  * Best C++ reference in Japanese.
* [boostjp](https://sites.google.com/site/boostjp/)
  * Japanese boost portal site.
* [Boost C++ Library Document](http://www.boost.org/doc/libs/release/libs/libraries.htm)
  * Read here before you implement something in C++.
* [Boost uBLAS tutorial in Japanese](http://www.page.sannet.ne.jp/d_takahashi/boost/ublas/index.html)
* [command line flags module](https://code.google.com/p/gflags/)
* [header only JSON library](https://github.com/kazuho/picojson)
* [c++ programming principle in unix](http://d.hatena.ne.jp/yupo5656/20040712/p2)
* [std::istream -> std::string](http://stackoverflow.com/questions/3203452/how-to-read-entire-stream-into-a-stdstring)
* [Sprout](https://github.com/bolero-MURAKAMI/Sprout)
  * constexpr library
* c_function
  * [c_function and vtable](http://d.hatena.ne.jp/mb2sync/20071218#p1)
  * [type inference version](http://d.hatena.ne.jp/osyo-manga/20120323/1332507615)
  * [header](https://github.com/boost-vault/Function-Objects/blob/master/c_function.hpp)
* [NTL](http://www.shoup.net/ntl/)
* [boost.wave](http://www.ruche-home.net/program/boost/wave)
* [longjmp/setjmp and RAII](http://0xcc.net/blog/archives/000155.html)
  * makes C++ code unsafe
* [faster std::function implementation](http://dl.dropbox.com/u/27990997/function.h)
* [explaining monad with c++](http://newartisans.com/2010/07/a-word-on-haskell-monads-and-c/)
  * Haskell's syntax is better
* [Implicit Cast](http://en.cppreference.com/w/cpp/language/implicit_cast)
* [diff template library](https://github.com/cubicdaiya/dtl)
* [Better stream iterator in boost.spirit.](http://boost-spirit.com/home/2010/01/05/stream-based-parsing-made-easy/)

## ABI
* [Summary](http://mentorembedded.github.io/cxx-abi/)
* [ABI document.](http://mentorembedded.github.io/cxx-abi/abi.html)
* [Execption handling document.](http://mentorembedded.github.io/cxx-abi/abi-eh.html)
* [libcxx-abi spec](http://libcxxabi.llvm.org/spec.html)
* [Internal of C++ exception handling.](http://theofilos.cs.columbia.edu/blog/2013/10/03/c-exception-handling-stack-frame-destruction/)

## cfront
* prototype of C++
* translater to C
* [archive](http://www.softwarepreservation.org/projects/c_plus_plus/index.html#cfront)

## mangling
* function name format for c++ features such as overloading
* some mangling format doesn't have return type in it
  * this makes C++ FFI difficult
* [libmangle](http://mingw-w64.sourceforge.net/libmangle/)
  * mangling library for visual studio

## Boost.Build
* [how to build](https://sites.google.com/site/boostjp/howtobuild)
* [build using mingw](http://www.vle-project.org/wiki/Cross_compilation_Win32)
* [stackoverflow](http://stackoverflow.com/questions/1399252/boost-cross-compile-from-linux-to-windows)
* [cross compile](http://www.boost.org/boost-build2/doc/html/bbv2/tasks/crosscompile.html)
* [how to build library used in boost](http://wikiwiki.jp/wesnoth/?MinGW%A4%C8SDLSKK%A4%C7%A5%AF%A5%ED%A5%B9%A5%D3%A5%EB%A5%C9)
* don't forget to pass "--user-config=user-config.jam" so that it uses user-config.jam

## connecting std::ofstream to stdout
The basic is to [do somethings to rdbuf](http://handasse.blogspot.com/2009/05/c.html)but it needs some devise to do it. 
std::ofstream has const rdbuf() but non-const rdbuf() is hidden so we need to call it by casting to std::ostream like 

```C++
static_cast<std::ostream&>(ofs).rdbuf(std::cout.rdbuf());
```

After output is finished restore the rdbuf that is changed. 
Or don't use it in long running program.

## Using clang from python
* http://eli.thegreenplace.net/2011/07/03/parsing-c-in-python-with-clang/ 
- http://blog.fenrir-inc.com/jp/2011/07/clang_syntax_analysis_interface_with_python.html 
とかの記事を読んだことはあって前々から使ってみたいと思っていたんですが，スクリプト言語からC++へのバインダを生成するコードを書こうかと思って試してみました．ドキュメントがなかったり，自分の中であんまりうまく整理できてないことが多いせいか目的のモノへはまだ遠いんですが，C++がこうも簡単に使えるとは思っていなかったので楽しいです． 
実はインストールする方法がよくわかっていなかったのがハードルだったんですが，それが案外と簡単に解決しました．Clangのビルドがずっと必要だと思っていたんですが，実際はlibclangと 
- https://github.com/llvm-mirror/clang/tree/master/bindings/python/clang 
にあるpythonスクリプトがあればよかったようです．一応，バージョンによっては使えない関数があったりしてスクリプトが実行できないなんてことがあるので，libclangとバージョンを揃えないといけません． 
今のところASTの中身を標準出力するくらいが限界なんですが，ぼちぼちもっと役に立つツールを書ければと思っています．

## mcpp
llvm-gccのプリプロセッサとgccのプリプロセッサとの挙動の違いに気がついて，さてどうしたものかと思っていたんですけど，そういえば，独立した（independentとか？）プリプロセッサがあるのを思い出して，使ってみました． 
ウェブサイトはとりあえずここです． 
- http://mcpp.sourceforge.net/index.html 
C++98となっているあたりちょっと古いんですけど，C++11でプリプロセッサにはあんまり大きな変更点はなかったはずなので，問題ないと思います．精々，マクロがないとかそんな感じなので，たぶんビルドシステムでマクロを定義してやればなんとかなる問題ですし． 
使い方は，gccとそんなに変わらないので，CMakeLists.txtには実行ファイル検索のところだけを変更するだけで済みました．-Iでインクルードディレクトリを指定，-oで出力ファイルを指定，できます． 
gccと少し違うのは， 
- http://gcc.gnu.org/onlinedocs/cpp/Preprocessor-Output.html 
に書かれている出力形式とは違うところです． 
- # $(linenum) $(filename) $(flags)  
となるのが（$(var)はvarという値です） 
- #line $(linenum) $(filename)  
と行番号であることを明示してくれて読みやすくなっています．flagsがあるのかは知りません．それと，#line以外のメタ情報は調べてないのでわからないです．順次調べようかと思います． 
とりあえず，わかりやすい違いなので，sqlexer.cppの正規表現に手を加えてこっちも認識できるようにしました．これで，boost.preprocessorが使えるようにまたなりました． 
万歳＼(^o^)／万歳

## [スクリプト言語でPP](http://textt.net/take_cheeze/20110511102209/19)
C++なコードをSquirrelを移植していて、Boost.PP使いたいなーと思って、色々試してたらできそうだったので、やってみました。できたときは、「俺TUEEEEE！」と思いたかったんですが、いくつか欠点がみつかって、その気分はお預けになっています。 
まず、https://github.com/take-cheeze/sq_rpg2kmu/blob/master/CMakeLists.txtにどうやってやったのか書いてあります。cpp(C PreProcessor)をfind_programで見つけて、add_custom_commandでPP結果を出力するルールを記述、add_custom_targetで構文チェックです。まだプログラムが不十分な関係で実行できなくなっているのは、目をつむってください。 
因みに、PPのライブラリといったら、Boost.PPしか知らないので、cppにはBoostのインクルードパスを通してあります。Boost.PPがプリプロセッサならどこでも使えるライブラリなのは幸いでした。 
先程触れた欠点ですが、Squirrel側のサポートがないので、PP後のコードはPP前のコードと行番号がズレます。なので、PP前のファイルとPP後のファイルを両方みながらでないと構文エラーを直せません。使うコンパイラのcppによって仕様が違うかもしれないのですこし悩んでいます。 
そういえば、Squirrelのコメントの形式なんですが、実行した後に、//と/* */しかないと思って慌ててドキュメントを確認したところ#もOKらしいです。( http://www.squirrel-lang.org/doc/squirrel3.html#d0e410) なんか、とても助かりました。ギリセーフというか。 
それから、まだpushましてやcommitしていないコードの話なんですが、nut.inの.inがいらない方法でできそうなので、おそらく次のコミットあたりで、拡張子を元に戻します。それから、Squirrelだけで書かれたファイルなら#includeで色々と解決しそうです。大昔に考えられた仕組みが今も使えるって素晴らしいですね！そして、jsに対するメリットも増えました。明示的に#includeしないといけないのはめんどくさかったんです。それから、インクルードガードをきっと使えますね。Boost.PPを知って以来、PPをなめていたと思い知ったんですが、今、再び実感しています。 
うわさでは、PPはHTML生成にも使えるので、意外と万能な言語なんですね。

## [PPと遅延評価](http://textt.net/take_cheeze/20110511102209/13)
clangはgccのC++11標準ライブラリを使うと悲惨なので、C++03のままなんですが、そのせいかBoost.PPにとてもお世話になっています。C++11では簡単に書けるようなプログラムは、わざわざPPしてエミュレートですよ。 
っと、まあ、そんな状況でやっと気がついたんですが、
#define SOME_MACRO some_pp_func()
は、SOME_MACROとしてすぐに展開されるんですけど、
#define SOME_MACRO() some_pp_func()
は、SOME_MACRO()と書かれた時に展開されます。これを有名な言葉でいうと遅延評価（遅刻理由にも使える）と呼ぶそうです。関数型言語で実力を発揮する機能だそうで、「関数型したよ、ぬふふ」（きもい笑い）と喜んでいます。しかし、C++も一応、関数型言語の端くれらしいので、実際は当たり前の機能です。 
それに、テンプレートだけとかPPだけでプログラムを書けば、それはれっきとした関数型なプログラムになります。なので、実際は微妙でした。すいません。 
別の話なんですが、BOOST_PP_ITERATEはよく知って使わないと、なんか大変ですね。REPEATとかSEQ_FOR_EACHのノリで使うと悲惨な結果しか待っていない気がします。インクルードガードの位置も独特です。さっき、気がついてやっと直しました。ついでに、そのままだったエラーもいっぱい出てきて、variadic templatesが早く使いたいです。

## MPL
Boost.MPLは一度これ縛りで書いたことがあるんですが、デバッグ不能なコードになってしまって放棄した記憶があります。それ以来、遠ざかっていたんですがenable_ifで色々したくなったらどうしても必要なので、とりあえず、今日はちょこちょこ触っていました。そうしたら、不思議と以前感じた違和感がだいぶなくなって少しだけ楽しいです。 
グーグル先生に質問しまくったところこのリンクが一番早い気がします。 
- http://d.hatena.ne.jp/osyo-manga/20110510/1305008054 
細かいところは、どうしてもリファレンスが必要なんですが、MPLのリファレンスは階層が深くて億劫です。ただこれはテンプレートの副産物なのでしょうがないのでしょうね。

## [nutbindの書き直しとか](http://textt.net/take_cheeze/20110511102209/9)
luabindを改造したのがあまりにアレしたので、ほとんどのコードを捨てて書きなおしてます。ただ、テストは残しました。これを全部コンパイルできるようにするのが今のところの目標です。 
それで、今日は関数呼び出しのところを実装してました。なんか自分でも嫌になるくらいPPしててキモいです。一箇所間違えると、Gなみにエラーが増殖するのはやっぱりこわくて怖気付きます。でも、そのおかげでboost/std::functionの実装方法（の一部）が理解できたのは思わぬ収穫です。 
下の２つのページが一番参考になった気がします。 
- http://d.hatena.ne.jp/faith_and_brave/20071031/1193831871 
- http://d.hatena.ne.jp/mb2sync/20050324 
今回、一番わかっていなかったのは可変長引数の部分なんですが、これはもうほとんどPPによる力技みたいです。どうやって呼び出しているのかは、書き方を覚えてしまえば大したことないように感じられます。

それから、enable_ifの使い方を覚えました。type_traitsと組み合わせれば特殊化よりもこっちのほうが便利な気がします。それに、特殊化は継承した型には効かないそうです。 
http://cpplover.blogspot.com/2008/01/boostenableif.html

## [C++0x](http://textt.net/take_cheeze/20110511102209/1)

**[http://textt.net/content/edit/20110511102209/1]
**[http://textt.net/content/destroy/20110511102209/1]
**[http://twitter.com/share?url=http%3A%2F%2Ftextt.net%2Ftake_cheeze%2F20110511102209%2F1&text=Please%20check%20%5BC%2B%2B0x%5D%20on%20Textt%20%23textt]
**[http://www.facebook.com/sharer.php?u=http%3A%2F%2Ftextt.net%2Ftake_cheeze%2F20110511102209%3Fversion%3D1&t=Please%20check%20%5BC%2B%2B0x%5D%20on%20Textt%20%23textt]
ちょっと古いリンク集 
- http://www.aristeia.com/C++0x/C++0xFeatureAvailability.htm

有名なコンパイラな対応表 
- http://wiki.apache.org/stdcxx/C++0xCompilerSupport

clangのステータス 
- http://clang.llvm.org/cxx_status.html

gcc  
- http://gcc.gnu.org/projects/cxx0x.html


## Grammer
* [BNF](http://www.csci.csusb.edu/dick/doc/Cpp.bnf)
  * [C version](http://www.csci.csusb.edu/dick/samples/c.syntax.html)

## Boost

### Container
* [Document](http://www.boost.org/doc/libs/release/doc/html/container.html)
* Container utilities and boost optimized container.
  * Move semantics from boost.move
  * Allocators
* flat container
  * Sorted vector.

## [BOOST_CURRENT_FUNCTION](http://textt.net/take_cheeze/20101027154606/14)
このマクロを知らなかったのでちょっと、損してました。nutbindのdebug.hppでわざわざこれと同じ事は要らなくて、<boost/current_function.hpp>をインクルードして、BOOST_CURRENT_FUNCTIONと黙って書いておけばよかったんです。
( https://github.com/take-cheeze/langbind/blob/204b46cc34a99f486786fc6aeb75c0118e3f1416/nutbind/detail/debug.hpp ) 
GCCの__PRETTY_FUNCTION__はC++のテンプレート引数とかもちゃんと書いてくれるのでこれに移植性が高いものなら素晴らしいです。

## Boost.Localが採択されたらしい
ちょっと気乗りしてなかったので、モチベーションを上げるために採択されたとタイムラインで話題になっていたBoost.Localを調べてました。一応、英語の勉強です。(；･`д･´)  
まず、どうゆうライブラリなのかというと、関数内でも関数を定義できるようにするものです。"struct { T operator()() {} } func;"みたいな仕組み...らしいんですが、それ以外にローカル変数の拘束や、C++03でのサポート、C99のサポートなど、とっても変態だと思います。 

リンク 
- レビュー開始の告知: http://lists.boost.org/boost-announce/2011/11/0338.php  
- レビュー結果: http://thread.gmane.org/gmane.comp.lib.boost.devel/226546  
- Boost.Localのドキュメント: https://svn.boost.org/svn/boost/sandbox/local/libs/local/doc/html/index.html  
- Boost.Localのソースコード: https://svn.boost.org/svn/boost/sandbox/local/boost/  

このライブラリの対象は、C++11のラムダ式・Boost.Lambda・Boost.Phoenixと多くのものと被っているのですが、それらが及ばない領域もサポートしています。C++11のラムダは、C++03では使えません。Boost.LambdaやBoost.Phoenixはテンプレートを多用しているため、コンパイル時間が長かったり負荷も大きく、またコンパイルエラーも複雑です。それに引き換え、Boost.LocalはC++03で使えます。そして、テンプレートの代わりにPPを多用しているので、テンプレートよりも負荷は小さく（書き方さえ間違えなければ）エラーも易しいです。 
なので、まだC++03しか使えず、マクロを許容できて、テンプレートに自信がない人には、もってこいです！（わたしは対象外） 

さて、中身の話ですが、とりあえずPPがまったくわかりませんでした。bindキーワードをどうやって実装してるのか全くわからずソースコードを見たりドキュメントを読んだんですが、わかりませんでした。BOOST_LOCAL_TYPEOF( https://svn.boost.org/svn/boost/sandbox/local/libs/local/doc/html/BOOST_LOCAL_TYPEOF.html )というものを使っているそうですが、これはBoost.Typeofとは別物みたいです。PPには多少が自信がついてきたつもりなんですが、その自信もあっさりへし折られました。orz  
レビューの内容もマクロ名を変えるとかそうゆう細かい瑣末なことしかわりません。 
テンプレートがPPの代替なのがよくわかります。 

そういえば、ベンチマーク( https://svn.boost.org/svn/boost/sandbox/local/libs/local/doc/html/boost_local/Alternatives.html#boost_local.Alternatives.local_function_benchmarking )がけっこう面白かったです。Boost.LambdaとBoost.Phoenixが想像していたよりも、コンパイルに掛かる時間に対してそんなに早くなかったです。それに、バイナリのサイズも他よりも増加しています。更に、最適化がないとコンパイルに掛かる時間がBoostしてますね！ 
それと、「いくらテンプレートじゃないからといってコンパイルには時間掛かるだろ？」と予想していたんですが、C++11のラムダとあまり変わらないですね。意外です。 

まとめですが、そんなに興味のあることじゃなかったので、ないです。強いて言うならば、コンパイルにかかる時間を縮めたくなったら使うかもしれません。このライブラリは、C++11への移行期だからこそ、な面が強いです。Boost.Localが使えるバージョンのboostでついカッとなって使いたくなるかもしれませんね。

(2011/12/17 移動。2011/12/15に書いた）

## [boost.exception](http://textt.net/take_cheeze/20101027154606/12)
nutbindで例外処理をしたくなったので、いいライブラリが無いのかと、探したんですけど、luabindはboostをいっぱい使ってるということなので、boost.exceptionを使ってみることにしました。 
まず、どのようなライブラリなのかというと 
- C++11でのexceptionヘッダにあるexception_ptrなど（http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2179.html ） 
- ソースコードのファイル名と行番号、現在の関数（BOOST_CURRENT_FUNCTION）などの付加  
- 例外が使えない環境での対応 
といったことでしょうか。使い始めたばかりだとよくわかりませんね。 
今回、わたしが目的としたのは、例外の使えない時にどうするか？というものです。Effective C++でわたしの例外安全に関する考え方の甘さを思い知った後なので、例外がめんどくささを実感します。従来のエラー処理よりも楽なのは確かだと思うんですけど、やっぱり強力な分、負の面が大きいんですね。きっと。 
例外のない環境でのサポートですが、 

#ifdef BOOST_NO_EXCEPTIONS  
void throw_exception(std::exception const & e) {  
// ごにょごにょ 
}  
#endif  

的なコードを書けばいいみたいです。終わり。 
ちょっと補足すると、この関数は時々リンカエラーで出てきます。正直そうゆうエラーに悩まされたくないと思うなら例外を使った方がいいです。例外によるパフォーマンス低下よりも、例外によるエラーハンドリングの方がメリットが大きいと思います。 
因みに、nutbindでは 
https://github.com/take-cheeze/langbind/blob/master/nutbind/detail/function_utility.hpp#L32  
といった風に使っています。PREFIXはC++関数の呼び出しの前に、SUFFIXは後に、置くマクロです。構文上、セミコロンを書けないのが悔しいですね。12/17/11

## [bcp](http://textt.net/take_cheeze/20101027154606/11)
Boostから必要なヘッダをコピーするツール
- http://www.boost.org/doc/libs/release/tools/bcp/doc/html/index.html 
- http://d.hatena.ne.jp/Cryolite/2005102507/21/11

## [Asio](http://textt.net/take_cheeze/20101027154606/10)
非同期な入出力ライブラリ
- ネットワークが得意らしい。

まとめ
- http://d.hatena.ne.jp/tt_clown/20110325/130104879506/11/11

## [Iostreams](http://textt.net/take_cheeze/20101027154606/9)
- 標準ライブラリの入出力ライブラリを拡張しやすくしてくれるの。
- zlibとかそれだけでもけっこう使える。

バイナリデータ(std::vectorとかstd::arrayとかstd::string)をコピーなしでストリームにする方法
- arrayデバイスを使う。
- reinterpret_castがめんどうだけどねー

## [iterators](http://textt.net/take_cheeze/20101027154606/8)
counting_iterator 
- http://www.boost.org/doc/libs/release/libs/iterator/doc/counting_iterator.html 
- int型を格納するのに使うイテレータ。
- for(int i = 0; i < size; i++) {}の時に使う。
- make_counting_iteratorという補助関数があるけど、長くなる。
- counting_rangeがrange版（irangeにした方がいいかも）
-- http://www.boost.org/doc/libs/1_46_1/libs/range/doc/html/range/reference/ranges/counting_range.html 06/25/11

## [ptr_container](http://textt.net/take_cheeze/20101027154606/7)
- スマポをSTLコンテナに入れるよりも効率的なコンテナ。
- unique_ptrがサポートされておらず、auto_ptrを使う必要がある。（1.46.1現在）

https://github.com/freundlich/fcppt/blob/master/include/fcppt/container/ptr/insert_unique_ptr_map.hpp 
- mapにunique_ptrをinsertするユーティリティ。
- 連想コンテナは生ポインタを挿入する時、keyがnon-constじゃないといけない。

所有権を持たないconst/non-constが効くT*の集合。
- http://d.hatena.ne.jp/eldesh/20110415/1302852188 
- http://d.hatena.ne.jp/redboltz/20110413/1302698607 
- http://d.hatena.ne.jp/redboltz/20110218/129798905006/25/11

## [Regex](http://textt.net/take_cheeze/20101027154606/6)
- 正規表現ライブラリ。
- C++0xに採用されている。
- ICU( http://site.icu-project.org/ )に依存してるみたい。
- リリース版では、コンパイル時間の長いXpressiveを使うべきかも。05/06/11

## [intrusive_ptr](http://textt.net/take_cheeze/20101027154606/5)
shared_ptrよりも手間がかかるけどshared_ptrよりも軽いポインタ。
参照カウントの処理を自分で書かないといけない。
- http://www.codeproject.com/KB/stl/boostsmartptr.aspx 
- http://alsharabi.blogspot.com/2009/06/boostintrusiveptr-is-one-of-six-smart.html 
- http://www.kmonos.net/alang/boost/classes/intrusive_ptr.html 
- http://www.cs.brown.edu/~jwicks/boost/libs/smart_ptr/intrusive_ptr.html 
- http://www.boost.org/doc/libs/1_46_1/libs/smart_ptr/intrusive_ptr.html04/29/11

## [Spirit](http://textt.net/take_cheeze/20101027154606/4)

**[](http://textt.net/content/edit/20101027154606/4)
**[](http://textt.net/content/destroy/20101027154606/4)
**[](http://twitter.com/share?url=http%3A%2F%2Ftextt.net%2Ftake_cheeze%2F20101027154606%2F4&text=Please%20check%20%5BSpirit%5D%20on%20Textt%20%23textt)
**[](http://www.facebook.com/sharer.php?u=http%3A%2F%2Ftextt.net%2Ftake_cheeze%2F20101027154606%3Fversion%3D4&t=Please%20check%20%5BSpirit%5D%20on%20Textt%20%23textt)
Qi 
- http://d.hatena.ne.jp/faith_and_brave/20110428/1303981789 
- http://d.hatena.ne.jp/boleros/20110429/1304096915 
- http://d.hatena.ne.jp/boleros/20110502/1304341387 

- http://d.hatena.ne.jp/Hossy/2008040705/21/11


## Effective C++
* Best book to read after a tutorial.
* g++ has "-Weffc++" that warns the things written in this book.
  * but inheriting warning is annoying in traits so I prefer not using it.

## C++11
* C++ standard that was published in 2011
* Many language improvements and new library mostly from boost.
* [Support status](http://www.aristeia.com/C++11/C++11FeatureAvailability.htm)

### array
* std::array
* How to remove element number from your code
  * [1](http://d.hatena.ne.jp/RiSK/20110502)
  * [2](https://gist.github.com/657582)
  * use with C++11 auto keyword

### Difference between boost
* [enable_if](http://d.hatena.ne.jp/faith_and_brave/20080926/1222422115)
  * boost version is more short
* No scoped_ptr.

### Detection
* [official way](http://www.stroustrup.com/C++11FAQ.html#11)
* Use BOOST_NO_XXXX macro in boost.config

### function
* std::function
* how use member pointer
  * set first template argument type to class type

## Member pointer
* [example](http://ideone.com/SM00t)
* type: RetType(Klass::*field_name)(args...)
* instance reference calling: (instance_ref.*mem_ptr)(args)
* instance pointer calling: (instance_ptr->*mem_ptr)(args)

## [Application of std::basic_string](http://d.hatena.ne.jp/E_Mattsan/20091007/1254919101)
* it's purposed to concat but it can be used in defining user defined string type.

## EA STL
* STL from Electronics Art
* [Getting original EA STL](http://gpl.ea.com/nfsworld.html)
* It was closed until it was opened in 2010/10 with EAWebKit
* You can download original source code from [here](http://gpl.ea.com/)
* [Github repository](https://github.com/paulhodge/EASTL)
* Benchmark [1](http://msinilo.pl/blog/?p=668) [2](http://msinilo.pl/blog/?p=675)
* Has char8_t but just a typedef of char.
* Has many libraries from C++11
* Allocator design is great.
