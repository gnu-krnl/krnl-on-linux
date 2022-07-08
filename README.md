## This is a tutorial on how to manually install KRNL on Linux 
## Some disclaimers is that there is no GUI, dev said he will be working on a GTK version


#### Installing dependencies and grapejuice
These commands will be for Arch, if you're on Ubuntu figure it out 

Install winetricks `sudo pacman -S --needed winetricks zenity` 

Make sure you've already installed [grapejuice](https://brinkervii.gitlab.io/grapejuice/docs) and atleast runned `grapejuice gui` and roblox once

You can install it using the source which should be just running 
```
sudo pacman -S --needed libpulse lib32-libpulse gnutls lib32-gnutls git python-pip python cairo gtk3 gobject-introspection desktop-file-utils xdg-utils xdg-user-dirs gtk-update-icon-cache shared-mime-info mesa-utils && git clone --depth=1 https://gitlab.com/brinkervii/grapejuice.git /tmp/grapejuice && cd /tmp/grapejuice && ./install.py
```

Then also run Roblox once to create the necessary game files 

Install wget for getting files or use curl
`sudo pacman -S wget`

Follow this [guide by grapejuice](https://brinkervii.gitlab.io/grapejuice/docs/Guides/Installing-Graphics-Libraries.html) to install the necessary graphics drivers


#### Installing DXVK
This method only works for DXVK so that's what we're gonna use 
Enable DXVK by setting DX11 as your Roblox renderer in grapejuice and enable the "Use DXVK D3D implementation" 


#### Installing C++ libs
In grapejuice open winetricks by pressing the "Wine Apps" button then press "Winetricks"
Select default wineprefix > Install windows dll > Find and enable both "dotnet48" and "vcrun2019" and click ok 
Ignore any errors that it throws at you, just click ok 
If all goes well and it's installing you should see a few GUIs, this can take up to 10 minutes so be patient and if you don't fuck something up you're good


#### Setting up KRNL directory
```
mkdir ~/krnl && cd ~/krnl && wget https://k-storage.com/bootstrapper/files/krnl.dll && mkdir autoexec && echo "loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()" > autoexec/iy.lua && mkdir workspace && curl https://raw.githubusercontent.com/gnu-krnl/krnl-on-linux/main/files/RunCode.iy  > workspace/RunCode.iy
``` 

Allow me to explain what the script above does, first it makes a KRNL directory, goes in it, gets the krnl.dll, makes a directory called autoexec, adds a loadstring in a lua file in autoexec which is infinite yield, gets a plugin that allows us to load files in the workspace directory 


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


#### Extras
If you think your doing it wrong check out this [example](https://github.com/gnu-krnl/krnl-on-linux/tree/main/example-directory)
