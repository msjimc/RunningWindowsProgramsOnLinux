# SlackWare 15.0_RELEASE

## Starting point

OpenSUSE - 'Leap' 15.5 was installed on a 64 bit virtual machine with 4,096 MB of RAM, 4 processors, with 40 GB hard disk (VirtualBox) or dynamically resizing hard disk (HyperV) and was configured with the default settings (the hard disk was GPT formatted with partition of: 600M EFI boot, 4 G Linux swap partition and a 35.4 G Linux file system set using cfdisk) and configured to use the KDE5 desktop.

Note: VirtualBox was configured with EFI enabled and was of type: Linux and version: Oracle Linux (64-bit)

The circularMT_64.exe file and the sequence.gb files were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Download folder (~/Downloads) using FireFox.

## Preparation and installation

* **The account performing the installation must have admin rights.**

Log in as root to install Wine. The download the wine-9.9-x86_64-1sg.txz file from https://sourceforge.net/projects/wine/files/Slackware%20Packages/9.9/x86_64/ to root's Downloads folder and install wine with:

> sudo -i upgradepkg --install-new ~/Downloads/wine-9.9-x86_64-1sg.txz

This installed wine64 version 9.9 which was configured for each user with the command:

> winecfg


## Installing Winetricks 

To install the Winetricks you must be either root or have admin rights. To install Winetricks run:

> sudo -i upgradepkg --install-new winetricks

## Installing  a .Net runtime

### Installing multilib for 
 
 Since some core components of the .Net runtime are 32 bit, to install the runtime you need multilib which allows Slackware to make and use 32 bit binaries. The following steps came from this [web page](https://ratfactor.com/slackware/steam)

These steps must be performed as root or with admin rights:

> su -l root 

 Make the folders and enter:  
> mkdir multilib && cd multilib  

Download the code base (may take a while):  

> lftp -c "open http://www.slackware.com/~alien/multilib/ ; mirror -c -e 15.0"

Enter the folder

> cd 15.0  

Create and install the binaries (May take another while)  
> upgradepkg --reinstall --install-new *.t?z  
> upgradepkg --install-new slackware64-compat32/*-compat32/*.t?z  
> printf "\n//Multilib:\n[0-9]+alien\n[0-9]+compat32\n" >> /etc/slackpkg/blacklist

Exit root

> crtl + D

### Install the .Net 6 runtime

Download the runtime x64 install file from the __.NET Desktop Runtime 6.0.32__ section on this {page](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) and delete the current Wine configuration with:

> rm -R ~/.wine

and remake with:

> winecfg

and install the .Net runtime with:

> wine ~/Downloads/windowsdesktop-runtime-6.0.32-win-x64.exe

This will open the installer dialogue box allowing you to install the runtime.

## Running a Windows application like circularMT

circularMT_64.exe was then run with the command:

> wine64 ~/Downloads/circularMT_64.exe (figure 1)
<hr />

![Figure 1](images/Slackware_15_0_RELEASE_figure1.jpg)

Figure 1

<hr />
 
