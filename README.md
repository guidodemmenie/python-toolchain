# robotframework-toolchain

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

## venv

[python -m venv](https://docs.python.org/3/library/venv.html)

``` bash
$ pyenv global 3.10.6
$ $(pyenv which python3) -V
Python 3.10.6
```

### Workflow

New project
``` bash
~/src % mkdir rf-test-project
~/src % cd rf-test-project
~/src/rf-test-project % python -m venv .venv
~/src/rf-test-project % source .venv/bin/activate
(.venv) ~/src/rf-test-project %
``` 

Continue working on a project
``` bash
~/src/rf-test-project % source .venv/bin/activate
(.venv) ~/src/rf-test-project %
```

Removing virtual environment
``` bash
(venv) % deactivate
% rmdir -df .venv
```


## Robotframework
Install Robotframework
``` bash
(venv) % pip install robotframework
```

## Browserlibrary

Install NodeJS
``` bash
% brew node
```

Install Browser library
``` bash
(venv) % pip install robotframework-browser
```

Initialize the Browser library:
``` bash
% rfbrowser init 
```


## Visual Studio Code

Install VSC
``` bash
% brew install --cask visual-studio-code
```

Install mandatory extensions
``` bash
% code --install-extensions robocorp.robotframework-lsp
```

Install optional extensions
``` bash
% tobe filled
```

Using venvs in VSCode
* Todo -> installing python plugin and making sure it opens your venv automagically