# WSL

## Update Windows 10

Ensure that you have the most current update from Windows. Currently to install WSL2 you must have **Build 1904** or higher. To check your Windows version open the run command dialog using 

## Enable WSL2 on Windows 10

Open PowerShell as an Administrator by right clicking on the start menu icon and clicking **Windows PowerShell \(Admin\)**

![](../.gitbook/assets/image%20%281%29.png)

Copy and paste the following commands into PowerShell to enable and install WSL & WSL2:

```text
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestartdism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

```text
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

#### Reboot Windows to let the changes take effect

When you've logged back in open PowerShell as an Administrator once again and enter the following command to instruct Windows to use  WSL2 for new installations of Linux distributions.

```text
wsl --set-default-version 2
```

## Download and Install Ubuntu from the Microsoft Store

![Microsoft Store](../.gitbook/assets/Microsoft-store.jpg)

## Run Ubuntu from the Start Menu

![Ubuntu Logo](../.gitbook/assets/Ubuntu-logo.jpg)

Launch the application and it will prompt you to select a username and password. Welcome to Linux, from this point on you may follow the instructions for Linux users, some caveats are noted and instructions for those specific circumstances are below.

### WSL Specific Configurations

###  Jupyter

Firefox is recommended, you'll need to install a modern browser in Windows before continuing. Internet Explorer will not work well.

```text
jupyter notebook --generate-config
```

```text
nano ~/.jupyter/jupyter_notebook_config.py
```

At the bottom of the file that is opened paste the following:

```text
```shell script
c.NotebookApp.allow_remote_access = True
c.NotebookApp.browser = "/mnt/c/Program Files/Mozilla Firefox/firefox.exe"
c.NotebookApp.open_browser = True
c.NotebookApp.use_redirect_file = False
```

* Exit nano: `ctrl-x` and `y` then `ENTER` to save the file.

This instructs Jupyter to open the correct browser when it is launched.

