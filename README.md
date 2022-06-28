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


#### Installing DXVK
This method only works for DXVK so that's what we're gonna use 
Enable DXVK by setting DX11 as your Roblox renderer in grapejuice and enable the "Use DXVK D3D implementation" 
You should be good after that 


#### Installing C++ libs
In grapejuice open winetricks by clicking the Wine Apps button then winetricks 
Select default wineprefix > install windows dll > find and enable both dotnet40 and vcrun2019 or vcredist2019 and click ok 
If al goes well and it's installing you should see a few GUIs, this can take up to 10 minutes so be patient and if you don't fuck something up you're good


#### Setting up KRNL directory
```
mkdir ~/krnl && cd ~/krnl && wget https://k-storage.com/bootstrapper/files/krnl.dll && mkdir autoexec && echo "loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()" > autoexec/iy.lua && mkdir workspace && curl https://raw.githubusercontent.com/gnu-krnl/krnl-on-linux/main/files/RunCode.iy  > workspace/RunCode.iy
``` 

Allow me to explain what the script above does, first it makes a KRNL directory, goes in it, gets the krnl.dll, makes a directory called autoexec, adds a loadstring in a lua file in autoexec which is infinite yield, gets a plugin that allows us to loadfiles in the workspace directory 


#### Using KRNL 
##### Getting Extreme Injector 
After you've setup the KRNL dir, you need to get the extreme injector exe which can be found here 
https://github.com/gnu-krnl/krnl-on-linux/blob/main/files/Extreme%20Injector%20v3.exe?raw=true
Above is a download for the exe, if you think it's malware here's the [Extreme Injector github repo](https://github.com/master131/ExtremeInjector) so you can get the exe 
##### Finally actually running KRNL 
Now open taskmanager which can be found in Wine Apps > Task Manager, then click file on top right and run extreme injector, then inject krnl.dll into Roblox which should be straight forward and you're still not done 
##### Enabling the file loader plugin and using it
This is a one time thing to enable it unless you delete your IY config, run this `addplugin RunCode` in IY on Roblox 
Now if you want to execute scripts, put them in the workspace directory then `loadfile script.lua` in infinite yield
