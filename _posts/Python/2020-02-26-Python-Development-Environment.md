---
layout: post
title: 'pyenv, venv'
comments: true
author: Rudy
date:   2020-02-26 14:00:00 +0900
tags: [pyenv, venv]
category: [Python]
---

# My Python Development Environment

## => pyenv + venv
### pyenv (Python version Management)

    $ pyenv versions
    $ pyenv install 3.7.6
    $ pyenv install 3.8.1
    $ pyenv global 3.7.6 3.8.1
    ...

### venv (Python Virtual Environment)

Create a virtual environment:

    $ python3.7 -m venv ENV_NAME

You must run `pyenv global x.x.x` before running this command to make sure to use the version installed with pyenv.

Now you need to run 'activate' file which is in `ENV_NAME/bin/` to activate the new environment:

    $ source ENV_NAME/bin/activate

### Why use venv instead of pyenv-virtualenv

pyenv-virtualenv manages environments with one directory.

You can activate an environment with pyenv-virtualenv like this:

    $ cd PROJECT_PATH # if you need
    $ pyenv virtualenvs
    env_1 (created from ...)
    env_2 (created from ...)
    env_3 (created from ...)

    $ pyenv activate <ENV_NAME>

which means that you have to keep track of the connections between the environment names and projects. So one way to use pyenv-virtualenv easily is to name an environment as a project name.

On the other hand, if you use venv, you can activate it by simply running the activate file which is in the project's bin directory.

    $ cd PROJECT_PATH
    $ source /bin/activate

So you don't need to memorize which environment you have to use with your project.

<!-- ### Why use venv instead of Virtualenv
You can use both venv and Virtualenv to create virtual environments. But the difference between these two is Virtualenv creates python binary files when creating a virtual environment, whereas venv just links the files. The benefit of this is that when a python version is updated, venv can reflect it immediately, whereas Virtualenv can't. -->
