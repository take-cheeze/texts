* [OpenAL.org](http://openal.org/)
* [OpenAL Japanese translation](http://www.memorize-being.net/releases/oal11spec-ja/)
* A 3D audio library that was inspired by OpenGL
* OpenSL is the official Khronos library but OpenAL is more popular.
* `ALC_ALL_DEVICES_SPECIFIER`: list all devices
* [OpenAL Document](http://connect.creativelabs.com/openal/Documentation/OpenAL%201.1%20Specification.htm)
* [Reading audio files using libsndfile.](https://gist.github.com/take-cheeze/4233185)
* Streaming
  * [iOS](http://benbritten.com/2010/05/04/streaming-in-openal/)
  * [Example](http://sugarpot.sakura.ne.jp/yuno/?OpenAL%E3%82%B9%E3%83%88%E3%83%AA%E3%83%BC%E3%83%9F%E3%83%B3%E3%82%B0%E5%86%8D%E7%94%9F)
* [How to use buffer queues.](http://kcat.strangesoft.net/openal-tutorial.html)
* [SDL backend patch.](http://openal.996291.n3.nabble.com/PATCH-SDL-1-2-backend-for-OpenAL-Soft-td5390.html)
  * Not merged since initialization of SDL1 is difficult and the patch uses dynamic library loading.

## OpenAL Utility Toolkit
* [Document](http://connect.creativelabs.com/openal/Documentation/The%20OpenAL%20Utility%20Toolkit.htm)
* Context managing other utility.
* Supplement not like OpenGL

## [WebAL](https://github.com/benvanik/WebAL)
* javascript port of OpenAL

## [OpenAL Soft](http://openal-soft.org/)
* [Public repository](http://repo.or.cz/w/openal-soft.git)
* [config file writing](http://castle-engine.sourceforge.net/openal.php)
  * [config file path](http://repo.or.cz/w/openal-soft.git/blob/HEAD:/Alc/alcConfig.c#l208)
    * `/etc/openal/alsoft.conf`
    * `$HOME/.alsoftrc`
    * `$ALSOFT_CONF`
```
 [wave]
 file = /tmp/output.wav
```

### MIDI support
* Implemented as extension of OpenAL.
* [Basic information about MIDI extension.](http://openal.org/pipermail/openal/2014-January/000005.html)
* Needs to get function pointers with `alcGetProcAddress`.
* The unit of clock is changed to **micro-second** to **nano-second** after the mail.
* [Using fluidsynth directly instead of extension.](https://gist.github.com/take-cheeze/43f026d07547b9399738)
