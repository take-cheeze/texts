* [libapril](http://sourceforge.net/projects/libapril/)
  * graphics library wrapper
* [Regal for NaCl](http://www.altdevblogaday.com/2012/09/04/bringing-regal-opengl-to-native-client/)

## Pass Tracing
* [smallpt](http://www.kevinbeason.com/smallpt/)
  * [repository](https://github.com/munificent/smallpt)
  * [js implementation](http://create.stephan-brumme.com/smallpt-js/)
* [edupt](http://kagamin.net/hole/edupt/index.htm)
  * [repository](https://github.com/githole/edupt)
  * [slide](http://www.slideshare.net/h013/edupt-kaisetsu-22852235)


## Pixman
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
