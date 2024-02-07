# Debugging Ren'py with PowerShell for VSCode

This template includes VSCode launchs for developing Ren'Py projects.

**What can be done**:
* Add `$ print("...")` to display them in the vscode terminal while the app is running
* Don't have to open Ren'py SDK every time
* Close the game with CTRL+C in the terminal or when closing VSCode

**What cannot be done**:
* Insert breakpoint

## How Run Debug (F5)

![image](https://user-images.githubusercontent.com/67595890/179401467-c8abbc9b-8970-4bad-af86-2b5b31c173a4.png)


### Setup

( **Necessary only in the beginning** )

Paste the path to your Ren'Py SDK folder

Exemple: `/home/username/renpy`

### Run

Select:

- Run or
- Force Recompile & Run

And Play!

#### For Linux first:

Installing PowerShell on Ubuntu
https://learn.microsoft.com/en-us/powershell/scripting/install/install-ubuntu?view=powershell-7.3
```bash
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q "https://packages.microsoft.com/config/ubuntu/$(lsb_release -rs)/packages-microsoft-prod.deb"
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of packages after we added packages.microsoft.com
sudo apt-get update
# Install PowerShell
sudo apt-get install -y powershell
```

give renpy permission
```bash
chmod +x renpy.sh
chmod +x renpy.py
chmod +x renpy.exe
chmod +x lib/py3-linux-x86_64/renpy
chmod +x lib/py3-linux-x86_64/pythonw
sudo apt-get install -y xdg-utils

```

when opening the text with error info via terminal, write:

```bash
:q

```


if this:

![image](https://user-images.githubusercontent.com/67595890/181924847-19e28398-259a-4ca0-831a-da72410e4612.png)


them:

```bash
sudo apt-get install -y yad

```

#### For microsoft wsl
https://docs.microsoft.com/it-it/windows/wsl/tutorials/gui-apps



## File

- `bin/renpy`: macOS/linux script for calling Ren'Py SDK `renpy.sh`
- `bin/renpy.ps1`: Windows script for calling Ren'Py SDK `renpy.exe`
- `bin/set-origin.sh`: Git setup helper to configure your local folder to sync to a remote host
- `.vscode/launch.json`: Launch for launching Ren'Py SDK commands without opening the Ren'Py launcher.
  - Setup (custom file for remembering your project's SDK path for commands to work)
  - Run
  - Force Recompile & Run
  - Delete Persistent
  - Lint
  - Distribute
- `.vscode/extensions.json`: Optional extensions that VSCode will offer to install for you
- `.vscode/settings.json`: For Test Formatting, and other settings
  - [Ren'Py Language](https://marketplace.visualstudio.com/items?itemName=LuqueDaniel.languague-renpy) for syntax highlighting
  - [Power Shell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell) for an easy clickable list of launchs from `.vscode/launch.json`
  - [Python](https://marketplace.visualstudio.com/items?itemName=spmeesseman.vscode-taskexplorer) for python syntax highlighting
- `.gitignore`: Git configuration file for ignoring certain file paths and types.
- `/game/tool/utility.rpy`: Useful functions such as: isNullOrEmpty 
- `/game/tool/flags.rpy`: Flags System
- `/game/tool/notify.rpy`: Notify System
- `/game/tool/log_system.rpy`: Log System
