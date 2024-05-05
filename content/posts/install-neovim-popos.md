+++
author = "David Salter"
title = "Installing Neovim on Pop!_OS"
date = "2024-05-05"
description = "How to build and install neovim on Pop!_OS"
tags = [
    "popos",
    "neovim"
]
+++
Neovim is a modern VIM based text editor that is gaining popularity within the developer community. The Pop!_OS apt repositories contain an old version of Neovim. This article shows how to build and install the latest stable version of Neovim on Pop!_OS.

![Neovim](/static/assets/Neovim-logo.svg)

Full build instructions for Neovim are available on Neovim's [Github repository](https://github.com/neovim/neovim/blob/master/BUILD.md), but are summarised here is a specific format that can be directly used on Pop!_OS.

## Install the build dependencies

There are a few build dependencies required to be able to build Neovim:

``` sh
$ sudo apt-get install gettext cmake unzip curl build-essential
```

## Checkout the source code

Once your system is ready to build Neovim, get the latest source code via git.

``` sh
$ git clone https://github.com/neovim/neovim
$ cd neovim
$ git checkout stable
```

This script checks out the stable branch of Neovim rather than the latest daily build. At the time of writing, the stable build is version 0.9.5

I find it best to check out the stable build rather than the daily build as some of the internal APIs used by Neovim can change, causing instabilities with different plugins.

<div class="info-note"><strong>Note:</strong> If you wish to install the latest daily build and not the latest stable build, omit checking out the <code>stable</code> branch.</div>

## Build and install

Neovim can be built and installed as a Debian package (.deb), this allows it to be easily uninstalled or upgraded at a later date. To build and install, execute the following:

``` sh
$ make CMAKE_BUILD_TYPE=RelWithDebInfo
$ cd build
$ cpack -G DEB
$ sudo dpkg -i nvim-linux64.deb

```

## Uninstall

To uninstall Neovim, uninstall the Debian package.

``` sh
$ sudo apt remove neovim
```


## Summary

In this article, we've seen how to install the latest stable version of Neovim, and optionally the latest daily build. Enjoy and happy developing !

## Credits

Neovim logo by Jason Long, available at [http://neovim.org/logos/neovim-logos.zip](http://neovim.org/logos/neovim-logos.zip)

