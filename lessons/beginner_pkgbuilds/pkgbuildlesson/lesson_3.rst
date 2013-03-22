Non-make Packages
*****************

Overview
========

As we talked about in the earlier chapters, the usual route for building and
installing packages is::

    $ ./configure
    $ make
    # make install

but many packages do not follow this cycle. Python packages are one
example. There are even some that are simply pre-compiled binaries in an
archive. On the rare occasion that these packages comes with a `Makefile`,
then you are in luck. This chapter should help making distributable packages
without `make`.

Languages
=========

Python
------

Python sources are a delicate thing. Many do not specify whether or not they
want python 3 or 2 to be used, and so this must be rectified with very
specific sed or awk commands. A lot of python packages include a
``setup.py`` script in the source. Usually this can be used to install to an
arbitrary location quite easily, as we can see in the build and package
section of pyalpm

.. code-block:: bash

    build() {
      cd ${srcdir}/${pkgname}-${pkgver}
      python setup.py build
    }

    package() {
      cd ${srcdir}/${pkgname}-${pkgver}
      python setup.py install --root=${pkgdir}
    }

The ``--root`` directive will generally allow you to specify a directory to
install, and if you're using it in a PKGBUILD, then you are going to want to
use the `pkgdir`.
