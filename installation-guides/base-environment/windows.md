# Windows

<h2 id='InstallPython'> 1. Installing Python </h2>

1. Go to [this link](https://www.python.org/downloads/windows/) and download the newest version of Python.<br>
   - The latest version of the x86-64 executable installer from the stable releases section.
    
2. Open the executable to begin the Python Installation.
3. Select "Customize installation".
4. On the Optional Features page.<br>
    - Select all of the optional features. <br>
    - Click "Next"
5. On the Advanced Options page, select the following options:
    - Associate files with Python
    - Create shortcuts for installed applications
    - <b>Add Python to environment variables <- This is a very imporant option to mark</b>
    - Click "Install"
6. Once it has completed the install, click "Close"<br>
    
To verify it has installed correctly, open a command prompt and type "python"<br>
<ul style="list-style-type:circle;" id='opencmd'>
    <li> Go to the start menu and type "CMD" and hit enter </li>
</ul> 

If it enters into a python interpreter (shown by having ">>>" at the beginning of the line) then type "exit()" and continue to step 2

If it doesn't enter into the python interpreter see <a href='InstallPython'>this section</a>

<h2 id='InstallPip'> 2. Installing Pip </h2>

1. In the command line, run the following commands to download and install Pip<br>
    - `curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py`
    - `python get-pip.py`
2. Close the Command Prompt and <a href='opencmd'>open a new Command Prompt</a>
3. Verify pip installed successfully by executing the command "pip" in the command line
    - If it says "'pip' is not recognized as an internal or external command" see <a href='InstallPip'>this section</a>
    - Else, continue to part 3
    
<h2 id='InstallPipenv'> 3. Installing Pipenv </h2>
