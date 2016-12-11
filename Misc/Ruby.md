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

### Installing RVM

To install RVM with the latest version of Ruby, use this shell command:

    $ curl -L https://get.rvm.io | bash -s stable --autolibs=enabled --ruby
 
For more details, visit the [installation documentation](https://github.com/wayneeseguin/rvm#installation).

### Loading `rvm` into the shell

To enable the use of `rvm` in your shell after installation, you need to source the `rvm` script. This can be done manually using 

    source "$HOME/.rvm/scripts/rvm"

or (recommended) you can place `source "$HOME/.rvm/scripts/rvm"` into a file named `.bashrc` or `.bash_profile`, which would automatically enable the use of `rvm` whenever you open a new shell window.

### Using `rvm` to load a specific version of Ruby.

Once the `rvm` script is loaded into your shell, you can use it to switch between versions of Ruby.

#### Switch versions manually

    # switch to Ruby 2.1.1
    rvm use 2.1.1 

#### Switch versions automatically

With `rvm` loaded into your shell, `rvm` will automatically check the current directory for [files that suggest the use of particular versions of Ruby](https://rvm.io/workflow/projects#supported-files) whenever you `cd` into a new directory.

If you clone an existing Ruby project, it will hopefully designate a Ruby version using a `.ruby-version`, `Gemfile`, or `.rvmrc` file.

If you are starting your own Ruby project, it is recommended that you create a `.ruby-version` file containing only a single version number. For example, the full contents of `.ruby-version` could be:

    2.1.7

#### Install new versions of Ruby with `rvm`

    rvm install 2.1.1

#### View all your installed versions of Ruby

    rvm list


Speeding up the installation of Ruby gems
-----------------------------------------

To significantly speed up the installation of any Ruby gems you might be installing 
(such as Rails), skip downloading of documentation for each gem by adding a global
[no-document](http://guides.rubygems.org/command-reference/#installupdate-options)
configuration to the [.gemrc file](http://guides.rubygems.org/command-reference/#description-6):

    $ echo "gem: --no-document" >> ~/.gemrc

