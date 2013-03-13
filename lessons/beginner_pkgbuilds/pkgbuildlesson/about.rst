About
*****

The Class
=========

Welcome to the **Beginners Guide to Package Maintaining Class**. This class
has been put together by Daniel Wallace and William Giokas in the hopes of
improving the current state of the AUR and other user package repositories.
Meant to be a full introduction to maintaining packages, we have split the
class into four lessons:

#. A Basic Introduction to the ``pacman`` and ``makepkg`` Utilities
#. Finding Dependencies
#. Building Packages Without ``make``
#. Development and VCS Packages

Coming out of this class, it is expected that you can:

* build your own package, and have it conform to the `Arch Linux Packaging
  Standards`_
* understand the basics of an Arch Linux package (``pkg.tar.xz`` file), and
  how pacman and makepkg deal with them
* identify the variables and functions used in PKGBUILDs
* build and maintain packages using version control sources such as `git`_
  or `mercurial`_

While it would be nice if we could teach people to do this who know nothing
of Linux or how to do basic tasks in a shell, it is somewhat required to
have a basic knowledge of:

* the Linux filesystem
* basic Linux commands (ls, cd, make, mkdir, install, etc.)
* archiving and un-archiving files
* text editors (vim, emacs, leafpad, geany, etc.)
* file and directory permissions

Students will also need an up-to-date Arch Linux installation and an
internet connection for certain parts of the class.

.. _Arch Linux Packaging Standards: https://wiki.archlinux.org/index.php/Arch_Packaging_Standards
.. _git: http://git-scm.com/
.. _mercurial: http://mercurial.selenic.com/

The Teachers
============

William Giokas
--------------

I began using Linux 4 years ago, with Ubuntu 9.04, and I used it on my
computer that was, even at the time, quite old. For about a year, I was
quite content to use it for most everything, but once I began learning the
inner workings of Linux, Ubuntu's unneeded hiding of basic system workings
got in the way. That was when I discovered Arch. After taking a few hours
testing it out in virtual machines and failing to install it a few too many
times, I got a working Arch setup on real hardware.

Being a complacent user was fine, for a time. I installed a few AUR
packages, screwed up installing things without makepkg/pacman, and generally
went around doing what most of the noobs who use Arch do: break things.
Things have changed, slightly. Now I break things in order to fix them, not
just out of a lack of knowledge.

As of this writing, I maintain 7 packages in the Unsupported repository,
also known as the AUR. I also keep a moderately up-to-date git repository of
the PKGBUILDs that I use, along with all of the terrible edits that I have
made to them. Over the past few months, I have sent in a `few patches`_
to the `pacman`_ project, most to the makepkg/contrib side of things.

On IRC I go by the nickname ``KaiSforza``, and on many other services. If
you have any questions about these lessons, please feel free to `email me`_.


Daniel Wallace
--------------

I began using Linux 3 years ago.  I had ubuntu 10.10 installed for about 4
hours before removing it in favor of Arch Linux and its packaging structure.
After a year and a half of using archlinux, I decided I wanted to be a
Trusted User, and began working towards that goal.  I began adopting any
interesting package I could find in the AUR and updating it.

I maintain 59 packages in the `aur`_, 86 packages in `community and
multilib`_, and have submitted `several patches`_ to `pacman`_.  I also
maintain my own `repository` made up mostly of the new VCS PKGBUILD formats.

On IRC I go by ``gtmanfred``.  I can also me contacted by `email`_.

.. _few patches: https://projects.archlinux.org/pacman.git/log/?qt=author&q=William+Giokas
.. _pacman:   http://www.archlinux.org/pacman/
.. _email me: 1007380@gmail.com
.. _aur: https://aur.archlinux.org/packages/?SeB=m&K=gtmanfred
.. _community and multilib: https://www.archlinux.org/packages/?maintainer=dwallace
.. _several patches: https://projects.archlinux.org/pacman.git/log/?qt=author&q=Daniel+Wallace
.. _repository: http://code.gtmanfred.com/gtmanfred
.. _email: danielwallace@gtmanfred.com
