# Windows 10 - Linux Shell for Data Science


### 0. Update Windows 10
You may need to reboot.

### 1. Enable WSL2 on Windows 10
1. Open PowerShell as Admin
2. Paste the following and hit enter after each:
    - `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
    - `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
3. Reboot Windows
4. Set WSL as the default
    - `wsl --set-default-version 2`

### 2. Download and Install Ubuntu from the Microsoft Store
![Microsoft Store](Microsoft-store.jpg)

### 3. Run Ubuntu from the Start Menu
![Ubuntu Logo](Ubuntu-logo.jpg)

### 4. Get Linux Essentials
```sh
$ sudo apt update --fix-missing
$ sudo apt upgrade
$ sudo apt install build-essential
$ sudo apt install cmake
```

### 5. Get Python Essentials
```sh
$ sudo apt install python3-pip
```

### 6. Add Bash Shortcuts
Open the file named `.bashrc` in the nano text editor.

```sh
$ nano .bashrc
```

Page down to the bottom of the file and add the following:

```sh
# Environment Variables
export BROWSER="/mnt/c/Program Files/Mozilla Firefox/firefox.exe"
export PATH="$PATH:~/.local/bin"

# CLI Shortcuts
alias .bash='nano ~/.bashrc'
alias python=python3
alias pip=pip3
```
- Exit nano: `ctrl-x` and `y` then `ENTER` to save the file.
- Restart Ubuntu.

### 7. Get Data Science Tooling
```sh
$ pip install pandas Cython seaborn
$ pip install scikit-learn xgboost category_encoders
$ pip install eli5 pdpbox shap plotly jupyter notebook
```

### 8. Configure Jupyter

```sh
$ jupyter notebook --generate-config
$ nano ~/.jupyter/jupyter_notebook_config.py
```

```sh
c.NotebookApp.allow_remote_access = True
c.NotebookApp.browser = '/mnt/c/Program Files/Mozilla Firefox/firefox.exe'
c.NotebookApp.open_browser = True
c.NotebookApp.use_redirect_file = False
```
