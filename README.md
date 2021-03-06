# tad - multidimensional arrays in C++

Tagged Array Data (TAD) is a library to make working with multidimensional
arrays in C++ easy.

For example:
```c++
TAD::Array<uint8_t> image({ 640, 480 }, 3);
image[{ x, y }][0] = redValue;
image[{ x, y }][1] = greenValue;
image[{ x, y }][2] = blueValue;
TAD::save(image, "image.png");
```

Iterators are provided, so you can use STL algorithms on TAD arrays, e.g.
`std::for_each`, `std::sort` etc. You can also apply custom functions, functors,
or lamba expressions to array contents in a single line of code.

The core TAD library is header-only; you just include `<tad/array.hpp>`.

For input and output you can optionally link against libtad. This library
supports various file formats including png, jpeg, tiff, exr, hdr, DICOM, hdf5,
pdf, pfs, pfm, ppm, fits, CSV, and the native (and therefore very fast) tad
format. It can be built without any external libraries, but then only supports
a few core file formats.

There is also a command line utility named `tad` that can create, convert and
modify files in supported formats, and print information about them. The `tad`
utility does not require any external libraries either, but can use the muparser
library for its `calc` command.

This project uses the MIT license.
