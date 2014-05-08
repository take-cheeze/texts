* stands for Ruby Game Scripting System
* [RGSS world](http://jp.rubyist.net/magazine/?0005-RGSS)
* After RPG Maker XP, RPG Maker use ruby as a script engine.
* Table Class
  * [Marshaling](http://d.hatena.ne.jp/mirichi/20091201/p2)
  * No clamp in each elements
* rxdata
  * Marshal.dump of ruby object
  * In root array 0th element is nil
  * Scripts.rxdata
    * <nowiki>data[= [some number, script name, deflated(use zlib) script data](index])</nowiki>
* reset(RGSS1/RGSS2)
  * http://www.tktkgame.com/tkool/memo/rgss/reset.html
  * http://www.tktkgame.com/tkool/memo/rgss/reset2.html
* [RGSS error handling](http://www5f.biglobe.ne.jp/~delusion/tech/text_004.html)
* [table class marshaling](http://d.hatena.ne.jp/mirichi/20090501/p4)

==Archive==
* encrypted game data archive
* referenced from load_data function, bitmap, audio
* [RGSSAD version 3](http://forum.xentax.com/viewtopic.php?p=77000#p77000)
  * now encryption key isn't fixed.

==RGSS1==
* [reference](http://k-du.de/rgss/)

==RGSS2==
* [reading map](http://d.hatena.ne.jp/mirichi/20120419/p1)

==RGSS3==
* [english document](http://fixato.org/rpgmaker/Manual/RPGVXAce/rgss/)
* use ruby 1.9 for script engine
  * can use Fiber
* [Review of VX Ace sample game creator](http://d.hatena.ne.jp/ktakaki/20111201/p1)
  * Fiber is used in game command loop.
* [Little reference](http://matome.naver.jp/odai/2133557964248369701)
* [VX tile ids](http://www.tktkgame.com/tkool/memo/vx/tile_id.html)
* [RGSS3 reference](http://ja.scribd.com/doc/95067279/RPG-Maker-VX-Ace-Help-RGSS3-Reference-Manual)

==rgss_script_editor==
* personal rgss script viewer(though it can edit) using Qt.
* uses QScintilla for editing script.
* [repository](https://github.com/take-cheeze/rgss_script_editor)

==mkxp==
* RGSS engine using mruby
* [repository](https://github.com/Ancurio/mkxp)

==ARGSS==
* [Project page](http://sourceforge.net/projects/argss/)
* Open Source RGSS clone
* Using library
  * OpenGL
    * No vertex arrays
    * No shaders
  * SDL
    * Timer API
    * Key input handling
  * SDL_mixer
  * SOIL
    * Simple OpenGL Image Library
    * Public Domain
    * Written in C
  * CRuby
    * Script engine
* Manage object with map<VALUE, obj*>
* Not good C++