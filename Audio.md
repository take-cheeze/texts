* [Real time audio](http://www.rossbencina.com/code/real-time-audio-programming-101-time-waits-for-nothing)
* "glitch" means interrupt or break of sound
* [OpenSL](http://www.khronos.org/registry/sles/)
* [audio processing in C (book)](http://floor13.sakura.ne.jp/book03/book03.html)
* [sox command document](http://sox.sourceforge.net/sox.html)

## [Julius](http://julius.sourceforge.jp/)
* large vocabulary continuous speech recognition

## Conversion
* [many types](http://en.linuxreviews.org/HOWTO_Convert_audio_files)
* MIDI
  * using fluidsynth
    * [http://wootangent.net/2010/11/converting-midi-to-wav-or-mp3-the-easy-way/]
    * `fluidsynth -F out.wav /usr/share/sounds/sf2/FluidR3_GM.sf2 myfile.mid`
    * [2 step version](http://music.columbia.edu/pipermail/linux-audio-user/2006-December/040654.html)
```
 fluidsynth -i -a file <sound font> <midi>
 sox -r 44100 -w -c 2 -s fluidsynth.raw fluidsynth.wav
```
  * using timidity
    * [changing output type](http://wiki.livedoor.jp/cafeboy1/d/TiMidity%20%A4%CE%BB%C8%A4%A4%CA%FD%20%3A%3A%20%B2%BB%B8%BB%CA%D1%B4%B9)
 * `timidity /path/to/midi/file/.mid -Ow -o /path/to/output/file/.wav`
* ogg
  * use `oggenv` to convert wave to ogg
* [Using fluidsynth and sox command to convert MIDI to WAV.](http://stackoverflow.com/questions/19762063/convert-midi-file-to-wav-using-fluidsynth-on-os-x)

## Library
* [jdksmidi](https://github.com/jdkoftinoff/jdksmidi)
* [stk](https://ccrma.stanford.edu/software/stk/download.html)
* CFugue
  * [project page](http://cfugue.sourceforge.net/)
  * [document](http://gopalakrishna.palem.in/CFugue.html)

### [libsndfile](http://www.mega-nerd.com/libsndfile/)
* Library to read many type of audio file.
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
