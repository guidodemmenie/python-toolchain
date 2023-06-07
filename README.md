# Robot Framework Toolchain for Beginners

In order to start playing around with Robot Framework, Python needs to be installed. Also using an IDE with the correct plugins helps creating your Robot Framework code in many ways.

One issue with Mac OS: It has its own Python installation that is not always the version you need for your projects. Since Mac OS is dependent on the version it uses, you don't want to mess with that installation.

To fix this `pyenv` helps to install a separate (more up to date) version of Python alongside the one Mac OS uses and can be used without interfering.

So to get started with Robot Framework on a Mac you need the following tools:

* [Homebrew](https://brew.sh) - The Missing Package Manager for macOS (or Linux)
* [pyenv](https://github.com/pyenv/pyenv) - Simple Python version management
* [Visual Studio Code]() - IDE
    * robocorp.robotframework-lsp

## Homebrew

Homebrew is a package management system with which you can install all kinds of applications or tools, here it is used to install `pyenv` and the tools needed to install python later on.

To install `brew` first install de CLT from xcode by running from the terminal [[1]](https://docs.brew.sh/Installation#macos-requirements)

```sh
xcode-select --install
```

Then to install `brew` itself [[2]](https://brew.sh)

``` sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

It will guide you through the process and after some time you'll get the message:

``` sh
==> Installation successful!
```

## pyenv

`pyenv` can manage multiple versions of python next to each other.

1. To install pyenv:

``` 
brew install pyenv
```

2. Set up your shell environment for `pyenv` by running following code in the terminal [[3]](https://github.com/pyenv/pyenv#set-up-your-shell-environment-for-pyenv) 

``` sh
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```


3. Add dependencies for building python from source as pyenv does:
``` bash
brew install openssl readline sqlite3 xz zlib
```

4. Open a new terminal window and check the installed versions of Python, it will look something like this
``` sh
pyenv versions
```

``` sh
  system
  3.8.13
```

5. Install a recent version of python
``` sh
pyenv install 3.11
```

``` sh
Downloading Python-3.11.2.tar.xz...
-> https://www.python.org/ftp/python/3.11.2/Python-3.11.2.tar.xz
Installing Python-3.11.2...
...
Installed Python-3.11.2 to /Users/myuser/.pyenv/versions/3.11.2
```

6. Verify that the version is installed
``` sh
pyenv versions
```

``` sh
  system
  3.8.13
  3.11.2
```

7. Set the version as the python to be used
``` sh
pyenv global 3.11.2
```

8. Check if the new version is now active
``` sh
pyenv versions
```

``` sh
  system
  3.8.13
* 3.11.2 (set by /Users/myuser/.pyenv/version)
```

9. Check if the new version of python is active

``` sh
python --version
```

``` sh
Python 3.11.2
```

So now we have a working new version of python that is up to date and which we can use for Robot Framework.

## Robot Framework

We can use the python package management system `pip` to install Robot Framework.

1. Install Robotframework
``` sh
pip install robotframework
```

``` sh
Collecting robotframework
  Using cached robotframework-6.0.2-py3-none-any.whl (658 kB)
Installing collected packages: robotframework
Successfully installed robotframework-6.0.2
```

2. Check if robot framework is correctly installed.
``` sh
robot --version
```

``` sh
Robot Framework 6.0.2 (Python 3.11.2 on darwin)
```

## Visual Studio Code

Visual Studio Code can be installed 
1. through the installer from https://code.visualstudio.com or
2. through `brew` 
``` sh
brew install --cask visual-studio-code
```

Install extensions for Robot Framework
* from VSCode use `cmd+shift+X` and search for `robotframework-lsp` or
* from the terminal
``` sh
code --install-extensions robocorp.robotframework-lsp
```

## Happy Testing!