* General rendering API.
* No image file loading function so you need to make or have the rest of functions you need.
* [Tutorial](http://marina.sys.wakayama-u.ac.jp/~tokoi/oglarticles.html)
* [glDrawArrays sample](http://wiki.livedoor.jp/mikk_ni3_92/d/glDrawArrays%A4%CB%A4%E8%A4%EB%C9%C1%B2%E8)
* [waving texture](http://nehe.gamedev.net/tutorial/flag_effect_(waving_texture)/16002/)
* [SOIL](http://www.lonesock.net/soil.html)(Simple OpenGL Image Library)
  * png/bmp to OpenGL texture
* [OpenGL Tutorial](http://open.gl/introduction)
* [blend funcs](http://d.hatena.ne.jp/melpon/20070824/p1)

## [GLM](http://glm.g-truc.net/)
* [repository](https://github.com/g-truc/glm)
* [document](http://glm.g-truc.net/api/index.html)

### EGL
* interface betweem OpenGL API
* [EGL and EAGL](http://db-in.com/blog/2011/02/khronos-egl-and-apple-eagl/)
* [EGL tutorial](https://sites.google.com/site/learningopengl/eglbasics)

### Data type
* GL_FIXED
  * [GL_FIXED](http://www.opengl.org/registry/specs/OES/OES_fixed_point.txt)
  * [GL_FIXED performance](https://groups.google.com/forum/?fromgroups=#!topic/android-ndk/KvHTF_ZtxGk)
  * [GL_FIXED in android](http://stackoverflow.com/questions/2903295/is-it-better-to-use-gl-fixed-or-gl-float-on-android)
* half float extension
  * [half float](http://en.wikipedia.org/wiki/Half-precision_floating-point_format)
  * [discussion](http://bytes.com/topic/c/answers/811019-half-floating-point-type)
  * [extension detail](http://oss.sgi.com/projects/ogl-sample/registry/ARB/half_float_pixel.txt)
  * [conversion](http://stackoverflow.com/questions/1659440/32-bit-to-16-bit-floating-point-conversion)
* [openexr](http://openexr.com/)
  * 16bit floating point number implementation

### OpenGL ES
* Embed purpose OpenGL API.
* Mostly in iOS, Android, Browser GL API
* Removal of glBegin/glEnd was good a decision.
* From 2.0 fixed function pipeline is removed and only shaders are used for effects.
* [OpenGL ES 1.1](http://www.khronos.org/opengles/sdk/1.1/docs/man/)
* [OpenGL ES 2.0](http://www.khronos.org/opengles/sdk/docs/man/bottom.php)
* [OpenGL ES 3.0](http://www.khronos.org/opengles/sdk/docs/man3/bottom.php)
* [GLSL ES](http://www.khronos.org/opengles/sdk/docs/manglsl/)
* [EGL reference](http://www.khronos.org/registry/egl/sdk/docs/man/xhtml/)
  * [EGL and EAGL](http://db-in.com/blog/2011/02/khronos-egl-and-apple-eagl/)
  * [Tutorial](https://sites.google.com/site/learningopengl/eglbasics)
* [angelproject](https://code.google.com/p/angleproject/)
  * OpenGL ES 2.0 implementation for WebGL
  * used in Chromium and FireFox

### GLSL
* Spec of OpenGL's Shader Language.
* [GLSL data type](http://www.opengl.org/sdk/docs/manglsl/)
* [GLSL data type](http://www22.atwiki.jp/opengles/pages/9.html)
* GLSL optimizer
  * Using MESA(Open Source OpenGL implementation)
  * [article](http://aras-p.info/blog/2010/09/29/glsl-optimizer/)
  * [repository](https://github.com/aras-p/glsl-optimizer)

### GLEW
* OpenGL Extension Wrangler library
* [home page](http://glew.sourceforge.net/)
* [examples](http://imd.naist.jp/~fujis/cgi-bin/wiki/index.php?GLEW%A4%CB%A4%C4%A4%A4%A4%C6)
