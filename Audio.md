* [Real time audio](http://www.rossbencina.com/code/real-time-audio-programming-101-time-waits-for-nothing)
* "glitch" means interrupt or break of sound
* [OpenSL](http://www.khronos.org/registry/sles/)
* [audio processing in C (book)](http://floor13.sakura.ne.jp/book03/book03.html)

## [Julius](http://julius.sourceforge.jp/)
* large vocabulary continuous speech recognition

## Conversion
* [many types](http://en.linuxreviews.org/HOWTO_Convert_audio_files)
* MIDI
  * using fluidsynth
    * [http://wootangent.net/2010/11/converting-midi-to-wav-or-mp3-the-easy-way/]
```
 fluidsynth -F out.wav /usr/share/sounds/sf2/FluidR3_GM.sf2 myfile.mid

```
    * [2 step version](http://music.columbia.edu/pipermail/linux-audio-user/2006-December/040654.html)
```
 fluidsynth -i -a file <sound font> <midi>
 sox -r 44100 -w -c 2 -s fluidsynth.raw fluidsynth.wav

```
  * using timidity
    * [changing output type](http://wiki.livedoor.jp/cafeboy1/d/TiMidity%20%A4%CE%BB%C8%A4%A4%CA%FD%20%3A%3A%20%B2%BB%B8%BB%CA%D1%B4%B9)
```
 timidity /path/to/midi/file/.mid -Ow -o /path/to/output/file/.wav

```
* ogg
  * use '''oggenv''' to convert wave to ogg

## [OpenAL](http://connect.creativelabs.com/openal/default.aspx)
* [OpenAL Japanese translation](http://www.memorize-being.net/releases/oal11spec-ja/)
* A 3D audio library that was inspired by OpenGL
* OpenSL is the official Khronos library but OpenAL is more popular.
* ALC_ALL_DEVICES_SPECIFIER: list all devices
* [OpenAL Document](http://connect.creativelabs.com/openal/Documentation/OpenAL%201.1%20Specification.htm)
* OpenAL Utility Toolkit
  * [Document](http://connect.creativelabs.com/openal/Documentation/The%20OpenAL%20Utility%20Toolkit.htm)
  * Context managing other utility.
  * Supplement not like OpenGL
* [WebAL](https://github.com/benvanik/WebAL)
  * javascript port of OpenAL
* Streaming
  * [iOS](http://benbritten.com/2010/05/04/streaming-in-openal/)
  * [Example](http://sugarpot.sakura.ne.jp/yuno/?OpenAL%E3%82%B9%E3%83%88%E3%83%AA%E3%83%BC%E3%83%9F%E3%83%B3%E3%82%B0%E5%86%8D%E7%94%9F)
* [config file writing](http://castle-engine.sourceforge.net/openal.php)
  * [config file path](http://repo.or.cz/w/openal-soft.git/blob/HEAD:/Alc/alcConfig.c#l208)
    * /etc/openal/alsoft.conf
    * $HOME/.alsoftrc
    * $ALSOFT_CONF
```
 [wave]
 file = /tmp/output.wav

```
* [OpenAL Soft](http://openal-soft.org/)
  * [Public repository](http://repo.or.cz/w/openal-soft.git)
* reading ogg
  * [http://www.gamedev.net/topic/609666-streaming-ogg-files-with-openal/]
  * [example](https://gist.github.com/611624)
  * [http://www5.ocn.ne.jp/~tane/prog/oggplayer/oggplayer.html]
  * [java implementation](http://jogamp.org/joal-demos/www/devmaster/lesson8.html)
  * [using source queue](http://devmaster.net/posts/2895/openal-lesson-8-oggvorbis-streaming-using-the-source-queue)
* [reading wave file](http://kcat.strangesoft.net/openal-tutorial.html)
* [ruby bindings](https://rubygems.org/gems/ruby-openal)

## MIDI
* Score for synthesizers.
* Timidity and FluidSynth is a popular free software synthesizer.
* Needs sound font to play in software synthesizer.
* [Tick](http://www.blitter.com/~russtopia/MIDI/~jglatt/tech/midispec/tick.htm)
* [Example API](http://www.sjbaker.org/wiki/index.php?title=MIDIfile_player_library_API)
* [rpg maker xp](http://mimikopi.nomaki.jp/domino/rpgxp/index.html)

### Library
* [The Synthesis ToolKit in C++ (STK)](https://ccrma.stanford.edu/software/stk/)

### RPG Maker
* [RPG Maker XP midi](http://mimikopi.nomaki.jp/domino/rpgxp/index.html)

### Sound Font
* [Spec](http://www.synthfont.com/sfspec24.pdf)
* [fluidsynth sound font](http://sourceforge.net/apps/trac/fluidsynth/wiki/SoundFont)

### File Format
* Major format is SMF(Standard MIDI Format)
* [Standard File Format](http://home.roadrunner.com/~jgglatt/tech/midifile.htm)
* [Standard MIDI File format](http://www.omnibase.net/smf/)
* [MIDI message](http://www.midi.org/techspecs/midimessages.php)
* [Japanese SMF spec](http://www2s.biglobe.ne.jp/~yyagi/material/smfspec.html)
* [Japanese SMF spec 2](http://mofo.pns.to/wibs/?#63)

#### Chunk
```
 struct Chunk {
   char ID[4];
   uint32_t size;
   uint8_t data[size];
 };

```

### Timidity
* [Home page](http://timidity.sourceforge.net/)
* [Latest Timidity](http://bluewing.usamimi.info/timidity/index.php)
* [Timidity for Mac](http://www.asahi-net.or.jp/~gb7t-ngm/timidity.old/index.html)
* [Timidity for Mac OS X](https://github.com/albertz/timidity-macosx)
* [Mailing list](http://sourceforge.net/mail/?group_id=64316)
* [Timidity++ document](http://timidity.s11.xrea.com/index.en.html)
* [Timidity repository](http://timidity.git.sourceforge.net/git/gitweb.cgi?p=timidity/timidity;a=summary)
* [Timidity and Sound Font](http://pohwa.adam.ne.jp/you/music/timidity.html)
* [arch linux page](https://wiki.archlinux.org/index.php/Timidity)

### FluidSynth
* [Document](http://fluidsynth.sourceforge.net/api/)

## Library
* [jdksmidi](https://github.com/jdkoftinoff/jdksmidi)
* [stk](https://ccrma.stanford.edu/software/stk/download.html)
* CFugue
  * [project page](http://cfugue.sourceforge.net/)
  * [document](http://gopalakrishna.palem.in/CFugue.html)

### [libsndfile](http://www.mega-nerd.com/libsndfile/)
* Library to read many type of audio file.
* [using it with OpenAL](https://gist.github.com/4233185)
* [Document](http://www.mega-nerd.com/libsndfile/api.html)
* [read/write example](http://haraita9283.blog98.fc2.com/blog-entry-233.html)

## MP3
* [using mp3lame](http://pf-j.sakura.ne.jp/program/tips/mp3lame.htm)
* Patent problem
  * [Copyright problem](http://www.law.co.jp/okamura/copylaw/mp3.htm)
  * [Patent problem](http://www.initialt.org/lame/patent.html)
  * Conclusion: Don't use MP3 in games or etc.., use OGG or other free format.

## OGG
* [document](http://xiph.org/ogg/doc/libogg/reference.html)
* [Ogg Vorbis tutorial](http://marupeke296.com/OGG_main.html)
* [vorbisfile document](http://xiph.org/vorbis/doc/vorbisfile/index.html)
* use vorbisfile to read ogg vorbis.

## FLAC
* Free Lossless Audio Codec
* similar to mp3
* [SIZE_MAX compile error](http://www.hydrogenaudio.org/forums/index.php?showtopic=89083)
  * [patch](http://sourceforge.net/p/flac/bugs/264/)
* [socket compile error](http://lists.gnu.org/archive/html/mingw-cross-env-list/2010-10/msg00101.html)

## WAV
* [file format](http://www.kk.iij4u.or.jp/~kondo/wave/)
* [file format](http://www.sonicspot.com/guide/wavefiles.html)

## Web Browser
* [node.js](http://blog.livedoor.jp/kotesaki/archives/1544696.html)
* [node.js server](http://stackoverflow.com/questions/3955103/streaming-audio-from-a-node-js-server-to-html5-audio-tag)
* [Internet explorer audio tag](http://blogs.msdn.com/b/ie_jp/archive/2011/08/12/10195042.aspx)
* [audio player using audio tag](http://ascii.jp/elem/000/000/525/525808/)
* [media element](http://www.html5.jp/tag/elements/media_elements.html)
* [html5audio

## SDL_mixer
* SDL based audio library.
* Has support of many file types.
* [http://hg.libsdl.org/SDL_mixer/ repository](http://www.html5audio.org/)

## ALmixer
* [Home Page](http://playcontrol.net/opensource/ALmixer/)
