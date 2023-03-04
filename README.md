# Virtualizing macOS in VMWare
### A simple tutorial on how to install macOS in VMWare

## Ingredients:
### A copy of VMWare Workstation Player or Pro, both of them work.
*Player:* https://www.vmware.com/products/workstation-player.html

*Pro:* https://www.vmware.com/products/workstation-pro.html

### A macOS Offline Installer ISO

There are two ways on getting yourself one of these, the first one requires having a mac

#### Using a mac
You can read it here: https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html

Of course, don't forget to convert the DMG to a ISO file.

#### Using the information super highway
So, I was diggin' through the internet archive and I found this link: https://archive.org/download/macos_iso

I didn't test it though, so be careful!

### At least 12 GB of RAM
If you _really_ don't want to suffer with the slowness, make sure the VM has at least 6GB of RAM

### At least 80 GB of free storage
I personally recommend using a *SECONDARY* hard drive.

### VMWare Unlocker
It's not necessary if you use VMWare Workstation Pro.

You can get it here: https://github.com/paolo-projects/auto-unlocker/releases

## finally doing something that is not downloading a whole lot of files!!!! uwuw wow

### Step 1 (For VMWare player users!):
Make sure VMWare is closed, open up the Unlocker, if the directory is incorrect just fix it, hit `Patch` and give it some time.

### Step 2:
After patching VMWare Player, open it up, hit `Create a New Virtual Machine`

`I will install the operating system later.`

`Apple Mac OS X`, select the version you got, give it a nice name,

give it 80 GB of storage and make sure to hit `Store virtual disk as a single file`

`Customize hardware`

give it some ~[[GOGOL KROM FOOD]]~ RAM

give it 3 Processors

at New CD/DVD (SATA) add the macOS iso you got,

`Close`, `Finish`.

### Step 3:
Now we need to update the .vmx file, open it up on notepad or any other text editor and add this at the end of the file:
```
smbios.reflectHost = "TRUE"
hw.model = "MacBookPro14,3"
board-id = "Mac-551B86E5744E2388"
smc.version = "0"
```
The `hw.model` value can be changed to spoof the model, but the one I used is at the top

Save it and _pray_ for the best.

### Step 4 (Optional but recommended):
Install VMWare Tools on the guest.

### Step 5 (Optional, but really recommended):
Use some scripts you can find at `github.com/sickcodes/osx-optimizer`
