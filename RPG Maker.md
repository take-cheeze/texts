* RPG developing tools.
* After XP has scripting system to program game.
* [kame soft](http://ytomy.sakura.ne.jp/)
  * script distribution site

# RPG Maker 95
* String encoding is "Windows-31J"
* Materials has prefix "A:¥Program Files¥RPGﾂｸｰﾙ95¥$(PROJECT_NAME)"
* Use little endian
* RPG file
  * Has signature "RPGツクール95" in it.
* eve%05d.dat
  * corresponds to each event.
  * always has EVE99999.DAT. Maybe some special event.
*.ATR
  * Defines of map data attributes?
  * Size is 0x100
  * Seems like only 0x05, 0x06, 0x0B, 0x0C, 0x00 is used.
* ITEM.DAT
  * Item data list?
  * Has 0x00 0x00 0x00 "string" pattern.
* strings.dat
  * text that is separated with '\n'
  * it seems like equivalent of rpg2k vocabulary

# RPG Maker 2000/2003
* [Analyze result](http://rpg2kdev.sue445.net/)
* [Clip board format](http://www.multimediaxis.de/threads/71-Detail-Wissen-und-Geheimnise-des-RPG-Makers-vorallem-f%C3%BCr-Erfahrene-Profis-lehrreich?p=2161714&viewfull=1#post2161714)
* [Someones personal research result](http://www007.upp.so-net.ne.jp/spas13/game.html).
* [name input screen](http://yado.tk/2k/03_ibekoma/340_namae_nyuuryoku/)
* [spec report](http://airs.s10.xrea.com/document)
* [ruby library](http://hossy.info/rpgdev/2k_save.php)
* [report](http://www007.upp.so-net.ne.jp/spas13/game.html)

## RunTime Package
* [Difference between 2000 and 2003](https://easy-rpg.org/wiki/development/rtp-database/migration-2000-2003)
* [List of RTP file](https://easy-rpg.org/wiki/development/rtp-database/2003-rtp)

## Time stamp format
* [Microsoft Access time stamp format](http://support.microsoft.com/kb/210276)
* [EasyRPG implementation](https://github.com/EasyRPG/Readers/blob/master/src/lsd_reader.cpp#L29)
* [Converting Microsoft Access timestamp to unix time](http://www.access-programmers.co.uk/forums/showthread.php?t=70481)
* Total seconds from 1970/01/01 00:00:00 is the Unix time
* Access begins from 1899/12/30 00:00:00 and add 1.0 per each day

# Font
*font-familiy
**sans-serif: gothic
**serif: mincho
*font-size
**11px
* [easyrpg exfont discussion](https://easy-rpg.org/forums/viewtopic.php?f=5&t=36&p=161&hilit=font)

# EasyRPG
* Open source clone of RPG Maker 2k/2k3
* Repository is hosted in [github](http://github.com/EasyRPG).
* IRC Channel is #easyrpg in freenode. The cannel is [logged](http://easy-rpg.org/irc/log/easyrpg/).
* [Player Document](https://easy-rpg.org/jenkins/job/EasyRPG_Documentation/ws/doc/index.html)
* [Readers Document](https://easy-rpg.org/jenkins/job/EasyRPG_Documentation/ws/lib/readers/doc/index.html)

## Font
*cache generated font
*ctx.font = '11px sans-serif'
*way to hide canvas element: $(canvas).hide()
*clipping, scissor:
**var p = new Path();
**p.rect(x,y,w,h);
**ctx.clip(p);
**// do drawing
**ctx.resetClip();

## EasyRPG Server
*project/
*.json
 <code>{
   name: must match with base name of the file
   description: About game, can be ignored
   type: github, git, zip, lha
   url: if type is github the format will be user/project
   access: access type. public, user only, private is available
 }
 
```
**get base path(path of ldb, lmt, lmu
*tmp/
**place to extract project
**in git "git clone proj.name name"
**extract file to make ldb, lmt, lmu to the top directory
*REST API
**/project
***only GET
***query parameters
****name: Project name
****type: database, maptree, mapunit is available
****index: used only if type is mapunit
****format: my default json, "lcf" is available
**/material
***only GET
***query parameters
****name: Project name
*****if not specified global material (like RTP) will be returned.
****type: material type
****material_name: material name
****format: jpg, bmp, png, xyz, and AV types
***exchange format if needed
**/archive
***only GET
***query parameters
****name: project name
***if type is archive zip, lha will be available
**/search
***query parameters
****q: search query.
***returns json array of
****{ name: "project", description: "blah blah" }
***if authenticated private and user only project will be also searched.
**/savedata
***GET/POST
***query parameter
****index: index of save data 1～
*****if "latest" last saved data will be used.
****name: project name
***to call this method user must be authenticated
**/view
***GET
***query parameter
****name: project name
***view project description
*server.go
**node.js is familiar to me but go this time
**authentication
***Use cookie?
***where to save session
****username, password hash, savedata
***way to send mail
***private project, user only project
**make data submittable
**RSS output

## RPG_RT
*first strike is only valid in normal attack

## NaCl
*Native Client support
*Remove filefinder

## rb_rpg_editor
*build GUI components from schema
*Type
**Integer: SpinBox
**Enumeration: ComboBox
***Only selection
**String: TextCtrl
**Material: ComboBox
***Warnings to unused material
***Material type
***Timing to update material list
****When material was imported
****When project was loaded(including startup of the executable)
***behavior of copy pasting
**2d array: ListBox or ComboBox
***When selected element is changed, view must be updated
***sort elements with reference frequency
**1d array: QTabWidget or Widget
***In database use tabwidget
*range of integer
**Use range of variable by default
**Difference in 2k and 2k3
*meta field
**min/max: range of integer
**material_type: material type, if defined it is material
**element_list
***used in enumeration
***Array and map can be used.
**specialization: Specialized class name
***Exp curve, map data
**is_lenthof: length of array, can be ignored in build
*build_from_schema(schema, val)
**val: json value, by default skip it
*Search engine
**variable
**switch
**material
*multiple project
*Backup periodically by using QTimer
*Translation
**json of structure similar to schema
**array will be map with key name field
***[{children}](name,)
**Add "improve translation" button
*RPG Maker XP/VX/VX Ace editor
*Text Editor using QScintilla
*Project template
*Changelog will be push in json stack
**Version management
**reduce memory use
**track save data
*When projected is loaded list all available material
**Use recursion to list material
*json2lcf
**done
**in librpg2k
*mruby SWIG
*Use json in librpg2k schema
**remove meta field
  * [picojson](https://github.com/kazuho/picojson)
***use boost::flyweight to reduce memory use of string
***use AssocVector/boost::flat_map to speedup and reduce memory use