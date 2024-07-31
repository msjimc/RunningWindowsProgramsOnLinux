# POP!_OS:

## Starting point
POP!OS 22.04 was installed on a 64-bit virtual machine with 4,096 MB of RAM, and 4 processors. For the virtualization platforms, VirtualBox was allocated a 25 GB hard disk, whereas Hyper-V was set up with a dynamically resizing hard disk. Both environments utilized the default configuration settings along with the GNOME desktop environment.

The circularMT.exe file and the sequence.gb files were obtained from the GitHub (https://github.com/msjimc/circularMT)  repository under the 'Program' and 'Example data' directories, respectively. These files were downloaded directly to the user’s Download folder via Firefox. 


## Installation

Initially, ```Wine``` was installed using the ***apt*** package installation tool with the command:

> sudo apt wine

However, this only installed ```Wine``` version 6.0. Since POP!_OS is based on Ubuntu - Jammy, Wine was installed using Wine's guide [Ubuntu Jammy](https://wiki.winehq.org/Ubuntu).  To allow the installation of 32-bit applications, the following command was executed in a terminal:

> sudo dpkg --add-architecture i386 

Next, the required repository was added by creating a new directory and downloading the WineHQ key:

> sudo mkdir -pm755 /etc/apt/keyrings  
> sudo wget -O /etc/apt/keyrings/winehq-archive.key https://dl.winehq.org/wine-builds/winehq.key

This was followed by adding the source locations. For Ubuntu Noble Numbat 24.04, the command to add the WineHQ repository is:

> sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/jammy/winehq-jammy.sources

Finally, Wine was installed using the following command:

> sudo apt install --install-recommends winehq-stable

After installation, Wine was configured and associated the wine-mono file with winecfg:

> winecfg

This creates the required Wine Prefix and allows the user to install wine-mono via a dialogue box.

## Check the installation

To verify the installed version of Wine, the following commands can be used:

> wine --version  

and 

> wine64 -- version

This confirmed that Wine 9.0 and Wine64 9.0 had been installed on the system.

## Installing the .NETt runtime

The runtime can be installed by first downloading the installer for the ***.NET Desktop Runtime 6.0.32***. This can be done by visiting the [.NET download page](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) and selecting the appropriate file for Windows. Once downloaded, the runtime is installed using the following command in the terminal:

> wine ~/Downloads/windowsdesktop-runtime-6.0.32-win-x64.exe

***Note***  It’s also possible to install the latest versions, such as .NET 8 or the preview version of .NET 9, by downloading and installing the corresponding files from the official .NET website

## Running Windows applications such as circularMT.exe

 To run ```circularMT```, download the program from its [GitHub repository]( https://github.com/msjimc/circularMT), to your Downloads folder and execute the following command in the terminal:

> wine ~/Downloads/circularMT.exe 

Once started, circularMT can be used as if it were on a Windows PC (Figure 1).

<hr />

![Figure 1](images/pop_OS_figure1.jpg)

Figure 1

<hr />
