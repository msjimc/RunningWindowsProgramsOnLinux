# SlackWare 15.0_RELEASE

## Starting point

SlackWare 15.0_RELEASE was installed on a 64-bit virtual machine featuring 4,096 MB of RAM and 4 CPU cores. The storage was set up with a 40 GB hard disk in VirtualBox and a dynamically resizing hard disk in Hyper-V. Default settings were applied during the installation, with the hard disk being GPT formatted and partitioned as follows: a 600 MB EFI boot partition, a 4 GB Linux swap partition, and a 35.4 GB Linux filesystem partition, all configured using cfdisk. The system was set to utilize the KDE5 desktop environment.

Note: In VirtualBox, the machine was specifically configured with EFI enabled, categorized under the type: Linux and version: Oracle Linux (64-bit).

The circularMT_64.exe file and the sequence.gb files were obtained from the ‘Program’ and ‘Example data’ sections of the [circularMT GitHub repository](https://github.com/msjimc/circularMT).  These files were downloaded into the user’s Download directory (~/Downloads) using the Firefox web browser.

## Preparation and installation

* **The account performing the installation must have admin rights.**

You need to be either root or elevate your permissions with sudo to install Wine. Then download the wine-9.9-x86_64-1sg.txz file from [Wine files on SourceForge for Slackware](https://sourceforge.net/projects/wine/files/Slackware%20Packages/9.9/x86_64/) to the Downloads folder. Install Wine using the following command:

> sudo -i upgradepkg --install-new ~/Downloads/wine-9.9-x86_64-1sg.txz

This installed Wine64 version 9.9. To configure Wine the following command:

> winecfg


## Installing Winetricks 

To install Winetricks, you must have root privileges or administrative rights. You can install Winetricks by running the following command:

> sudo -i upgradepkg --install-new winetricks

## Installing  a .Net runtime

### Installing multilib for 
 
To install the .NET runtime on Slackware, which includes some 32-bit components, you’ll need to enable multilib support. This allows Slackware to run 32-bit binaries. The following steps, adapted from this [web page](https://ratfactor.com/slackware/steam). This must be performed as root or with admin rights:

First, switch to root user with:

> su -l root 

 Create a directory for multilib and navigate into it:

> mkdir multilib && cd multilib  

Download the code base (may take a while):  

> lftp -c "open http://www.slackware.com/~alien/multilib/ ; mirror -c -e 15.0"

Navigate into the downloaded directory

> cd 15.0  

Install the multilib packages (May take another while):

> upgradepkg --reinstall --install-new *.t?z  
> upgradepkg --install-new slackware64-compat32/*-compat32/*.t?z  
> printf "\n//Multilib:\n[0-9]+alien\n[0-9]+compat32\n" >> /etc/slackpkg/blacklist

Exit the root session

> crtl + D

### Install the .Net 6 runtime

Download the ***.NET Desktop Runtime 6.0.32*** x64  installer file from the __.NET Desktop Runtime 6.0.32__ section on this [.NET download page](https://dotnet.microsoft.com/en-us/download/dotnet/6.0). Before installing the new runtime, remove the current Wine configuration with the following command:

> rm -R ~/.wine

and remake with:

> winecfg

Finally, install the .NET runtime with:

> wine ~/Downloads/windowsdesktop-runtime-6.0.32-win-x64.exe

Running this command will open the installer dialog box, allowing you to proceed with the installation of the runtime.

## Running a Windows application like circularMT

To run the circularMT_64.exe application, you would typically use the following command in the terminal:

> wine64 ~/Downloads/circularMT_64.exe (figure 1)

<hr />

![Figure 1](images/Slackware_15_0_RELEASE_figure1.jpg)

Figure 1

<hr />
 
