---
layout: post
title: "Emacs Live"
date: 2013-07-10 17:36
comments: true
categories: emacs tools programming
---

So today I decided to re-install emacs from scratch.

{% img /images/why_would_you_do_that.png 400 400 why would you do that? %}

this started the usual way,

```
$ brew install emacs
```
and *voila!* I had a vanilla install of emacs.

I was using the [starter-kit](https://github.com/technomancy/emacs-starter-kit) before
but I had some problems with certain packages playing nice so I decided to look for
something new. Enter **Emacs Live**.

Emacs Live
==========

{% img /images/emacs-live.png Emacs Live %}

Sam Aaron makes [music](https://www.youtube.com/watch?v=bMP-7POtML0) with code. He
live-codes his music using a *customised* version of Emacs. Apparently this is also a
nice setup for developing in Clojure, a language I'm very interested in.

To install I cloned [the repository](https://github.com/overtone/emacs-live)
to .emacs.d.

```
$ git clone https://github.com/overtone/emacs-live.git  ~/.emacs.d
```

I started it up and played with some of the features (undo-tree!!!).
I couldn't leave well enough alone and wanted my pretty [solarized](http://ethanschoonover.com/solarized) colors, so I got to hacking.

Solarized
=========

I found a custom 'pack' for solarized [here](https://github.com/siancu/solarized-pack) but
it uses [batsov's solarized-emacs package](https://github.com/bbatsov/solarized-emacs) which I could never get working with emacs running in iTerm. I read a bit of the documentation and decided to roll my own user pack with [sellout's color-theme-solarized package](https://github.com/sellout/emacs-color-theme-solarized) (There are at least **three** different emacs packages for the solarized theme).

The [documentation](http://overtone.github.io/emacs-live/documentation.html) explains how to
make a user pack and get it loaded into emacs. What I did with my user pack was to clone
sellout's package into the lib folder for the pack:

```
$ cp -r ~/.emacs.d/packs/template ~/.live-packs
$ cd ~/.live-packs
$ mv user-template-pack dave-pack
$ git clone https://github.com/sellout/emacs-color-theme-solarized ~/.live-packs/dave-pack/lib/emacs-color-theme-solarized
```

then a little editing was needed to some files inside the pack:

``` cl ~/.live-packs/dave-pack/init.el
;; Solarized
(live-load-config-file "solarized-conf.el")
```

``` cl ~/.live-packs/dave-pack/config/solarized-conf.el
;; Solarized theme configuration file
(add-to-list 'custom-theme-load-path "~/.live-packs/dave-pack/lib/emacs-color-theme-solarized")
(load-theme 'solarized-dark t)
```

created ~/.emacs-live.el

``` cl ~/.emacs-live.el
(live-use-packs '(live/foundation-pack
                 ;live/colour-pack ;disabled for solarized to work properly
                 live/clojure-pack
                 live/lang-pack
                 live/power-pack))
(live-add-packs '(~/.live-packs/dave-pack))
```

PROTIP: set your terminal's XTERM to 16 colors!

-and that was that! Now I have to spend some time installing my favorite
ruby packages, like rinari and rspec-mode. That can wait for another night.
