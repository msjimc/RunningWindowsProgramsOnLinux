# Manjaro:

## Starting point
Manjaro-Cinnamon 23.0.1 was installed on two 64-bit virtual machines with 4,096 MB of RAM, and 4 processors. The VirtualBox virtual machine had a 25 GB hard disk while Hyper-V's virtual machine had a dynamically resizing hard disk. Both installations were completed using the default settings and the Cinnamon desktop.

The circularMT.exe and the sequence.gb files were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Downloads folder using Vivaldi.

***Note:*** Vivaldi is the default browser, but on these installations it had to be started using the ***Internet*** > ***Avahi VNC Server Browser*** option in the start menu .

## Installation

Manjaro is derived from Arch Linux and so the installation is almost the same. However, you don't need to edit the ***/etc/pacman.conf*** file and there doesn't seem to be an issue with the winecfg step hanging.

Before installing Wine, it is recommended to do a full system update:

> sudo pacman -Syu

```Wine``` is installed with the dependencies wine-mono and wine-gecko with:

> sudo pacman -S wine wine-mono wine-gecko

The installation and version can be checked with:
 
> wine --version

and/or 

> wine64 --version

Both commands stating wine 9.9 is installed.

The installation is configured with:

> winecfg

Unlike the other installations, since I downloaded and installed wine-mono, winecfg will not ask to install it.

## Installing Winetricks and the .NET runtime

Winetricks was installed with:

> sudo apt install winetricks

The .NET 6 runtime can be installed by downloading the runtime installer from [here](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) by selecting the appropriate Windows ***.NET Desktop Runtime 6.0.32*** file. This is then installed with:

> wine ~/Downloads/windowsdesktop-runtime-6.0.32-win-x64.exe

***Note:*** It is also possible to install the current .NET 8 and the preview .NET 9 versions by downloading and installing the required file.


## Running a Windows program such as circularMT.exe

 To run ```circularMT``` download the program from [Here](https://github.com/msjimc/circularMT) to your Downloads folder and issue the command below:

> wine ~/Downloads/circularMT.exe 

This will open the program, which can be used as described in the [guide]( https://github.com/msjimc/circularMT/tree/master/Guide/README.md).

<hr />

![Figure 1](images/manjaro-cinnamon_figure1.jpg)

Figure 1

<hr />
