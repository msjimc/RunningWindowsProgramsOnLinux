# Raspberry Pi Desktop 

Raspberry Pi Desktop is an x86 version of Raspberry Pi OS (Raspbian) which runs on ARM processors. Both are derived from Debian Bullseye. Consequently it's not Raspberry Pi, but an OS with the feel of Raspberry Pi.

Raspberry Pi Desktop (2022-07-01-raspios-bullseye-i386.iso) was installed on a 64 bit virtual machine with 4,096 MB of RAM, 4 processors. VirtualBox used a 20 GB hard disk while HyperV used a dynamically resizing hard disk. Both installations were configured with default settings with the PIXEL desktop.

The circularMT_64.exe file and the sequence.gb file were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Download folder (~/Downloads) using FireFox.

## Preparation and installation

* **The account performing the installation must have admin rights.**

Unlike the Debian installation that used the package manager, its necessary to follow the [WineHQ install method](https://wiki.winehq.org/Debian) for Debian, since the repository contains a Wine 5.0 package rather than Wine 9.0.  

First set the architecture for 32 bit programs

> sudo dpkg --add-architecture i386 

Add the repository key:

> sudo mkdir -pm755 /etc/apt/keyrings   
> sudo wget -O /etc/apt/keyrings/winehq-archive.key https://dl.winehq.org/wine-builds/winehq.key

Download the source files (Raspberry Pi Desktop is based on Debian Bullseye)

> sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/debian/dists/bullseye/winehq-bullseye.sources

Install the stable version of Wine:

> sudo apt install --install-recommends winehq-stable

Finally, configure the installation with and download the wine-mono file:

> winecfg

## Installing Winetricks and .Net 6 (or above)

Winetricks is install with:

> apt-get install winetricks

Finally install the .Net 6 runtime with:

winetricks -q dotnetdesktop6

if this fails to work or you don't want to install Winetricks download the .Net 6 runtime (or 8/9) from  [here]
(https://dotnet.microsoft.com/en-us/download/dotnet/6.0) selecting the appropriate ***Windows*** 64 bit version from the __.NET Desktop Runtime 6.0.32__ section. Install the runtime with the command (the runtime file name may differ):

> wine windowsdesktop-runtime-6.0.32-win-x64.exe

This will open a dialogue box asking whether you want to install the runtime.

## Running a window application like circularMT


```Wine``` was then used to run circularMT with the following command:

> wine ~/Downloads/circularMT.exe

Once running, data can be imported as described in the [Guide](https://github.com/msjimc/circularMT/tree/master/Guide/README.md) (Figure 1). 


<hr />

![Figure 41](images/raspbian_pi_os_figure1.jpg)

Figure 1

<hr />

