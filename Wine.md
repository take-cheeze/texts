* Software that allows to run Windows application on non-Windows OS.
* The difference between ReactOS is that it isn't OS.
* [FAQ](http://wiki.winehq.org/FAQ)
* [repository](http://source.winehq.org/git/wine.git/)
* [MIDI device](http://kakurasan.ehoh.net/summary/mididev.sound.wine.html)
* [arch linux page](https://wiki.archlinux.org/index.php/Wine)

## Paths
* prefix
  * $WINEPREFIX
  * if $WINEPREFIX isn't set '~/.wine' is used instead
* "Z:" drive means root directory in unix

## Registry
* [wine registry file name](http://kakurasan.ehoh.net/summary/winereg.reg.wine.html)
* [wine wiki page](http://wine-wiki.org/index.php/Wine_Registry)
* [about format](http://wiki.winehq.org/RegistryFormat)
* [regedit guide](http://www.winehq.org/docs/wineusr-guide/using-regedit)
* [string parser](http://source.winehq.org/git/wine.git/blob?f=server/unicode.c)
* [registry parser](http://source.winehq.org/git/wine.git/blob?f=server/registry.c)

## Configuration
To use Japanese add
```
  export LANG="ja_JP.UTF-8"
  export LC_ALL=$LANG
  export LC_ALLLANG=$LANG
  export LC_CTYPE=$LANG

```

in your shell config.

## Tools
### winedbg
* wine debugger that can debug mingw program.
* [Reference](http://www.winehq.org/docs/winedev-guide/dbg-commands)