Overview
========

This is a simple graph editor library for wxWidgets.


Building
========

Prerequisites
-------------

1. wxWidgets 3.1.2 or later.
1. Graphviz headers and libraries: tested with Graphviz 2.26 and 2.38.


Using Microsoft Visual Studio
-----------------------------

The solution file uses MSVS 2017 format, but previous MSVS 201x versions should
probably work as well -- they haven't been tested however.

1. Edit `build/graphviz.props` file and change GraphvizDir directory value to
   point to Graphviz installation directory (note that this value should be
   backslash-terminated).
1. Open `build/grapheditor.sln` and build it. Currently only 32-bit build is
   supported.
1. Run `graphtest` sample after setting the `WX_GRAPHTEST_DATA_DIR` environment
   variable to point to `samples/resources` directory to allow it finding its
   image files.


Using GNU Make
--------------

This works in any Unix-like environment providing the standard Unix tools such
as ar(1) and ranlib(1) as well as pkg-config, with `libgvc.pc` from Graphviz
being available, and wx-config.

Simply run `make -C build` to build, optionally specifying the following
variables on make command line:

- `DEBUG` may be set to 1 to build with debug info and without optimizations.
- `WX_CONFIG` may be set to the full path of `wx-config` if it's not in `PATH`.
- `WX_PORT`, `WX_SHARED` and `WX_VERSION` may be used to select a particular
   wxWidgets build if more than one are available.

Set `WX_GRAPHTEST_DATA_DIR` to the location of the directory containing the
resources when running `graphtest` after building, e.g.

    $ WX_GRAPHTEST_DATA_DIR=`pwd`/samples/resources ./build/out/graphtest
