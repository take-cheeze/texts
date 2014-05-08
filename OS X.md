* OS used in Apple Intel hardware.
* [Darling](http://darling.dolezel.info/en/Darling)
  * emulation layer for OS X
  * like wine in Windows
  * [maloader for dynamic loader?](https://github.com/shinh/maloader)
* [user global environment variable](http://news.mynavi.jp/column/osxhack/083/index.html)
* [creating ram disk](http://blog.dateofrock.com/2010/02/osxram.html)

# [maloader](https://github.com/shinh/maloader)
* [Mach-O and maloader](http://d.hatena.ne.jp/shinichiro_h/touch/20110428/1304002959)
* [slide](http://shinh.skr.jp/slide/ldmac/000.html)
* [article](http://d.hatena.ne.jp/shinichiro_h/touch/20110316#1300238828)
* used in darling

# App Bundle
* [app bundle structure](https://developer.apple.com/library/mac/documentation/CoreFoundation/Conceptual/CFBundles/BundleTypes/BundleTypes.html#//apple_ref/doc/uid/10000123i-CH101-SW19)
* [documentation](https://developer.apple.com/library/mac/documentation/CoreFoundation/Conceptual/CFBundles/Introduction/Introduction.html)
* [building app bundle yourself](http://stackoverflow.com/questions/1596945/building-osx-app-bundle)
* structure
  * App.app/
    * Contents/
      * Info.plist
      * MacOS/
        * App (executable)
      * Resources/

# Specific command
* purge
  * OS X command to release not used memory.
* [Window screenshot](http://blog.goo.ne.jp/vallie/e/bf986a23f617dde56ac9c9e11df0c6c8)
  * ⌘ + Shift + 4, Space and select
* [install_name_tool](https://developer.apple.com/library/mac/documentation/Darwin/Reference/Manpages/man1/install_name_tool.1.html)
  * tool to change shared library path
* [macdylibbundler](http://macdylibbundler.sourceforge.net/)
  * command to embed shared libraries to app bundle
  * written in c++
  * use install_name_tool internally
  * can be installed with macports