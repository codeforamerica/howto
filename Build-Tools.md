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
but other tools in the Python, Ruby, and other languages rely
on them to work. Both GCC and Make are developed and maintained
by the [GNU Project](https://www.gnu.org) and
[Free Software Foundation](http://www.fsf.org),
originators of the legal and technical basis
of free and open source software.


Ubuntu
------

Install http://packages.ubuntu.com/precise/build-essential

    $ sudo apt-get install build-essential


Mac OS 10.9, 10.8 (Mavericks & Mountain Lion)
-----------------

Install XCode from the Mac App Store.

Install [Homebrew](http://brew.sh/#install):

    $ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"


Mac OS 10.7, 10.6 (Lion & Snow Leopard)
-----------------

Install [OSX GCC Installer](https://github.com/kennethreitz/osx-gcc-installer#readme).

Install [Homebrew](http://brew.sh/#install):

    $ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
