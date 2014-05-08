* Simple Direct-media Layer
* Well ported media library. Most of the environment have SDL port.
* SDL 1.3 was renamed to SDL 2.0 because it has enough feature for it.(but still developing...)

# SDL 2.0
* zlib license
* [1.2 to 2.0 guide](http://wiki.libsdl.org/MigrationGuide)
* [API categories](http://wiki.libsdl.org/APIByCategory)
* [API list](http://wiki.libsdl.org/CategoryAPI)
* [SDL active event equivalent](http://stackoverflow.com/questions/19202867/sdl-activeevent-equivalent-in-sdl-2-0)

# Emitting Manual Event
* [SDL_Event structure](http://sdl.beuc.net/sdl.wiki/SDL_Event)
* [Pushing event to SDL event queue](http://sdl.beuc.net/sdl.wiki/SDL_PushEvent)
```C
 SDL_Event ev;
 /*
  * Write events to push in "ev"
  */
 BOOST_VERIFY(SDL_PushEvent(&ev) == 0);
```

# Links
* [SDL 1.2](http://www.libsdl.org/docs/html/)
* [SDL 1.3](http://www.libsdl.org/cgi/docwiki.cgi/SDL-1.3/SDL_API)
* [SDL_image](http://www.libsdl.org/projects/SDL_image/docs/SDL_image.html)
* [SDL_mixer](http://www.libsdl.org/projects/SDL_mixer/docs/SDL_mixer.html)
* [SDL_net](http://www.libsdl.org/projects/SDL_net/docs/SDL_net.html)
* [SDL_tff](http://www.libsdl.org/projects/SDL_ttf/docs/SDL_ttf.html)
* [Repositories](http://hg.libsdl.org/)
