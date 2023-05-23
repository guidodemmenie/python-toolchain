# Managing different environments

When you have to maintain multiple projects with different dependencies and different versions of python it pays of to start using virtual environments. In comes [python venv](https://docs.python.org/3/library/venv.html), a Python virtual environment management.

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

### VSCode
Todo: VSCode steps to make this work.

## Browserlibrary

Install NodeJS
``` bash
brew install node
```

Install Browser library
``` bash
pip install robotframework-browser
```

Initialize the Browser library:
``` bash
rfbrowser init 
```
