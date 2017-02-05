**This documentation is being deprecated!**
Please update your links to [here](https://wiki.codeforamerica.org)
Future changes will be made from [this github repository](https://github.com/codeforamerica/cfa-wiki)


Build Tools
===========

A core development system should typically include build tools
like [Make](http://en.wikipedia.org/wiki/Make_%28software%29)
and [GCC](http://en.wikipedia.org/wiki/GNU_Compiler_Collection).
Make is a utility that automatically builds executable programs
and libraries from source code. The GNU Compiler Collection (GCC)
is a compiler system produced by the GNU Project supporting
various programming languages.

These tools are not used directly in normal web development,
but other tools in Python, Ruby, and other languages rely
on them to work. Both GCC and Make are developed and maintained
by the [GNU Project](https://www.gnu.org) and
[Free Software Foundation](http://www.fsf.org),
originators of the legal and technical basis
of free and open source software.

You might already have them installed, here’s how to check:

    $ make --version
    $ gcc --version


Linux (Ubuntu or Debian)
-----

Install [build-essential](http://packages.ubuntu.com/precise/build-essential):

    $ sudo apt-get install build-essential


Mac OS X
--------

### 10.9 (Mavericks)

Install the standalone Command Line Tools by running this command from the Terminal:

    $ xcode-select --install

For more details, and step-by-step instructions
with screenshots, visit [Moncef Belyamani's tutorial](http://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/#step-1).

### 10.8, 10.7 (Mountain Lion & Lion)

Install the standalone Command Line Tools from the [Apple Developer](https://developer.apple.com/downloads/) portal.

For more details, and step-by-step instructions
with screenshots, visit [Moncef Belyamani's tutorial](http://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/#clt-ml).

### 10.6 (Snow Leopard)

Install GCC and Make alone with
[OSX GCC Installer](https://github.com/kennethreitz/osx-gcc-installer#readme).


### Homebrew

Homebrew is a package manager for OS X that allows for the installation of
command line utilities and other software. It is analogous to
[Ubuntu & Debian’s Apt](http://en.wikipedia.org/wiki/Advanced_Packaging_Tool).

To install Homebrew, follow directions given at [brew.sh](http://brew.sh/#install):

> Install Homebrew
> 
      $ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
> 
> Paste that at a Terminal prompt.
> 
> The script explains what it will do and then pauses before it does it.
> There are more installation options [here](https://github.com/Homebrew/homebrew/wiki/Installation)
> (needed on 10.5).

After initial installation, check Homebrew’s output for additional instructions.
Before you install anything with Homebrew, run `brew doctor` to make sure your system is ready
to brew. If `brew doctor` reports any errors or warnings, read Moncef Belyamani's tutorial for helpful
[troubleshooting tips](http://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/#troubleshoot-homebrew).
