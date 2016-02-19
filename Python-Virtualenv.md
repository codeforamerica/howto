Python Install and Virtual Environments
=======================================

Pip and Virtualenv are the packaging tools recommended by the [Python Packaging User Guide](https://python-packaging-user-guide.readthedocs.org/en/latest/current.html). Use Pip to install Python packages from [PyPI](https://python-packaging-user-guide.readthedocs.org/en/latest/glossary.html#term-python-package-index-pypi), and virtualenv to isolate application specific dependencies from a shared Python installation.

Python Install
--------------
For comprehensive and up to date instructions for OSX installs look [here](http://docs.python-guide.org/en/latest/starting/install/osx/) but for simple cases the instructions below should help.

To install ``python3``  on OSX use
> brew install python3

or if ``python3`` is not supported by a required library use python 2.7 

> brew install python

On Debian and Ubuntu

> sudo aptitude install python3.5-dev

On Fedora

> sudo yum install python3.5-dev

Pip
---

To install Pip on a Mac OS, [follow the Pip installer instructions](http://www.pip-installer.org/en/latest/installing.html):

Install or Upgrade pip
----------------------

To install or upgrade pip, securely download [get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py). [[1](http://www.pip-installer.org/en/latest/installing.html#id5)]

Then run the following (which may require administrator access):

>     $ python get-pip.py

If setuptools (or distribute) is not already installed, get-pip.py will install [setuptools](https://pypi.python.org/pypi/setuptools) for you. [[2](http://www.pip-installer.org/en/latest/installing.html#id6)]


On Debian and Ubuntu:
 
>     $ sudo aptitude install python3-pip
 

On Fedora:

>     $ sudo yum install python3-pip

If you need to use python 2.7 just remove the 3 from the commands.

Virtualenv
----------

Virtualenv is a tool that allows projects to have isolated environments on the same machine so that developing on multiple projects doesn't create a dependency conflict nightmare.  [This tutorial](http://docs.python-guide.org/en/latest/dev/virtualenvs/) should help get virtualenv and virtualenvwrapper installed on your development machine.

Once you have virtualenvwrapper installed you can start a new virtualenv like so

> mkvirtualenv -p `which python3` --no-site-packages project_name

or if you have to use python 2

> mkvirtualenv -p `which python` --no-site-packages project_name

The ``--no-site-packages`` option means that none of the system versions of your requirements will be used, which greatly decreases the risk of unexpected conflicts.
