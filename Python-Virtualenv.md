Python Virtual Environments
====

Pip and Virtualenv are the packaging tools recommended by the [Python Packaging User Guide](https://python-packaging-user-guide.readthedocs.org/en/latest/current.html). Use Pip to install Python packages from [PyPI](https://python-packaging-user-guide.readthedocs.org/en/latest/glossary.html#term-python-package-index-pypi), and virtualenv to isolate application specific dependencies from a shared Python installation.

Pip
---

To install Pip on a Mac OS, [follow the Pip installer instructions](http://www.pip-installer.org/en/latest/installing.html):

> Install or Upgrade pip
> To install or upgrade pip, securely download [get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py). [[1](http://www.pip-installer.org/en/latest/installing.html#id5)]
> 
> Then run the following (which may require administrator access):
> 
>     $ python get-pip.py
> 
> If setuptools (or distribute) is not already installed, get-pip.py will install [setuptools](https://pypi.python.org/pypi/setuptools) for you. [[2](http://www.pip-installer.org/en/latest/installing.html#id6)]

On Debian, Ubuntu, and Fedora Linux, Pip is available under the name `python-pip`.

> On Debian and Ubuntu:
> 
>     $ sudo apt-get install python-pip
> 
> On Fedora:
> 
>     $ sudo yum install python-pip

Virtualenv
---

Install Virtualenv tools.

    $ sudo pip install virtualenv

Change into your Python project directory (for example, “my-project”), then create a new virtual environment. Naming it `.venv` will create a hidden folder to contain the necessary files in.

    $ cd my-project
    $ virtualenv .venv

Activate the environment.

 * `$ source .venv/bin/activate` (if you use the bash shell)
 * `$ source .venv/bin/activate.csh` (if you use the csh or tcsh)

Now `which python` should confirm that your python executable is located under `.venv`. Your shell prompt might also be modified to include “my-project”.

When you're done working with your virtual environment, it is easy to get out.

    $ deactivate

Install Packages
---

If you are installing an existing project, look for a [requirements.txt](http://www.pip-installer.org/en/1.1/requirements.html) file containing names of packages required by the project. Ask Pip to install the list of packages.

    $ pip install -r requirements.txt

Auto Activating the Virtual Environment
---
Taken from https://gist.github.com/codysoyland/2198913

Add the following code to your .bashrc or .bash-profile
When you cd into a folder with a virtual environment name `.venv` it will automatically activate.
```
#   The virtualenv will be activated automatically when you enter the directory.
_virtualenv_auto_activate() {
    if [ -e ".venv" ]; then
        # Check to see if already activated to avoid redundant activating
        if [ "$VIRTUAL_ENV" != "$(pwd -P)/.venv" ]; then
            _VENV_NAME=$(basename `pwd`)
            echo Activating virtualenv \"$_VENV_NAME\"...
            VIRTUAL_ENV_DISABLE_PROMPT=1
            source .venv/bin/activate
            _OLD_VIRTUAL_PS1="$PS1"
            PS1="($_VENV_NAME)$PS1"
            export PS1
        fi
    fi
}
 
export PROMPT_COMMAND=_virtualenv_auto_activate
```
