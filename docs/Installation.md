# Installation

The suggested and easiest way to install Homebrew is on the
[homepage](https://brew.sh).

The standard script installs Homebrew to `/usr/local` so that
[you don’t need sudo](FAQ.md#why-does-homebrew-say-sudo-is-bad) when you
`brew install`. It is a careful script; it can be run even if you have stuff
installed to `/usr/local` already. It tells you exactly what it will do before
it does it too. And you have to confirm everything it will do before it starts.

## Requirements
* An 64-bit Intel CPU <sup>[1](#1)</sup>
* macOS 10.12 or higher <sup>[2](#2)</sup>
* Command Line Tools (CLT) for Xcode: `xcode-select --install`,
  [developer.apple.com/downloads](https://developer.apple.com/downloads) or
  [Xcode](https://itunes.apple.com/us/app/xcode/id497799835) <sup>[3](#3)</sup>
* A Bourne-compatible shell for installation (e.g. bash or zsh) <sup>[4](#4)</sup>

## Alternative Installs

### OS X Mountain Lion (10.8) and below
Because GitHub now only allows clients that support TLS 1.2 to access repositories over HTTPS, the Homebrew installer will use the Git protocol when run on systems older than OS X Mavericks (10.9). This requires the availability of a `git` binary, which can be provided by pre-installing the [Command Line Tools for Xcode](https://developer.apple.com/download/more/). Homebrew will also require the Command Line Tools or Xcode in order to automatically compile and install a newer `curl` and `git` with support for TLS 1.2.

### Untar anywhere
Just extract (or `git clone`) Homebrew wherever you want. Just avoid:

* Directories with names that contain spaces. Homebrew itself can handle spaces, but many build scripts cannot.
* `/tmp` subdirectories because Homebrew gets upset.
* `/sw` and `/opt/local` because build scripts get confused when Homebrew is there instead of Fink or MacPorts, respectively.

However do yourself a favour and install to `/usr/local`. Some things may
not build when installed elsewhere. One of the reasons Homebrew just
works relative to the competition is **because** we recommend installing
to `/usr/local`. *Pick another prefix at your peril!*

```sh
mkdir homebrew && curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew
```

### Multiple installations
Create a Homebrew installation wherever you extract the tarball. Whichever `brew` command is called is where the packages will be installed. You can use this as you see fit, e.g. a system set of libs in `/usr/local` and tweaked formulae for development in `~/homebrew`.

## Uninstallation
Uninstallation is documented in the [FAQ](FAQ.md).

<a name="1"><sup>1</sup></a> For 32-bit or PPC support see
[Tigerbrew](https://github.com/mistydemeo/tigerbrew).

<a name="2"><sup>2</sup></a> 10.12 or higher is recommended. 10.9–10.11 are
supported on a best-effort basis. For 10.4-10.6 see
[Tigerbrew](https://github.com/mistydemeo/tigerbrew).

<a name="3"><sup>3</sup></a> Most formulae require a compiler. A handful
require a full Xcode installation. You can install Xcode, the CLT, or both;
Homebrew supports all three configurations. Downloading Xcode may require an
Apple Developer account on older versions of Mac OS X. Sign up for free
[here](https://developer.apple.com/register/index.action).

<a name="4"><sup>4</sup></a> The one-liner installation method found on
[brew.sh](https://brew.sh) requires a Bourne-compatible shell (e.g. bash or
zsh). Notably, fish, tcsh and csh will not work.
