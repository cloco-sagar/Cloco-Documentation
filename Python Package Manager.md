# Python Package Manager : Poetry

## Introduction
Poetry is a Python Package Manager released in 2018. It is designed to simplify package management and make it more consistent across different platforms.
It is similar to pip but with more advanced features.



## Installation

There are many ways you can install poetry. And here we are going to use pipx to download and install poerty. If you want to install poerty in other ways you
can follow this link for the installation.

https://python-poetry.org/docs/#installing-with-pipx

To download poetry using pipx you need to install pipx into your system. And to install pipx into your system you can follow these steps 

```
// Download pipx into  the system

// For Linux
sudo apt update
sudo apt install pipx
pipx ensurepath

// For MacOS
brew install pipx
pipx ensurepath
```

Now check if pipx is installed into your system then you can follow these steps to install poetry using pipx

```
pipx install poetry
```

## Examples
Some of the examples using poetry:

```
poetry new poetry-demo //This will create a poetry-demo directory with some certain file structure

poetry install //This will install all defined dependencies that are in your project
```

## REFERENCE LINK
https://python-poetry.org/docs/#installing-with-pipx

https://github.com/pypa/pipx


## Knowledge Based

Problems you may encounter when using poetry

### Problem 1: Unable to delete or upgrade poetry from your system

You can uninstall or upgrade poetry using pipx using these following simple command
```
pipx uninstall poetry //This will uninstall poetry from your system

pipx upgrade poetry //This will update the latest poetry to your system 
```




