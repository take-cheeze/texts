* [photoshop 1.0 source code](http://computerhistory.org/atchm/adobe-photoshop-source-code/)

==Image Processing==
* [HSV and RGB](http://www.technotype.net/tutorial/tutorial.php?fileId=%7BImage%20processing%7D&sectionId=%7B-converting-between-rgb-and-hsv-color-space%7D)
* [mathematic HSV and RGB tutorial](http://hooktail.org/computer/index.php?RGB%A4%AB%A4%E9HSV%A4%D8%A4%CE%CA%D1%B4%B9%A4%C8%C9%FC%B8%B5)
* [tutorial](http://koujinz.cocolog-nifty.com/blog/2009/04/post-b8e6.html)
* [alpha blending](http://en.wikipedia.org/wiki/Alpha_compositing#Alpha_blending)
* [CImg](http://cimg.sourceforge.net/)
  * image processing library of C++ mess
  * too big, no generic things
* [IPL](https://github.com/Argoday/IPL)
* [DevIL](http://openil.sourceforge.net/)

===Cairo===
* open source 2d vector image library
* [manual](http://www.cairographics.org/manual/)
* [ruby binding](http://jp.rubyist.net/magazine/?0019-cairo)

===Resizing===
* [popular algorithms](http://emaame.com/20080901.html)
* [http://imagingsolution.blog107.fc2.com/blog-entry-142.html]

===OpenCV===
* [stllcv](https://sourceforge.net/projects/stllcv/)
  * C++ opencv wrapper
  * [document](http://www2s.biglobe.ne.jp/~niitsuma/STLLCV/)

===Boost.GIL===
* generic, generic, generic image processing library included in boost
* no libraries needed
* [document](http://www.boost.org/doc/libs/release/libs/gil/doc/html/index.html)
* [Japanese document](https://sites.google.com/site/twinkleofsilence/)
* [Japanese tutorial of GIL](http://mglab.blogspot.jp/2011/02/boostgil.html)
* [examples](http://sssm.sakura.ne.jp/dev/gil.html)
* [examples](http://www25.atwiki.jp/guru/pages/36.html)
* [example](http://d.hatena.ne.jp/yotto-k/20060809/)
* [hsvfilter example](http://d.hatena.ne.jp/tt_clown/20111208/boost_gil_hsvfilter)
  * not generic gil code
* [creating OpenGL texture](http://d.hatena.ne.jp/Sigureya/20120628/1340876912)
* [gil and opengl](https://groups.google.com/forum/?fromgroups=#!topic/boost-list/Omqym3TU3P0)
* [IO tutorial](http://d.hatena.ne.jp/tsurushuu/20080723/1216783641)
* [alpha blending headers](https://github.com/gununu/gilblend)
  * [document](https://github.com/gununu/gilblend/wiki)
* [adobe project page](https://sourceforge.net/projects/genimglib.adobe/)
* [bicubic](http://grayhole.blogspot.jp/2009/04/boostgil-bicubic.html)

==Geotag==
* Information of where the Photo was taken.
* Maybe used to stalk people from Internet.
* [removing geotag with Picasa](http://support.google.com/picasa/bin/answer.py?hl=en&answer=43899)

==Pixel arts converter==
* Since the power of hardware is enough for big image it needs to be converted to that can scale.

===hqx===
* Scaling algorithm by Maxim Stepin.
* has hq2x, hq3x, hq4x
* uses nearest-neighbor scaling.
* [repository](https://code.google.com/p/hqx/)
* [Wikipedia page](http://en.wikipedia.org/wiki/Hqx)
* [demo page](http://www.hiend3d.com/demos.html)

===Depixelizing pixel art===
* [Microsoft publication](http://research.microsoft.com/en-us/um/people/kopf/pixelart/)
* better algorithm than hqx.

==File format==
* Binary data to store image data.

===SVG===
* popular vector image format.
* used in web standard.

===GIF===
* [GIFLIB](http://wwwcdf.pd.infn.it/libgif/index.html)
* Had patent problem.
* The only image format that has animation feature that works.
  * So animated image file is called "GIF image"

===PNG===
* [libpng](http://www.libpng.org/pub/png/)
  * Popular library to manipulate PNG
* [libpng Document](http://www.libpng.org/pub/png/libpng-manual.html)
* [Japanese Translation of libpng.txt](http://dencha.ojaru.jp/programs_07/pg_graphic_10_libpng_txt.html)
* [png-1.2 format](http://www.libpng.org/pub/png/spec/1.2/png-1.2-pdg.html)

====Using manual output====
```
 static void write_data(png_structp out_ptr, png_bytep data, png_size_t len) {
   reinterpret_cast<std::ostream*>(png_get_io_ptr(out_ptr))->write(
     reinterpret_cast<char const*>(data), len);
 }
 static void flush_stream(png_structp out_ptr) {
   reinterpret_cast<std::ostream*>(png_get_io_ptr(out_ptr))->flush();
 }
 
 png_structp out = /* create png_struct */
 png_set_write_fn(out, &ostream_ptr, &write_data, &flush_stream);
 
 /* write data */
```

====Using manual input====
```
 static void read_data(png_structp in_ptr, png_bytep data, png_size_t len) {
   reinterpret_cast<std::istream*>(png_get_io_ptr(in_ptr))->read(
     reinterpret_cast<char*>(data), len);
 }
 
 png_structp in = /* create png_struct */
 png_set_read_fn(out, &ostream_ptr, &read_data);
 
 /* read data */
```

===BMP===
* Format used in old Windows.
* It doesn't have good compression so the file gets big

===TIFF===
* [libtiff](http://www.libtiff.org/)

===JPEG===
* Well used loss compression image format.
* Uses discrete cosine transform to compress.