# Windows

### **Install Git**

#### **If you’re unfamiliar with Vim please first install** [**Notepad++**](https://github.com/notepad-plus-plus/notepad-plus-plus/releases/download/v7.8.5/npp.7.8.5.Installer.exe) **or another text editor of your choice** <a id="if-youre-unfamiliar-with-vim-please-first-install-notepad-or-another-text-editor-of-your-choice"></a>

1. Download the Git for Windows [Installer](https://github.com/git-for-windows/git/releases/download/v2.25.1.windows.1/Git-2.25.1-32-bit.exe)​
2. Select the following options as the installer prompts
   * Notepad++ or editor of choice
   * Select **default**: Use Git from the command line and also from 3rd-party software
   * **Use OpenSSH**
   * **Use OpenSSL**
   * **Checkout Windows Style, Commit Unix-style Line Endings**
   * **Use MinTTY \(the default of MSYS2\)**
   * \[**No extra options**\]
   * Click **Install**
   * Launch Git Bash when the installation finishes

## **Configure Settings** <a id="configure-settings"></a>

The next step is configure your credentials with git.

**Your `user.name` variable can be set to any name however you email address should be the one associated with your GitHub account.**

```text
git config --global user.name <your username>
```

```text
git config --global user.email <your email address>
```

## Configure Line Endings <a id="configure-line-endings"></a>

**Unix systems and Windows systems have different paradigms for how they reference line endings. Avoid any frustrations when working in teams  by instructing git to download in your local systems**  


```text
git config --global core.autocrlf true
```

##  1. Installing Python <a id="InstallPython"></a>

1. Go to [this link](https://www.python.org/downloads/windows/) and download the newest version of Python. 
   * The latest version of the x86-64 executable installer from the stable releases section.
2. Open the executable to begin the Python Installation.
3. Select "Customize installation".
4. On the Optional Features page. 
   * Select all of the optional features.  
   * Click "Next"
5. On the Advanced Options page, select the following options:
   * Associate files with Python
   * Create shortcuts for installed applications
   * **Add Python to environment variables &lt;- This is a very imporant option to mark**
   * Click "Install"
6. Once it has completed the install, click "Close" 

To verify it has installed correctly, open a command prompt and type "python"  


*  Go to the start menu and type "CMD" and hit enter

If it enters into a python interpreter \(shown by having "&gt;&gt;&gt;" at the beginning of the line\) then type "exit\(\)" and continue to step 2

If it doesn't enter into the python interpreter see [this section](windows.md#InstallPython)

##  2. Installing Pip <a id="InstallPip"></a>

1. In the command line, run the following commands to download and install Pip 
   * `curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py`
   * `python get-pip.py`
2. Close the Command Prompt and [open a new Command Prompt](windows.md#opencmd)
3. Verify pip installed successfully by executing the command "pip" in the command line
   * If it says "'pip' is not recognized as an internal or external command" see [this section](windows.md#InstallPip)
   * Else, continue to part 3

##  3. Installing Pipenv <a id="InstallPipenv"></a>

