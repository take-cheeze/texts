## Bitmap Distribution Format (BDF)
* Bitmap font format by Adobe.
* [Wikipedia page.](http://en.wikipedia.org/wiki/Glyph_Bitmap_Distribution_Format)
* [Japanese article about BDF](http://hp.vector.co.jp/authors/VA013241/font/bdf.html)
* [Cyrillic fonts in X.org](http://rasher.dk/rockbox/fonts/cyrillic/)
* Origin is lower left corner.
* The bit order is same as freetype.

## Calculating Point
* [freetype guide](http://www.freetype.org/freetype2/docs/glyphs/glyphs-2.html)
* resolution Dot per inch(DPI)
```
 pixel = point * resolution / 72;
```
* [where 96dpi came from](http://en.wikipedia.org/wiki/Dots_per_inch#Computer_monitor_DPI_standards)
```
 72 * (1 + 1/3) = 96
```

## Freetype
* Free font engine
* [API Reference](http://www.freetype.org/freetype2/docs/reference/ft2-index.html)

### Mono bitmap
* [printing bitmap](http://ncl.sakura.ne.jp/doc/ja/comp/freetype-memo.html)
* 0x80 means that most left pixel of this octed is true.
* 0x01 means that most right pixel of this octed is true.
```C
 FT_Bitmap *bm = &face->glyph->bitmap;
 int row, col, bit, c;

 for (row = 0; row < bm->rows; row ++) {
     for (col = 0; col < bm->pitch; col ++) {
         c = bm->buffer[bm->pitch * row + col];
         for (bit = 7; bit >= 0; bit --) {
             if (((c >> bit) & 1) == 0)
                 printf("  ");
             else
                 printf("##");
         }
     }
     printf("\n");
 }
```

* Little big.

## Family name
* Sans-serif: Gothic
* Serif: Mincho

## IPA Font
* [Download page](http://ossipedia.ipa.go.jp/ipafont/index.html)
* Free true type/open type font.

## Shinonome font
* [Download page](http://openlab.ring.gr.jp/efont/shinonome/)
* Free bitmap font.
* "bfd" format is used.
