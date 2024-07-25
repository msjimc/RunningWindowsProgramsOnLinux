# Mint 21.3 "Virginia" with the Mate desktop

## Starting point

Mint 21.3 "Virginia" was installed on a 64 bit virtual machine with 4,096 MB of RAM, 4 processors, with 40 GB hard disk (VirtualBox)  and was configured with the default settings. The chosen ISO image was pre-configured to use the Mate Desktop.

***Note:*** Mint 21.3 can not be installed on HyperV so only the virtualbox installation was tested.

The circularMT.exe file and the sequence.gb files were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Download folder (~/Downloads) using FireFox.

## Preparation and installation

* **The account performing the installation must have admin rights.**

Wine can be installed either quickly via the [package manager](#quick-route), the [official way](#official-route) as suggested by Wine or via a slowly a series of [commands listed below](#install-wine-9). Since the quick route installs Wine version 6, the official route ,version 8 and the slow route version 9, it may be best to use the slower route.

### Quick route 

Open the Package manager and search for ***wine*** (Figure 1)

![Figure 1](images/mintPackageFigure1.jpg)

Figure 1

<hr />

Click on the first Wine package and install by pressing the ```Continue``` button (Figure 2)

![Figure 2](images/mintPackageFigure2.jpg)

Figure 2

<hr />


Test the version with:

> wine --version

and 

> wine64 -- version

Both commands should suggest version 6 is installed.

### Install Wine 9 with apt and Wine download

First update Mint (optional) with:

> sudo apt update  
> sudo apt upgrade

Update the repository setting with:   
> sudo apt install dirmngr ca-certificates software-properties-common apt-transport-https curl -y

Next enable the 32 bit environment:  

> sudo dpkg --add-architecture i386

Install the GPG key:  
> curl -s https://dl.winehq.org/wine-builds/winehq.key | sudo gpg --dearmor | sudo tee /usr/share/keyrings/winehq.gpg > /dev/null

Get the Wine repository

> echo deb [signed-by=/usr/share/keyrings/winehq.gpg] http://dl.winehq.org/wine-builds/ubuntu/ jammy main | sudo tee /etc/apt/sources.list.d/winehq.list

Update the installation

> sudo apt update

and then install Wine 
> sudo apt install winehq-stable --install-recommends 

Finally test the installation with:  
> wine --version

and 

> wine64 --version

Version 9 should be installed for both the 32 and 64 bit versions.

### Configure Wine

To configure Wine use:

> winecfg

When the first dialogue box appears Install Wine-Mono (Figure 3)
and finally select the version of Windows you wish to emulate using the options at the bottom of the ```Wine configuration``` form (Figure 4).

![Figure 3](images/mintPackageFigure3.jpg)

Figure 3

<hr />

![Figure 4](images/mintPackageFigure4.jpg)

Figure 4

<hr />


## Installing Winetricks and .Net runtime

Winetricks can be installed with the command (as root):

>  sudo apt-get install winetricks

and the the runtime installed by downloading the runtime installer from [here](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) selecting the appropriate Windows ***.NET Desktop Runtime 6.0.32*** file. This is then installed with:

> wine ~/Downloads/windowsdesktop-runtime-6.0.32-win-x64.exe

***Note*** It is also possible to install the current .Net 8 and the preview .Net 9 versions by downloading and installing the required file.


## Running a Windows program

To run circularMT, download it to the accounts Download folder from [here](https://github.com/msjimc/circularMT/Program) and start with this command in a terminal:

> wine ~/Downloads/circularMT.exe

This will start circularMT.exe which can be used as if it was on a Windows PC (Figure 5)

![Figure 5](images/mintPackageFigure5.jpg)

Figure 5

<hr />