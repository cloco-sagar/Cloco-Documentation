
# Python Version Management Tool: Pyenv

## Introduction
Pyenv is used for handling multiple python version in your system. It is simple Python Version Management tool.
It’s a lifesaver when you’re working on different projects that require different Python versions. 


## Installation

1. Install all the required packages using one-liner provided by the automatic installer for pyenv required packages
```
curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | zsh  //if you are using bash change zsh to bash
```

2. Grab the latest pyenv source tree from its Github repo

```
git clone https://github.com/pyenv/pyenv.git $HOME/.pyenv
```

3. Set the environment variable PYENV_ROOT
    Open .zshrc file or .bashrc file and paste these code
```
## pyenv configs
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"

if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
fi
```

4. Restart the shell for the PATH changes to take effect.
```
exec "$SHELL"
```

## Ways to install multiple python Version

```
# View all available versions with this command.
pyenv install -l

# You can now install multiple Python version via pyenv, for example.
pyenv install 3.6.4
pyenv install 3.6.5

# List all Python versions available to pyenv
pyenv versions

# Check the global Python version
pyenv global

# Set the global python version using the pyenv command
pyenv global 3.6.5
pyenv global

# Set the local Python version on per-project basis
# For instance, if you have a project located in $HOME/python_projects/test,
# you can set the Python version of it using following command.
cd python_projects/test
pyenv local 3.6.5
pyenv version		#view local python version for a specific project
```

## Extras
Pyenv manages virtual environments via the pyenv-virtualenv plugin which automates management of virtualenvs and conda environments for Python on Linux and other UNIX-like systems.

**Installing pyenv-virtualenv plugin**
```
git clone https://github.com/yyuu/pyenv-virtualenv.git $HOME/.pyenv/plugins/pyenv-virtualenv
source $HOME/.zshrc # Replace zshrc with bash accoring to your requirement
```
**Create a test virtual environment**
called venv_project1 
```
mkdir project1
cd project1
pyenv virtualenv 3.6.5 venv_project1
```
**Note: Make sure required pyenv version is installed before setting that version as its virtual environment** 

## REFERENCE LINK
https://github.com/pyenv/pyenv

https://amaral.northwestern.edu/resources/guides/pyenv-tutorial#:~:text=Meet%20pyenv%3A%20a%20Simple%20Python,environments%20(%22virualenv's%22).


## Knowledge Based 

Problems you may encounter when using pyenv

### Problem 1: zsh: pyenv not found or bash: pyenv not found
Make sure you have correctly followed the above installation process. If the problem still exists. Make sure to restart the shell.
```
exec "$SHELL"
```

