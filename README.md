## This is a tutorial on how to use KRNL on Linux 
## Some disclaimers is that there is no GUI, dev said he will be working on a GTK version


#### Installing dependencies and grapejuice
These commands will be for Arch, if you're on Ubuntu figure it out 
It is assumed you've already setup [grapejuice](https://brinkervii.gitlab.io/grapejuice/docs/) 
Install wine `sudo pacman -S wine winetricks` 
Make sure you've already installed [grapejuice](https://brinkervii.gitlab.io/grapejuice/docs) and run it 
Then also run Roblox once to create the necessary game files 

Also install zenity for dialogs on winetricks
`sudo pacman -S zenity`

Install wget for getting files or use curl
`sudo pacman -S wget`

Follow this [guide by grapejuice](https://brinkervii.gitlab.io/grapejuice/docs/Guides/Installing-Graphics-Libraries.html) to install the necessary graphics drivers



```
mkdir ~/krnl && cd ~/krnl && wget https://k-storage.com/bootstrapper/files/krnl.dll && mkdir autoexec && echo "loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()" > autoexec/iy.lua
```

#### Installing

#### Installing C++ libs
Gonna continue this tomorrow
