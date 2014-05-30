Ruby with RVM
=============

Ruby is a dynamic, reflective, object-oriented, general-purpose programming language.
It’s typically used for web development with Ruby On Rails, Sinatra, or Jekyll.
Ruby comes pre-installed on both Mac and Linux, but it’s likely that you’ll need
to upgrade to a newer version of the language than what you already have.

Before you begin, ensure that you have installed the [build tools](Build-Tools.md). 
If you're on a Mac, ensure that you have also installed [Homebrew](Build-Tools.md#homebrew).
Without Homebrew, RVM will attempt to install [Macports](http://www.macports.org).
In most cases, Homebrew is a preferable Mac package manager.

RVM
---

[Ruby Version Manager](https://rvm.io) (RVM) is a command-line tool which allows
you to easily install, manage, and work with multiple Ruby environments, from
interpreters to sets of gems. The Ruby language is under active development,
and the version that ships with your operating system may be older than the 
versions expected by current frameworks such as Rails. RVM helps bring your
Ruby up to date.

To install RVM with the latest version of Ruby:

    $ curl -L https://get.rvm.io | bash -s stable --autolibs=enabled --ruby
 
For more details, visit the [installation documentation](https://github.com/wayneeseguin/rvm#installation).

After initial installation, check RVM’s output for additional instructions, e.g.:

> To start using RVM you need to run `source /home/nobody/.rvm/scripts/rvm`
> in all your open shell windows, in rare cases you need to reopen all shell windows.


Ruby
----

### Mac & Ubuntu

To install a given version of Ruby, run `rvm install desired_version`, e.g.:

    $ rvm install 2.1.1
