# Setting up a Python development environment in Windows

## Preparing the system

We should:
1. allow powershell to execute scripts
2. install Git
3. (optional but recommended) uninstall and clean any Python versions currently installed. **Warning: This will break current working repositories which will need to be reconfigured under the new pyenv-poetry combination!**

## Setting up the Python environment

### Pyenv - The Python Version Manager

#### Why use it?

To-do

#### Instructions

1. Let's open a Powershell window and install pyenv for windows according to the [official instructions](https://github.com/pyenv-win/pyenv-win). 

    **Note 1:** We must use the install option with git clone. 

    **Note 2:** Since we are using PowerShell (and not the command line), in the git command we should replace `%USERPROFILE%` with `$env:USERPROFILE`, e.g.: 

    ```
    git clone https://github.com/pyenv-win/pyenv-win.git $env:USERPROFILE/.pyenv
    ```

1. After installing pyenv, we need to follow the instructions on the section "finish the installation" and confirm that we have a working installation by typing ```pyenv --version``` in the terminal.

1. Now that pyenv is installed, we also need to install a global python version that we will use to install poetry:
    1. We can check what Python versions are available with ```pyenv install -l```
    2. We can then install the latest available (3.8.2 at the time of writing this, in 32bit and 64bit) with ```pyenv install 3.8.2-amd64``` and follow the instructions of the pop-up wizard
    3. Once the installation has completed, we can set this version as global with ```pyenv global 3.8.2-amd64```
    4. We then have to reset the symbolic links in Pyenv to redirect to this new global python version by typing ```pyenv rehash``` . This is done so that everytime we type `python` in the terminal (outside of a virtual environment), pyenv will redirect to the correct global one
    5. We can confirm that we have set up everything correctly by typing ```python --version```

### Poetry - Virtual Environment and Python Package Manager

#### Why use it?

To-do

#### Instructions

1. Let's open a Powershell window and install pyenv according to the [official instructions](https://python-poetry.org/docs/). For this, we need to use the powershell command: 

    ```
    Invoke-WebRequest -Uri https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py -UseBasicParsing.Content | python
    ```

1. then, let's restart Powershell and type ``poetry --version``. It should return the latest installed version.

1. Finally, we need to change a global setting of Poetry to ensure that all our virtual environments will be created within our project folders as a .venv folder. In the powershell terminal we need to type ```poetry config virtualenvs.in-project true```

    We can confirm the change by checking the global setting in poetry:

    ```poetry config --list```

    *If we don't do the above, all new virtual environments will be created globally, which is not necessarily wrong, but is a messier solution compared to having it locally, per project. Over time, this will make our python virtual environments more difficult to manage.*

## Set-up a Python project




### Day-to-day work
### Collaboration and co-development
### Packaging and publishing
