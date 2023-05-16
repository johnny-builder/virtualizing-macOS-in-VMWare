# Virtualizing macOS in VMWare
### A simple tutorial on how to install macOS in VMWare

## Ingredients:
### A copy of VMWare Workstation Player or Pro, both of them work.
*Player:* [![VMWare - Player](https://img.shields.io/badge/VMWare-Player-yellow)](https://www.vmware.com/products/workstation-player.html)

*Pro:* [![VMWare - Pro](https://img.shields.io/badge/VMWare-Pro-blue)](https://www.vmware.com/products/workstation-pro.html)

### A macOS Offline Installer ISO

There are two ways on getting yourself one of these, the first one requires having a mac

#### Using a mac
You can read it here: [![Dortania's - Open Core Install Guide](https://img.shields.io/badge/Dortania's-Open_Core_Install_Guide-blue)](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html)

Of course, don't forget to convert the DMG to a ISO file.

#### Using the information super highway
So, I was diggin' through the internet archive and I found this link: [![Internet Archive - macOS ISO ](https://img.shields.io/badge/Internet_Archive-macOS_ISO_-blue?logo=internetarchive)](https://archive.org/download/macos_iso)

I didn't test it though, except for the High Sierra one, so be careful!

### At least 12 GB of RAM
If you _really_ don't want to suffer with the slowness, make sure the VM has at least 6GB of RAM

### At least 80 GB of free storage
I personally recommend using a *SECONDARY* hard drive.

### VMWare Unlocker
It's necessary since (probably because of piracy) they disabled macOS on VMWare.

You can get it here: [![paolo-projects - auto-unlocker](https://img.shields.io/badge/paolo--projects-auto--unlocker-blue?logo=github)](https://github.com/paolo-projects/auto-unlocker/releases)

## finally doing something that is not downloading a whole lot of files!!!! uwuw wow

### Step 1:
Make sure VMWare is closed, open up the Unlocker, if the directory is incorrect just fix it, hit `Patch` and give it some time.

### Step 2:
After patching VMWare, open it up, hit `Create a New Virtual Machine`

`I will install the operating system later.`

`Apple Mac OS X`, select the version you got

Give it a nice name,

Give it 80 GB of storage and make sure to hit `Store virtual disk as a single file`

`Customize hardware`

Give it some ~[[GOGOL KROMER FOOD]]~ RAM

Give it 2 Processors (3 Processors is always better, but of course, depends on your machine)

At `New CD/DVD (SATA)` attach the macOS ISO file you got,

`Close`, `Finish`.

Now, make sure to close VMWare, since the .vmx file will be in use!

### Step 3:
Now we need to update the .vmx file, open it up on notepad or any other text editor and add this at the end of the file:
```
smbios.reflectHost = "TRUE"
hw.model = "MacBookPro14,3"
board-id = "Mac-551B86E5744E2388"
smc.version = "0"
```
The `hw.model` value can be changed to spoof the model, but the one I used is at the top

Save it, _pray_ for the best, and fire it up.

### Step 3.1:

Now, just so you don't screw up, give it some time, select the right language and hit `Disk Utility`

Click on `View`, `Show all volumes`

Now, select `VMWare Virtual SATA Hard Drive` and hit `Erase`

Now, give it a nice name and format it as APFS or Mac OS Extended (Journaled)

Make sure the scheme is GUID Partition Map, and hit `Erase`

Now, you can close Disk Utility and continue to the installer, ~Dis~agree to the EULA

Select the drive you erased 2 lines ago and hit `Continue`

Now, just as a reminder, depending on your hardware this may take more than a few hours, so don't be alarmed if it takes too long.

After that, you just need to go through the first use process, by the way, if the profile pictures are invisible, just click on the empty space, they will show up.

### Step 4 (Optional but recommended):
Install VMWare Tools on the guest.

### Step 5 (Optional, but really recommended):
Use some scripts you can find at [![sickcodes - osx-optimizer](https://img.shields.io/badge/sickcodes-osx--optimizer-blue?logo=github)](https://github.com/sickcodes/osx-optimizer)

### Step 6:
Star this repo! If you liked it or it was useful for you, starring will really help me out!
