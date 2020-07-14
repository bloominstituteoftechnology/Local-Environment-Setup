# Linux - Local Setup

Ubuntu is by far the most common distribution of Linux. However there are many distributions to choose from.
- Debian
- OpenSUSE
- Mint
- Arch
- RedHat
- Fedora

### 0. Get Linux Essentials
- Some distributions use slightly different syntax from below. 
- For example, in OpenSUSE `apt` is spelled `zypper`, and in some other distributions it is spelled `pacman`.

```shell script
$ sudo apt update --fix-missing
$ sudo apt upgrade
$ sudo apt install build-essential
$ sudo apt install cmake
```

### 1. Get Python Essentials
- Python and pip may come pre-installed, depending on your distribution.
```shell script
$ sudo apt install python3-pip
$ sudo apt install python3-dev
```

 
### 2. Add Bash Shortcuts
- Open the file named `.bashrc` in the nano text editor.

```shell script
$ nano .bashrc
```

- Page down to the bottom of the file and add the following:

```shell script
# CLI Shortcuts
alias .bash='nano ~/.bashrc'
alias python=python3
alias pip=pip3
```

- Exit nano: `ctrl-x` and `y` then `ENTER` to save the file.
- Restart Linux.

### 3. Get Data Science Tooling
```shell script
$ pip install pandas Cython seaborn
$ pip install scikit-learn xgboost category_encoders
$ pip install eli5 pdpbox shap plotly jupyter notebook
```
