Ruby with RVM
=============

Ruby is a dynamic, reflective, object-oriented, general-purpose programming language.
It’s typically used for web development with Ruby On Rails, Sinatra, or Jekyll.
Ruby comes pre-installed on both Mac and Linux, but it’s likely that you’ll need
to upgrade to a newer version of the language than what you already have.

Before you begin, ensure that you have prepared [build tools](Build-Tools.md).

RVM
---

[Ruby Version Manager](https://rvm.io) (RVM) is a command-line tool which allows
you to easily install, manage, and work with multiple ruby environments from
interpreters to sets of gems. The Ruby language is under active development,
and the version that ships with your operating system may be older than the 
versions expected by current frameworks such as Rails. RVM helps bring your
Ruby up to date.

To install RVM, follow directions from [rvm.io](https://rvm.io):

> Install RVM with a Ruby:
> 
>     $ \curl -sSL https://get.rvm.io | bash -s stable
> 
> For all in one installation append `--rails` or `--ruby` or `--ruby=1.9.3`
> 
> For more details visit the [installation documentation](https://rvm.io/rvm/install/).

After initial installation, check RVM’s output for additional instructions, e.g.:

> To start using RVM you need to run `source /home/nobody/.rvm/scripts/rvm`
> in all your open shell windows, in rare cases you need to reopen all shell windows.


Ruby
----

### Homebrew (Mac)

Without Homebrew, RVM will attempt to install [Macports](http://www.macports.org).
In most cases, [Homebrew](http://brew.sh) is a preferable Mac package manager.
To install Homebrew, follow directions given in [Build Tools](Build-Tools.md#homebrew).

When you try to install a specific Ruby, you may encounter an OpenSSL conflict. More information
[is available on Stack Overflow](http://stackoverflow.com/questions/21508866/openssl-rvm-brew-conflicting-error),
with specific steps given to fix it:

    $ brew reinstall openssl
    $ brew link openssl --force


### Mac & Ubuntu

To install a given version of Ruby, run `rvm install`, e.g.:

    $ rvm install 2.0.0
