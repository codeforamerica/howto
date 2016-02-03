Python
======
Python is a clear and powerful object-oriented programming language, comparable to Perl, Ruby, Scheme, or Java.  Its main focus is on readability and standards based approached

PIP and Environment Management
---
Use ``pip`` to install applications and [virtualenv](./Python-Virtualenv.md) to manage your development environments.

Unless otherwise required use Python 3.5 and if multiple version of support are desired use [tox](https://tox.readthedocs.org/en/latest/) to run tests across multiple ``python`` versions.

Project Structure
-----------------
All projects should include README.md files with links to this document, Contributors.md with information about how to contribute and who is contributing, and a license file, MIT preferred.  Each project should have a requirements folder containing an app.txt file in the [requirement file format](https://pip.readthedocs.org/en/1.1/requirements.html) always pin requirements to and use projects which respect [semver](http://semver.org/).  Also including a dev.txt requirements file with developer tools can be helpful as well as operating system specific scripts.

Application Structure
---------------------
Applications should be pip installable and once mature added to [pypi](https://pypi.python.org/pypi).  This mainly means having a [setup.py](https://docs.python.org/3.5/distutils/setupscript.html) file in the root of your project.

Documentation
-------------
Documentation should be both inline and external documents stored in the ``docs/``.  [Sphinx](http://www.sphinx-doc.org/en/stable/) is well understood and popular tool.

PEP8
----
Follow [pep8](https://www.python.org/dev/peps/pep-0008/) rules, just do it, there are multiple tools but [``pep8`` ](https://github.com/PyCQA/pep8) is probably best used in continuous integration.  Tools like [``pyflakes``](https://pypi.python.org/pypi/pyflakes) can offer more hints but oftentimes can be too noisy.
