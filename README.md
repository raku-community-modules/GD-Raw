[![Actions Status](https://github.com/raku-community-modules/GD-Raw/actions/workflows/linux.yml/badge.svg)](https://github.com/raku-community-modules/GD-Raw/actions) [![Actions Status](https://github.com/raku-community-modules/GD-Raw/actions/workflows/macos.yml/badge.svg)](https://github.com/raku-community-modules/GD-Raw/actions)

NAME
====

GD::Raw - Low level language bindings to GD Graphics Library

SYNOPSIS
========

```raku
use GD::Raw;

my $fh = fopen("my-image.png", "rb");
my $img = gdImageCreateFromPng($fh);
LEAVE gdImageDestroy($_) with $img;

say "Image resolution is ", gdImageSX($img), "x", gdImageSX($img);
```

DESCRIPTION
===========

`GD::Raw` is a low level language bindings to LibGD. It does not attempt to provide you with an rakuish interface, but tries to stay as close to its `C` origin as possible.

LibGD is large and this module far from covers it all. Feel free to add anything your missing and submit a pull request!

FUNCTIONS PORTED TO RAKU
========================

Not all `libgd` functions are ported to Raku module `GD::Raw`. Here is the list of these functions, in the same order as the [libgd 2.3.3 documentation](https://libgd.github.io/manuals/2.3.3/files/preamble-txt.html)

Image Formats
-------------

[`gdImageBmpPtr`](https://libgd.github.io/manuals/2.3.3/files/gd_bmp-c.html#gdImageBmpPtr)

[`gdImageBmp`](https://libgd.github.io/manuals/2.3.3/files/gd_bmp-c.html#gdImageBmp)

[`gdImageCreateFromBmp`](https://libgd.github.io/manuals/2.3.3/files/gd_bmp-c.html#gdImageCreateFromBmp)

[`gdImageCreateFromGif`](https://libgd.github.io/manuals/2.3.3/files/gd_gif_in-c.html#gdImageCreateFromGif)

[`gdImageGdPtr`](https://libgd.github.io/manuals/2.3.3/files/gd_gd-c.html#gdImageGdPtr)

[`gdImageGifPtr`](https://libgd.github.io/manuals/2.3.3/files/gd_gif_out-c.html#gdImageGifPtr)

[`gdImageGif`](https://libgd.github.io/manuals/2.3.3/files/gd_gif_out-c.html#gdImageGif)

[`gdImageJpeg`](https://libgd.github.io/manuals/2.3.3/files/gd_jpeg-c.html#gdImageJpeg)

[`gdImageJpegPtr`](https://libgd.github.io/manuals/2.3.3/files/gd_jpeg-c.html#gdImageJpegPtr)

[`gdImageCreateFromJpeg`](https://libgd.github.io/manuals/2.3.3/files/gd_jpeg-c.html#gdImageCreateFromJpeg)

[`gdImageCreateFromPng`](https://libgd.github.io/manuals/2.3.3/files/gd_png-c.html#gdImageCreateFromPng)

[`gdImagePng`](https://libgd.github.io/manuals/2.3.3/files/gd_png-c.html#gdImagePng)

[`gdImagePngPtr`](https://libgd.github.io/manuals/2.3.3/files/gd_png-c.html#gdImagePngPtr)

[`gdImagePngPtrEx`](https://libgd.github.io/manuals/2.3.3/files/gd_png-c.html#gdImagePngPtrEx)

[`gdImageTiffPtr`](https://libgd.github.io/manuals/2.3.3/files/gd_tiff-c.html#gdImageTiffPtr)

[`gdImageWebpPtr`](https://libgd.github.io/manuals/2.3.3/files/gd_webp-c.html#gdImageWebpPtr)

[`gdImageWepbPtrEx`](https://libgd.github.io/manuals/2.3.3/files/gd_webp-c.html#gdImageWebpPtr)

Free Type Font Rendering
------------------------

[`gdFontCacheShutdown`](https://libgd.github.io/manuals/2.3.3/files/gdft-c.html#gdFontCacheShutdown)

[`gdImageStringFT`](https://libgd.github.io/manuals/2.3.3/files/gdft-c.html#gdImageStringFT)

[`gdFontCacheSetup`](https://libgd.github.io/manuals/2.3.3/files/gdft-c.html#gdFontCacheSetup)

[`gdFTUseFontConfig`](https://libgd.github.io/manuals/2.3.3/files/gdft-c.html#gdFTUseFontConfig)

`gd.c`
------

### Creation and Destruction

[`gdImageCreate`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageCreate)

[`gdImageCreateTrueColor`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageCreateTrueColor)

[`gdImageDestroy`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageDestroy)

### Color

[`gdImageColorExactAlpha`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageColorExactAlpha)

[`gdImageColorAllocate`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageColorAllocate)

[`gdImageColorResolve`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageColorResolve)

[`gdImageColorResolveAlpha`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageColorResolveAlpha)

### Pixels

[`gdImageSetPixel`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageSetPixel)

[`gdImageGetPixel`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageGetPixel)

[`gdImageGetTrueColorPixel`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageGetTrueColorPixel)

### Primitives

[`gdImageLine`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageLine)

[`gdImageString`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageString)

[`gdImageStringUp`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageStringUp)

[`gdImageArc`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageArc)

[`gdImageEllipse`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageEllipse)

[`gdImageFilledEllipse`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageFilledEllipse)

[`gdImageRectangle`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageRectangle)

[`gdImageFilledRectangle`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageFilledRectangle)

### Cloning and Copying

[`gdImageCopyResized`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageCopyResized)

[`gdImageCopyResampled`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageCopyResampled)

### Polygons

[`gdImagePolygon`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImagePolygon)

[`gdImageOpenPolygon`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageOpenPolygon)

[`gdImageFilledPolygon`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageFilledPolygon)

### Other

[`gdImageSetStyle`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageSetStyle)

[`gdImageSetThickness`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageSetThickness)

[`gdImageSetAntiAliased`](https://libgd.github.io/manuals/2.3.3/files/gd-c.html#gdImageSetAntiAliased)

`gd.h`
------

### Colour Decomposition

[`gdTrueColorGetAlpha`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdTrueColorGetAlpha)

[`gdTrueColorGetRed`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdTrueColorGetRed)

[`gdTrueColorGetGreen`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdTrueColorGetGreen)

[`gdTrueColorGetBlue`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdTrueColorGetBlue)

### Color Composition

[`gdTrueColorAlpha`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdTrueColorAlpha)

### Accessor Macros

[`gdImageSX`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdImageSX)

[`gdImageSY`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdImageSY)

[`gdImageColorsTotal`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdImageColorsTotal)

[`gdImageRed`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdImageRed)

[`gdImageGreen`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdImageGreen)

[`gdImageBlue`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdImageBlue)

[`gdImageAlpha`](https://libgd.github.io/manuals/2.3.3/files/gd-h.html#gdImageAlpha)

`gd_interpolation.c`
--------------------

[`gdImageScale`](https://libgd.github.io/manuals/2.3.3/files/gd_interpolation-c.html#gdImageScale)

[`gdImageRotateInterpolated`](https://libgd.github.io/manuals/2.3.3/files/gd_interpolation-c.html#gdImageRotateInterpolated)

[`gdImageSetInterpolationMethod`](https://libgd.github.io/manuals/2.3.3/files/gd_interpolation-c.html#gdImageSetInterpolationMethod)

`gd_version.c`
--------------

[`gdMajorVersion`](https://libgd.github.io/manuals/2.3.3/files/gd_version-c.html#gdMajorVersion)

[`gdMinorVersion`](https://libgd.github.io/manuals/2.3.3/files/gd_version-c.html#gdMinorVersion)

[`gdReleaseVersion`](https://libgd.github.io/manuals/2.3.3/files/gd_version-c.html#gdReleaseVersion)

[`gdExtraVersion`](https://libgd.github.io/manuals/2.3.3/files/gd_version-c.html#gdExtraVersion)

[`gdVersionString`](https://libgd.github.io/manuals/2.3.3/files/gd_version-c.html#gdVersionString)

gdFree
------

[`gdFree`](https://libgd.github.io/manuals/2.3.3/files/gdhelpers-c.html)

Image Filters
-------------

[`gdImageScatter`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageScatter)

[`gdImagePixelate`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImagePixelate)

[`gdImageNegate`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageNegate)

[`gdImageGrayScale`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageGrayScale)

[`gdImageBrightness`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageBrightness)

[`gdImageContrast`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageContrast)

[`gdImageColor`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageColor)

[`gdImageSelectiveBlur`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageSelectiveBlur)

[`gdImageEdgeDetectQuick`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageEdgeDetectQuick)

[`gdImageGaussianBlur`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageGaussianBlur)

[`gdImageEmboss`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageEmboss)

[`gdImageMeanRemoval`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageMeanRemoval)

[`gdImageSmooth`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageSmooth)

[`gdImageCopyGaussianBlurred`](https://libgd.github.io/manuals/2.3.3/files/gd_filter-c.html#gdImageCopyGaussianBlurred)

Built-in Fonts
--------------

[`gdGiantFont`](https://libgd.github.io/manuals/2.3.3/files/gdfontg-c.html)

[`gdLargeFont`](https://libgd.github.io/manuals/2.3.3/files/gdfontl-c.html)

[`gdMediumBoldFont`](https://libgd.github.io/manuals/2.3.3/files/gdfontmb-c.html)

[`gdSmallFont`](https://libgd.github.io/manuals/2.3.3/files/gdfonts-c.html)

[`gdTinyFont`](https://libgd.github.io/manuals/2.3.3/files/gdfontt-c.html)

Additional Functions
--------------------

`fopen` file management for graphic files

`fclose` file management for graphic files

`gdImageCreatePalette` is an alias of `gdImageCreate`.

VARIOUS ISSUES
==============

Memory Management
-----------------

When creating an in-memory image, some memory is allocated in GD. This memory is not automatically deallocated when the variable which refers to the image goes out of scope. To counter this possible memory leak, the simplest way is to use the `LEAVE` phaser and call function `gdImageDestroy` like this

```raku
my $img = gdImageCreateFromPng($fh);
LEAVE gdImageDestroy($_) with $img;
```

If a program creates several images, there will be a problem if the program reuses the `$img` variable. In this case, you cannot use the `LEAVE` phaser, you must call `gdImageDestroy` before creating the second image (and the third, and...)

```raku
my $img = gdImageCreateFromPng($fh1);
[...]
gdImageDestroy($img);
$img = gdImageCreateFromPng($fh2);
[...]
gdImageDestroy($img);
$img = gdImageCreateFromPng($fh3);
[...]
gdImageDestroy($img);
```

Or a simpler solution is to use different variables `$img1`, `$img2`, `$img3` and so on, and calling `gdImageDestroy` each time with the `LEAVE` phaser.

```raku
my $img1 = gdImageCreateFromPng($fh1);
LEAVE gdImageDestroy($_) with $img1;
[...]
my $img2 = gdImageCreateFromPng($fh2);
LEAVE gdImageDestroy($_) with $img2;
[...]
my $img3 = gdImageCreateFromPng($fh3);
LEAVE gdImageDestroy($_) with $img3;
[...]
```

When using a function `gdImage`*XXX*`Ptr` to fill a blob with graphic data, the memory management function is `gdFree`. Usually, the pointer has a very short lifespan. Once the blob has been generated by `blob-from-pointer`, the pointer is useless and can be fred immediately. A typical chunk of code would be:

```raku
use GD::Raw;
use NativeHelpers::Blob;

[...]

my int32 $size;
my $ptr  = gdImagePngPtr($im, $size);
my $blob = blob-from-pointer($ptr, elems => $size, type => Blob[int8]);
gdFree($ptr);
```

String Fonts
------------

When using functions `gdImageString` and `gdImageStringUp`, you can only use the built-in fonts `gdGiantFont`, `gdLargeFont`, `gdMediumBoldFont`, `gdSmallFont` and `gdTinyFont`. For the moment, you cannot load GD-formatted bitmap fonts.

SEE ALSO
========

Raku Module `GD`: [https://github.com/raku-community-modules/GD](https://github.com/raku-community-modules/GD)

C library: [https://libgd.github.io/](https://libgd.github.io/)

A few examples and a few development notes: [https://github.com/jforget/raku-sandbox-GD/](https://github.com/jforget/raku-sandbox-GD/)

AUTHORS
=======

  * Dagur Valberg Johannsson

  * Raku Community

COPYRIGHT AND LICENSE
=====================

Copyright 2013 - 2018 Dagur Valberg Johannsson

Copyright 2024, 2026 Raku Community

This library is free software; you can redistribute it and/or modify it under the Artistic License 2.0.

