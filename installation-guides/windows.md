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

**Your `user.name` variable can be set to any name; however your email address should be the one associated with your GitHub account.**

```text
git config --global user.name <your username>
```

```text
git config --global user.email <your email address>
```

## Configure Line Endings <a id="configure-line-endings"></a>

**Unix systems and Windows systems have different paradigms for how they reference line endings. Avoid any frustrations when working in teams by instructing git to download in your local systems**

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
   * **Add Python to environment variables &lt;- This is a very important option to mark**
   * Click "Install"
6. Once it has completed the install, click "Close"

To verify python has installed correctly, open a command prompt and type "python"

* Go to the start menu and type "CMD" and hit enter

If the command line enters into a python interpreter \(shown by having "&gt;&gt;&gt;" at the beginning of the line\) then type "exit\(\)" and continue to step 2

If the command line doesn't enter into the python interpreter see [this section](windows.md#InstallPython)

##  2. Installing Pip <a id="InstallPip"></a>

1. In the command line, run the following commands to download and install Pip 
   * `curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py`
     - If you get an error that says "'curl' is not recognized as an internal or external command" see [this section](windows.md#curl)
   * `python get-pip.py`
2. Close the Command Prompt and open a new Command Prompt
3. Verify pip installed successfully by executing the command "pip" in the command line
   * If the command line says "'pip' is not recognized as an internal or external command" see [this section](windows.md#InstallPip)
   * Else, continue to part 3

##  3. Installing Pipenv <a id="InstallPipenv"></a>

1. Use the command `pip install pipenv` to install pipenv to your computer
2. Close the command prompt and open a new command prompt

To verify the installation succeeded, execute the command `pipenv` in the command line

If the command line gives a list of options, then the install was successful. Continue to part 4

If the command line gives the error "'pipenv' is not recognized as an internal or external command" see [this section](windows.md#InstallPipenv)

##  4. Setting up your first Pip Environment <a id="FirstEnv"></a>

1. In the command prompt, navigate to the desired location of the environment using the command `cd (directory)`
   * As an example, the command prompt starts at `C:\Users\(username)`, I could use `cd documents\github\test` to change

     my directory to `C:\Users\(username)\documents\Github\test`

   * For BloomTech units, this will be in each of the sprint repositories. 
   * For personal projects or other python projects, this will be in the folder of that project    
2. Execute the command `pipenv shell` to create a virtual environment in the current directory
3. Use `pipenv install (packages)` to install the packages that will be used for the current project
   * An example of this command is `pipenv install pandas scipy eli5 matplotlib`
   * You can also specify package versions using `==` for example `pipenv install numpy==1.17.*`
     * This will install the latest version of NumPy 1.17. In this case, 1.17.5
     * Similarly, using `numpy==1.1*` would install the latest version of 1.1x NumPy \(which is 1.19\)
   * If the project is a build-on or for BloomTech units, you will probably be provided a `requirements.txt` file in the repository
     * To install dependencies to your pipenv shell from a requirements file, use `pipenv install -r requirements.txt`

##  5. Running Jupyter Notebooks <a id="JupNote"></a>

1. In your pip environment from [section 4](windows.md#FirstEnv), run the command `pipenv install notebook` to install Jupyter Notebooks
2. To start Jupyter Notebook in your current directory, simply run `pipenv run jupyter notebook`

## Extras
### Installing cURL <a id="curl"></a>
1. Installing cURL after installing Git Bash / Git for Windows
   - If you have installed git, you already have a usable instance of cURL in your files
   - Navigate to the folder you installed Git
       - This will probably be something like `C:\Program Files\Git`
   - From the base Git directory, search in this folder for `curl`
       - It should pop us as `curl.exe`
   - Right-click on this file and select `open file location`
   - Click on the navigation bar and copy the path to this folder
   - Next, in the windows task bar search `env` and hit enter
   - In the "System Properties" window, click `Environment Variables...`
   - In the `User variables for <user>` section find the Variable called `Path` and double click it
   - On the right side, click New and use Ctrl+v to paste the path you copied before into a new environment path
   - You should now be able to use the command `curl` in the command prompt
       - To verify it worked, open a command prompt and use `curl --help`
       
       
2. Installing cURL from scratch
   - Go to [this link](https://curl.haxx.se/windows/) and download either the 32-bit or 64-bit version for your system
   - Next, open a windows explorer window and navigate to the C: drive
       - Often in the directory window on the right side, it will be called `Windows (C:)`
   - Right click anywhere that is not on a file inside the windows explorer and create a new folder named `curl`
   - From your downloads, extract the zipped curl file you downloaded from the website into this new `curl` folder
   - Now go to [this link](https://curl.haxx.se/docs/caextract.html) and download the certificate that allows curl to access the web
   - Move this new file into your `curl` folder as well and rename the moved file to `curl-ca-bundle.crt`
   - Now copy this folder's path or just remember it (`C:\curl`)
   - Next, in the windows task bar search `env` and hit enter
   - In the "System Properties" window, click `Environment Variables...`
   - In the `User variables for <user>` section find the Variable called `Path` and double click it
   - On the right side, click New and use Ctrl+v to paste the path you copied before or memorized into a new environment path
   - You should now be able to use the command `curl` in the command prompt
      - To verify it worked, open a command prompt and use `curl --help`
