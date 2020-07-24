# WSL



## 0. Update Windows 10

You may need to reboot after the update.

## 1. Enable WSL2 on Windows 10

1. Open PowerShell as Admin
2. Paste the following and hit enter after each:
   * `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
   * `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
3. Reboot Windows
4. Set WSL default version
   * `wsl --set-default-version 2`

## 2. Download and Install Ubuntu from the Microsoft Store

![Microsoft Store](../../.gitbook/assets/Microsoft-store.jpg)

## 3. Run Ubuntu from the Start Menu

![Ubuntu Logo](../../.gitbook/assets/Ubuntu-logo.jpg)

## 4. Get Linux Essentials

\`\`\`shell script $ sudo apt update --fix-missing $ sudo apt upgrade $ sudo apt install build-essential $ sudo apt install cmake

```text
### 5. Get Python Essentials
```shell script
$ sudo apt install python3-pip
$ sudo apt install python3-venv
```

## 6. Add Bash Shortcuts \(optional but very handy\)

* Open the file named `.bashrc` in the nano text editor.

\`\`\`shell script $ nano .bashrc

```text
- Page down to the bottom of the file and add the following:

```shell script
# Environment Variables
export BROWSER="/mnt/c/Program Files/Mozilla Firefox/firefox.exe"
export PATH="$PATH:~/.local/bin"

# CLI Shortcuts
alias .bash="nano ~/.bashrc"
```

* Exit nano: `ctrl-x` and `y` then `ENTER` to save the file.
* Restart Ubuntu.

## 7. Virtual Environment Setup \(optional but highly recommended\)

\`\`\`shell script $ mkdir project $ cd project $ python3 -m venv venv $ source venv/bin/activate

```text
### 8. Get Data Science Tooling
```shell script
$ pip install pandas Cython seaborn wheel twine
$ pip install scikit-learn xgboost category_encoders
$ pip install eli5 pdpbox shap plotly jupyter notebook
```

## 9. Configure Jupyter

Firefox is recommended, you'll need to install a modern browser in Windows before continuing. Internet Explorer will not work well. \`\`\`shell script $ jupyter notebook --generate-config $ nano ~/.jupyter/jupyter\_notebook\_config.py

```text
- Add the following to the bottom of `.jupyter/jupyter_notebook_config.py`
```shell script
c.NotebookApp.allow_remote_access = True
c.NotebookApp.browser = "/mnt/c/Program Files/Mozilla Firefox/firefox.exe"
c.NotebookApp.open_browser = True
c.NotebookApp.use_redirect_file = False
```

* Exit nano: `ctrl-x` and `y` then `ENTER` to save the file.
* Install Jupyter Widgets

  \`\`\`shell script

  $ pip install ipywidgets

  $ jupyter nbextension enable --py widgetsnbextension

