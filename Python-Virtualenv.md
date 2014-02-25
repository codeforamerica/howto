Python Virtual Environments
====

Install Virtualenv tools.

    pip install virtualenv

Create a new virtualenv folder, in your local project directory.

    mkdir venv-project-name
    virtualenv venv-project-name

Activate the environment.

 * `source venv-project-name/bin/activate` (if you use the bash shell)
 * `source venv-project-name/bin/activate.csh` (if you use the csh or tcsh)

Now `which pip` should confirm that your pip executable is located under *venv-project-name*.
