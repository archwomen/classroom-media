============
Git for Gits
============

Thanks to meskarune, fsckd, alad, spider-mario, Will Smith

https://xkcd.com/1597/

  Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

  --- https://git-scm.com/

Here's where Git is used in Arch Linux:

  - https://git.archlinux.org/svntogit/

    - https://github.com/falconindy/asp

  - https://aur.archlinux.org/packages

.. contents:: Table of Contents

Getting started with Git
========================

  - git-config(1)

    - https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup#Your-Identity

  - git-init(1)

  - Clone repo, add file, push commit

Add content
===========

  - git-add

  - git-diff (--cached)

  - git-log

  - git-commit

      - use imperative present tense https://git-scm.com/book/ch5-2.html
      - http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
      - --amend

Review
======

  - git-show

  - git-checkout

  - git-reset

Merging changes to/from upstream
================================

  - git-pull

  - `git pull --rebase` while one commit ahead and behind upstream

  - Branch, add commit, and merge into master

Workflow
========

  - http://www.gweezlebur.com/2009/01/19/my-git-workflow.html
  - http://reinh.com/blog/2008/08/27/hack-and-and-ship.html
  - http://nvie.com/posts/a-successful-git-branching-model/
  - https://www.atlassian.com/git/workflows#!workflow-centralized

Future Considerations
=====================

  - You can pull github PRs as branches (thanks to maerwald)
  - Turning (a) commit/s into patch/es
  - Cleaning your repos
    - git-gc
    - git-filter-branch
  - git-reflog
  - git-rebase
  - git-imerge (thanks to spider-mario)
  - asciicast by e: https://asciinema.org/a/4ej7bclhngokdome26riewjmo
  - git-checkout --orphan
  - gitignore(5)

See also
========

  - https://jwiegley.github.io/git-from-the-bottom-up/
  - https://git-scm.com/book/
  - https://archwomen.org/wiki/aw-tech:git:start
  - https://try.github.io/
  - https://github.com/olivierverdier/zsh-git-prompt
  - https://github.com/AladW/aurutils
  - <alad> man git-tutorial, git-tutorial-2
  - http://jonas.nitro.dk/tig/
  - gitrevisions(7)
