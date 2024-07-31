# KDE Neon:

## Starting point

KDE Neon (20240624-1012) was installed on a 64-bit virtual machine with 4,096 MB of RAM, 4 processors, and a 40 GB hard disk (VirtualBox). The installation was configured with the default settings and the KDE desktop environment.

The circularMT.exe and the sequence.gb files were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Downloads folder (~/Downloads) using Firefox.

## Preparation and installation

* **The account performing the installation must have admin rights.**

Wine can be installed quickly via the package manager, the official method suggested by Wine (see Ubuntu method), or slowly via a series of [commands listed below](#install-wine-9). The quick route installs Wine version 6, the official route installs version 8, and the slow route installs version 9. Therefore, it may be best to use the slower route

### Install Wine 9 with apt and Wine download

This based on the install described [here](https://wine.htmlvalidator.com/install-wine-on-kdeneon-base22.04.html).

Enable the 32 bit environment:  

> sudo dpkg --add-architecture i386

Install the Winehq repository key:  

> sudo mkdir -pm755 /etc/apt/keyrings  
> sudo wget -O /etc/apt/keyrings/winehq-archive.key https://dl.winehq.org/wine-builds/winehq.key

Get the required Wine files:

> sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/jammy/winehq-jammy.sources

Update the repository data:

> sudo apt update

Install these missing packages

> sudo apt install libpoppler-glib8:{i386,amd64}=22.02.0-2ubuntu0.*

Then install Wine 

> sudo apt install --install-recommends winehq-stable 

Finall, test the installation with:  

> wine --version

and 

> wine64 --version

Wine version 9 should be installed for both the 32-bit and 64-bit versions.

### Configure Wine

To configure Wine use:

> winecfg

This will prompt you to download the wine-mono package and then open a dialogue box, allowing you to perform more advanced tasks.

## Installing Winetricks and .Net runtime

Winetricks can be installed with this command (as root):

>  pkg install winetricks

and the runtime is installed by downloading the installer from [here](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) selecting the appropriate Windows ***.NET Desktop Runtime 6.0.32*** file, which is then installed with:

> wine ~/Downloads/windowsdesktop-runtime-6.0.32-win-x64.exe

***Note*** It is also possible to install the current .Net 8 and the preview .Net 9 versions by downloading and installing the required file.

## Running a Windows program

'To run circularMT, download it to the accounts Downloads folder from [here](https://github.com/msjimc/circularMT/Program) and start with this command in a terminal:

> wine ~/Downloads/circularMT.exe

This will start circularMT.exe which can be used as if it was on a Windows PC (Figure 5)'

![Figure 5](images/kde-neon_figure1.jpg)

Figure 5

<hr />
