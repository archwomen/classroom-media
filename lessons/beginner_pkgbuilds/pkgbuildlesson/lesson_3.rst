Non-make Packages
*****************

Overview
========

As we talked about in the earlier chapters, the usual route for building and
installing packages is::

    $ ./configure
    $ make
    # make install

but many packages do not follow this cycle. Python packages are usually one
example. There are even some that are simply pre-compiled binaries in an
archive. On the rare occasion that these packages comes with a `Makefile`,
then you are in luck. This chapter should help making distributable packages
without `make`.
