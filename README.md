# python-toolchain

## homebrew


## pyenv

``` 
$ brew install pyenv
```

Add to `~/.zshrc` the following lines
``` bash
########
# Pyenv
########
# Setting for pyenv 
# (https://github.com/pyenv/pyenv#set-up-your-shell-environment-for-pyenv) 

export PYENV_ROOT="$HOME/.pyenv"
command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"

#####
```

Add dependancies for building python from source as pyenv does:
``` bash
$ brew install openssl readline sqlite3 xz zlib
```

## virtualenvmapper

``` bash
$ pyenv global 3.10.6
$ $(pyenv which python3) -V
Python 3.10.6
$ $(pyenv which python3) -m pip install virtualenvwrapper
```

Add to `~/.zshrc` the following lines
``` bash
########
# Virtualenvmapper
########
# Setting for virtualenvmapper 
# ()
# We want to regularly go to our virtual environment directory
export WORKON_HOME=~/.virtualenvs
# If in a given virtual environment, make a virtual environment directory
# If one does not already exist
mkdir -p $WORKON_HOME
# Activate the new virtual environment by calling this script
# Note that $USER will substitute for your current user
. ~/.pyenv/versions/3.10.6/bin/virtualenvwrapper.sh
```

### Workflow

New project
``` bash
~/src % mkdir rf-test-project
~/src % cd rf-test-project
~/src/rf-test-project % workon
~/src/rf-test-project % mkvirtualenv $(basename $(pwd))
created virtual environment CPython3.10.6.final.0-64 in 139ms
(rf-test-project) ~/src/rf-test-project % workon
rf-test-project
```

Continue working on a project
``` bash
~/src/rf-test-project % workon .
(rf-test-project) ~/src/rf-test-project %
```

Removing virtual environment
``` bash
% deactivate
% rmvirtualenv rf-test-project
```