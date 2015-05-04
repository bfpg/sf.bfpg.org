# Tools for Software Foundations

[Software Foundations][SF] is a course developed by Benjamin C Pierce and
others, and made freely available. It teaches:

[SF]: http://www.seas.upenn.edu/~bcpierce/sf/current/index.html

- Mechanised theorem proving using [Coq][].
- A broad introduction to Programming Language Theory, completely formalised in
  Coq.

[Coq]: https://coq.inria.fr/

This site augments the [System Requirements][SysReq] section of the course,
with links to all the tools you need, and some simple instructions, so you can
get into the interesting stuff quickly.

[SysReq]: http://www.seas.upenn.edu/~bcpierce/sf/current/Preface.html#lab10

You should go read the course [Preface][] now, and then come back here to set
up the tools you'll need.

[Preface]: http://www.cis.upenn.edu/~bcpierce/sf/current/Preface.html

This site was made by members of the [Brisbane Functional Programming
Group][BFPG], for a [workshop][] at [YOW! Lambda Jam 2015][YLJ15]. We hope to
maintain it for as long as we find it interesting.

[BFPG]: http://bfpg.org/
[workshop]: https://a.confui.com/-ejlKSwK8
[YLJ15]: http://lambdajam.yowconference.com.au/

## Generic instructions

Unless you really want to start from scratch, you probably just want to head
straight on to the [platform-specific recommendations][recommendations]. Come
back here if we don't cover your platform, or if you want to better understand
what you're installing.

[recommendations]: #user-content-platform-specific-recommendations

To follow the course, you will need:

- [Coq, version 8.4][Coq84].
  
  Coq tends to make breaking changes between point releases, so stick with the
  version on which Software Foundations was developed. You may take the most
  recent patch-level of that version, of course.

  You'll need this regardless of which interactive environment you choose
  below.

- An interactive environment. Realistically, this is the only way to build
  non-trivial proofs in Coq.
  
  We are aware of these options:

    - [Proof General, version 4.2][PG], with [GNU Emacs][Emacs] version 23.2
      or later.

      This is what we use and recommend. It is stable, mature, and reasonably
      easy to install.

    - [CoqIDE][], which is part of the Coq distribution. On some platforms,
      such as Linux and FreeBSD, CoqIDE might be packaged separately.

      This might seem to be the path of least resistance, but you'll soon find
      yourself wanting a more powerful editor. CoqIDE might not be as reliable
      as Proof General.

    - [Coquille][], a [vim-pathogen][] plugin for [Vim][].

      We don't have much experience with Coquille. It appears to be the newest
      of these options, but we can't comment on its reliability or
      functionality.

- The [Software Foundations][SF] course material. You may:

    - [Download a tarball][sf-tarball] from the [Software Foundations][SF]
      website.

    - Clone our [GitHub mirror][sf-mirror], where we intend to track released
      versions, starting with version 3.2 (January 2015).

- The [Coq documentation][coq-doc]. Optional, but recommended, especially:

    - The [tactics][coq-tactics] chapter in the [reference manual][coq-ref], if
      you find yourself forgetting the names of tactics.

    - The [library documentation][coq-lib], and the [library sources][coq-src],
      if you like learning by browsing.

[Coq84]: https://coq.inria.fr/coq-84
[PG]: http://proofgeneral.inf.ed.ac.uk/download
[Emacs]: http://www.gnu.org/software/emacs/
[CoqIDE]: https://coq.inria.fr/coqide-screenshots
[coqide-unreliable]: http://web.cecs.pdx.edu/~apt/coq_hints.html
[Coquille]: https://github.com/the-lambda-church/coquille
[vim-pathogen]: https://github.com/tpope/vim-pathogen
[Vim]: http://www.vim.org/
[sf-tarball]: http://www.seas.upenn.edu/~bcpierce/sf/current/sf.tar.gz
[sf-mirror]: https://github.com/bfpg/software-foundations
[coq-doc]: https://coq.inria.fr/documentation
[coq-tactics]: https://coq.inria.fr/distrib/current/refman/Reference-Manual010.html
[coq-ref]: https://coq.inria.fr/distrib/current/refman/
[coq-lib]: https://coq.inria.fr/distrib/current/stdlib/
[coq-src]: https://github.com/coq/coq/tree/trunk/theories

### Making the tools work together

The interactive environments all need to find the `coqtop` program from the
Coq 8.4 distribution, so set your `PATH` environment variable accordingly.

To use Proof General with Emacs, you'll need to load `generic/proof-site.el`
from the Proof General distribution, by one of the following methods:

- Adding a line to your `.emacs.d/init.el`:

    `(load "path/to/ProofGeneral-4.2/generic/proof-site.el")`

- Adding a command-line option when you start Emacs:

    `emacs --load path/to/ProofGeneral-4.2/generic/proof-site.el`

# Platform-specific recommendations

These are our recommendations for some common platforms.

We documented [how we built the bundles][sf-tools] for Mac and Windows. Bundles
are signed by [Matthew Brecknell][mbrcknl], who takes all reasonable care, but
no responsibility.

[sf-tools]: https://github.com/bfpg/software-foundations-tools
[mbrcknl]: https://keybase.io/mbrcknl

## Mac OS X

For Mac OS X, we provide a bundle that contains everything you need.

- [sf-mac-2015-05-18.dmg][sf-mac]
- [sf-mac-2015-05-18.dmg.sha256sum][sf-mac-sum]
- [sf-mac-2015-05-18.dmg.sig][sf-mac-sig]

[sf-mac]: http://sf.bfpg.org/files/sf-mac-2015-05-18.dmg
[sf-mac-sum]: http://sf.bfpg.org/files/sf-mac-2015-05-18.dmg.sha256sum
[sf-mac-sig]: http://sf.bfpg.org/files/sf-mac-2015-05-18.dmg.sig

Unpack the DMG, then run the `emacs` script in the top directory. This will
open Emacs with Proof General on the first chapter of Software Foundations.
When you finish a chapter, you might find the `make` script useful for
compiling your code so it can be loaded in the next chapter.

The scripts probably won't do everything you'll need. Use them to see how the
tools work together, and adapt them to your purpose.

You should now read below to learn the basics of [driving Proof
General][usage].

[usage]: #user-content-working-with-emacs-and-proof-general

## Microsoft Windows

For Windows, we provide a bundle that contains everything you need.

- [sf-windows-2015-05-03.zip][sf-windows]
- [sf-windows-2015-05-03.zip.sha256sum][sf-windows-sum]
- [sf-windows-2015-05-03.zip.sig][sf-windows-sig]

[sf-windows]: http://sf.bfpg.org/files/sf-windows-2015-05-03.zip
[sf-windows-sum]: http://sf.bfpg.org/files/sf-windows-2015-05-03.zip.sha256sum
[sf-windows-sig]: http://sf.bfpg.org/files/sf-windows-2015-05-03.zip.sig

Unpack the ZIP, then run `emacs.bat` in the top directory. This will open Emacs
with Proof General on the first chapter of Software Foundations. When you
finish a chapter, you might find `make.bat` useful for compiling your code so
it can be loaded in the next chapter.

The `.bat` files probably won't do everything you'll need. Use them to see how
the tools work together, and adapt them to your purpose.

You should now read below to learn the basics of [driving Proof
General][usage].

## Debian and Ubuntu Linux

This should work on Ubuntu Linux 14.04 LTS, Debian Jessie, and more recent
versions.

```
sudo apt-get install git proofgeneral coq
git clone git@github.com:bfpg/software-foundations.git
cd software-foundations/sf
proofgeneral Basics.v
```

## Fedora Linux

This should work on Fedora 19 and more recent.

```
sudo yum install git emacs-proofgeneral coq
git clone git@github.com:bfpg/software-foundations.git
cd software-foundations/sf
proofgeneral Basics.v
```

# Working with Emacs and Proof General

There is an [Emacs reference card][emacs-ref-card]. The *Getting Help* section
might be especially useful. There is also a [reference manual][emacs-ref].

[emacs-ref-card]: http://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf
[emacs-ref]: http://www.gnu.org/software/emacs/manual/html_node/emacs/index.html

Proof General has a [reference manual][pg-ref]. You'll mainly be interested in
the [script processing commands][pg-script].

[pg-ref]: http://proofgeneral.inf.ed.ac.uk/userman
[pg-script]: http://proofgeneral.inf.ed.ac.uk/htmlshow.php?title=Proof+General+user+manual&file=releases%2FProofGeneral%2Fdoc%2FProofGeneral%2FProofGeneral_3.html#Script-processing-commands

