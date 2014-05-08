* [libapril](http://sourceforge.net/projects/libapril/)
  * graphics library wrapper
* [Regal for NaCl](http://www.altdevblogaday.com/2012/09/04/bringing-regal-opengl-to-native-client/)

# Pass Tracing
* [smallpt](http://www.kevinbeason.com/smallpt/)
  * [repository](https://github.com/munificent/smallpt)
  * [js implementation](http://create.stephan-brumme.com/smallpt-js/)
* [edupt](http://kagamin.net/hole/edupt/index.htm)
  * [repository](https://github.com/githole/edupt)
  * [slide](http://www.slideshare.net/h013/edupt-kaisetsu-22852235)

# OpenGL
* General rendering API.
* No image file to texture loading function so you need to make or have the rest of functions you need.
* [Tutorial](http://marina.sys.wakayama-u.ac.jp/~tokoi/oglarticles.html)
* [glDrawArrays sample](http://wiki.livedoor.jp/mikk_ni3_92/d/glDrawArrays%A4%CB%A4%E8%A4%EB%C9%C1%B2%E8)
* [waving texture](http://nehe.gamedev.net/tutorial/flag_effect_(waving_texture)/16002/)
* [SOIL](http://www.lonesock.net/soil.html)(Simple OpenGL Image Library)
  * png/bmp to OpenGL texture

## EGL
* interface betweem OpenGL API
* [EGL and EAGL](http://db-in.com/blog/2011/02/khronos-egl-and-apple-eagl/)
* [EGL tutorial](https://sites.google.com/site/learningopengl/eglbasics)

## Data type
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

## OpenGL ES
* Embed purpose OpenGL API.
* Mostly in iOS, Android, Browser GL API
* Removal of glBegin/glEnd was good a decision.
* From 2.0 fixed function pipeline is removed and only shaders are used for effects.
* [OpenGL ES 1.1](http://www.khronos.org/opengles/sdk/1.1/docs/man/)
* [OpenGL ES 2.0](http://www.khronos.org/opengles/sdk/docs/man/)
* [OpenGL ES 3.0](http://www.khronos.org/opengles/sdk/docs/man3/)
* [GLSL ES](http://www.khronos.org/opengles/sdk/docs/manglsl/)
* [EGL reference](http://www.khronos.org/registry/egl/sdk/docs/man/xhtml/)
  * [EGL and EAGL](http://db-in.com/blog/2011/02/khronos-egl-and-apple-eagl/)
  * [Tutorial](https://sites.google.com/site/learningopengl/eglbasics)
* [angelproject](https://code.google.com/p/angleproject/)
  * OpenGL ES 2.0 implementation for WebGL
  * used in Chromium and FireFox

## GLSL
* Spec of OpenGL's Shader Language.
* [GLSL data type](http://www.opengl.org/sdk/docs/manglsl/)
* [GLSL data type](http://www22.atwiki.jp/opengles/pages/9.html)
* GLSL optimizer
  * Using MESA(Open Source OpenGL implementation)
  * [article](http://aras-p.info/blog/2010/09/29/glsl-optimizer/)
  * [repository](https://github.com/aras-p/glsl-optimizer)

## GLEW
* OpenGL Extension Wrangler library
* [home page](http://glew.sourceforge.net/)
* [examples](http://imd.naist.jp/~fujis/cgi-bin/wiki/index.php?GLEW%A4%CB%A4%C4%A4%A4%A4%C6)

# Pixman
* PIXel MANipulation library
* Software rendering backend.
* [repository](http://cgit.freedesktop.org/pixman/)
* [pixman.h](http://cgit.freedesktop.org/pixman/tree/pixman/pixman.h)
* [Writing png from pixman_image_t](http://cgit.freedesktop.org/pixman/commit/?id=99a53667da3014a463b8a0e2b6c317efe0ebb220)
  * before saving to PNG it renders to PIXMAN_a8r8g8b8 image
* [Fixing SIZE_MAX error](http://comments.gmane.org/gmane.comp.graphics.pixman/2133)
  * SIZE_MAX is not in standard(?)
* pixman_image_create_bits
  * clears bits when NULL pointer is passed
  * to skip clearing use _no_clear function
* [operators](http://cairographics.org/operators/)
  * document of cairo