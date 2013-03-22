Dependencies
************

Overview
========

In a ``PKGBUILD`` there are three types of dependencies:

* Standard dependencies
* Make dependencies
* Check dependencies

Each is crucial for a different part of the build, and they are specified
separately in the ``PKGBUILD``. Standard dependencies are those needed to
run the software after it is built. These, specified in the ``depends``
array, are handled by pacman when you or someone else installs the package.

The other two dependencies are only required for building the package. As is
probably evident, the make dependencies are needed for the build function
when running make. Sometimes binaries need to link against some particular
software to have a feature, so you would specify them in the ``makedepends``
array. Check dependencies are ones that are exclusively needed for the
check function.

.. note::
    Packages in the ``base-devel`` group do not need to be included in any
    of the dependency arrays. It is assumed that these are installed on
    systems running `makepkg`.

Know that finding dependencies may be completely different from what is
explained in this chapter. While some of these tools may come in handy, it
is up to you to figure out when they are appropriate.

Tools
=====

pkgfile
-------

One of the more useful tools in any Arch Linux packager's belt, `pkgfile`_
uses the ``.files`` databases created by ``repo-add`` to find what package a
file is in. When combined with other tools, this can very succinctly tell
you what exact packages are needed for everything to work right. There are
options that allow you to use shell globing patterns, directories and more
for finding packages. For more information, you can install `pkgfile` with a
simple:

    # pacman -Syu pkgfile

and read the manual page.

.. _pkgfile: https://wiki.archlinux.org/index.php/Pkgfile

ldd
---

When creating C or C++ packages, there is an excellent tool called `ldd`.
It is part of the GNU C Library, and should be on almost every machine.
According to the info manual, `ldd` prints the shared library dependencies
of a binary. Running it after you build the software is as simple as::

    $ ldd /path/to/binary

Here is an example running `ldd` on the grep binary we created in the last
chapter::

    $ ldd /path/to/grep
          linux-vdso.so.1 (0x00007fff8fffe000)
          libpcre.so.1 => /usr/lib/libpcre.so.1 (0x00007f035d155000)
          libc.so.6 => /usr/lib/libc.so.6 (0x00007f035cda8000)
          libpthread.so.0 => /usr/lib/libpthread.so.0 (0x00007f035cb8c000)
          /lib64/ld-linux-x86-64.so.2 (0x00007f035d3b8000)

As you can see, it is somewhat cryptic, but once you know how to use it, the
output is extremely meaningful. Using `pkgfile`, we can find out exactly
what package we need to include to make that binary work on a system. For
example, say I want to know what package has the file ``libacl.so.1``, one
would simply run::

    $ pkgfile libpcre.so.1
    core/pcre

.. note::
    On systems with the multilib repository enabled, you may see packages in
    the multilib repository and core, community and extra. Unless the
    software you are building does not support a 64-bit architecture, then
    it is best not to use those packages in any depends array.

This would tell me that in the `grep` project should depend on core/acl, and if
you look at the ``pacman -Si grep`` output, you will see that it does in fact
depend on this package. You can go through all of the `.so` files and find
all of the dependencies, but sometimes even that is not enough for some
packages. `grep` also depends on `sh`, as it is a shell program. Most of the
time, you can expect this to be installed from the `base`_ group, but it's
not always the case with some things, and some are not even C programs.

Investigation
=============

Almost all reputable sources will include a README file of some kind.
Sometimes these go by different names, but there is almost always one in the
root of the archive directory. Sometimes, subdirectories have their own.

In these files you can find installation instructions, license information,
pretty much whatever the author decides to tell you about the software. What
we are interested in here are the dependency lists. Many times packages will
not list files, but will actually list packages for a specific distribution.
If you happen to see things like this, then the distributions online package
database will come in handy. Sometimes the names are similar to Arch
packages, sometimes not. It all depends. Once you find out exactly what
files are depended on, then you can go about running `pkgfile`.

.. note::
    Generally packages use Ubuntu or Debian packages in the README.

Another way to figure out depends is, if you know the language the package
is written in, to simply read the source files.

Investigating and testing are usually the only ways to get the makedpends
and checkdepends for a package. Read the error messages that are printed,
and pay attention.


.. links
.. _base: https://www.archlinux.org/groups/i686/base/
