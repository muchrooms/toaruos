![Screenshot](http://i.imgur.com/z1aFy0C.png)
![More Screenshots](http://i.imgur.com/g3zclG2.png)

# ToAruOS (とあるOS) #

とあるOS (ToAruOS) is a hobby operating system, built mostly from scratch, in development since December of 2010.

It was originally developed at the University of Illinois at Urbana-Champaign. For a period of time, it was the development focus of the university's [SIGOps](http://www.acm.uiuc.edu/sigops/) chapter.

Both the kernel and core userspace are included in this repository. Third-party sources are downloaded during the build process.

## IRC ##

For discussion, help with building or running the OS, and for up-to-date build verification, please join us in `#toaruos` on Freenode (`irc.freenode.net`).

## Features ##

The とある kernel provides a number of standard features, including:

* Processes and threads
  * The kernel supports loading of static ELF binaries
  * Threads are scheduled by the kernel
* Shared memory
* Pipes and TTYs
* Virtual file system
  * `/proc` implementation similar to Linux
  * `/dev` entries
  * EXT2 filesystem for disk access
* Signals
  * Delivery is asynchronous from sending
  * Processed immediately during next context switch into receiving process

The included userspace also provides:

* A number of standard Unix utilities
* A graphical interface
  * Composited window manager
  * Limited widget toolkit
* Terminal emulator
  * Some xterm compatibility, support for 256 color palette, etc.
  * Anti-aliased text with FreeType
  * General support for UTF-8

### Third-Party Software ###

とあるOS makes use of and supplies the following third-party packages:

* `libpng` - Used extensively by the native graphics library to provide wallpaper and icons.
* `zlib` - Dependency of `libpng`, but also generally useful.
* `freetype` - For rendering text using TrueType fonts.
* `cairo` and `pixman` - For accelerated and managed graphics.
* `ncurses` - Terminal control library, provides `terminfo`.
* Mesa - Implementation of OpenGL (only the software rasterizer is available).
* Vim - Popular text editor.

Additionally, a number of third-party software packages have been ported to とあるOS, but are not yet included in this distribution:

* Lua - Builds as-is
* MuPDF - See [klange/toaru-pdfviewer](https://github.com/klange/toaru-pdfviewer) (library must be cross compiled)
* SDL - See [klange/SDL](https://github.com/klange/SDL)
* `snes9x-sdl` - See [klange/snes9x-sdl](https://github.com/klange/snes9x-sdl)
* Bochs
* Python - in progress...

## Screenshots ##

For a historical look at とあるOS, please see [SCREENSHOTS.md](docs/SCREENSHOTS.md).

## Testing / Building / Installation ##

Please see [testing.md](docs/testing.md).

## References ##
Here are some tutorials we found useful early on:

* [James M's kernel development tutorials](http://www.jamesmolloy.co.uk/tutorial_html/index.html)
* [Bran's Kernel Development Tutorial](http://www.osdever.net/bkerndev/Docs/basickernel.htm)
* [Skelix's OS tutorial](http://skelix.net/skelixos/index_en.html)

## Licenses ##

### ToAruOS Itself ###

This project is released under the terms of the University of Illinois / NCSA Open Source License, an OSI- and FSF-approved, GPL-compatible open source license. The NCSA License is a derivative of the MIT license and the BSD license; it is reproduced here for your convenience:

    Copyright (c) 2011-2013 Kevin Lange.  All rights reserved.

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to
    deal with the Software without restriction, including without limitation the
    rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
    sell copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:
      1. Redistributions of source code must retain the above copyright notice,
         this list of conditions and the following disclaimers.
      2. Redistributions in binary form must reproduce the above copyright
         notice, this list of conditions and the following disclaimers in the
         documentation and/or other materials provided with the distribution.
      3. Neither the names of the ToAruOS Kernel Development Team, Kevin Lange,
         nor the names of its contributors may be used to endorse
         or promote products derived from this Software without specific prior
         written permission.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE
    CONTRIBUTORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
    FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
    WITH THE SOFTWARE.

### Third-Party Packages ###

ToAruOS contains a number of third-party packages and software. As the number of third-party packages in the OS has increased drastically, I have moved the licenses to [THIRDPARTY.md](docs/THIRDPARTY.md).
