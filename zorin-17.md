# Zorin 17 core

## Starting point
Zorin Core 17 was successfully installed on a 64-bit virtual machine with 4,096 MB of RAM and 4 processors. On VirtualBox, a 25 GB hard disk was allocated, while Hyper-V was configured with a dynamically resizing hard disk. Both installations utilized the default settings and the GNOME desktop environment.

The circularMT.exe and the sequence.gb files were acquired from the ‘Program’ and ‘Example data’ sections within the [circularMT GitHub repository](https://github.com/msjimc/circularMT). These files were downloaded to the user’s Download directory using the Firefox browser. 

## Installation

Zorin Core 17, being derived from Ubuntu Jammy, follows a similar installation process for Wine. To prepare the system for 32-bit applications, the following command is used:

> sudo dpkg --add-architecture i386 

Next, the WineHQ repository key was added:

> sudo mkdir -pm755 /etc/apt/keyrings  
> sudo wget -O /etc/apt/keyrings/winehq-archive.key https://dl.winehq.org/wine-builds/winehq.key

After adding the key, the repository is included in the sources list:

> sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/jammy/winehq-jammy.sources


Update the package information:

> sudo apt update

Finally. install ```Wine``` with:

> sudo apt install --install-recommends winehq-stable

Verify the installed version of Wine:

> wine --version

 or

> wine64 --version

The output should confirm that Wine 9.0 is installed.

Finally, configure Wine with:

> winecfg

This command will prompt the installation of the wine-mono file, which is necessary for certain Windows applications. Afterward, the Wine configuration dialog window will appear, allowing you to set the desired Windows version.

## Installing Winetricks and the .NET 6 runtime

Winetricks can be installed with the following command:

> sudo apt install --install-recommends winetricks

Install the  .NET 6 runtime with:

> winetricks -q dotnetdesktop6

Its important to read the first few lines written to the terminal to see if you are using a 32-bit WinePrefix. if are or you encounter an error message stating you need to install the .NET runtime,  make a 32-bit specific Wine prefix using:

> WINEPREFIX="$HOME/.win32" WINEARCH=win32 wine wineboot

To install the runtime in the 32-bit Wine prefix, download the x86 .NET 6 runtime installer from the __.NET Desktop Runtime 6.0.32__ section of the [.NET download page](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) and install it with:

>  WINEPREFIX="$HOME/.win32" wine  ~/Downloads/windowsdesktop-runtime-6.0.32-win-x86.exe 

Note: If the application is a .NET program compiled with the ‘Any CPU’ option and does not run, try using binaries specifically compiled for an x86 OS. For example, [AgileStructure](https://github.com/msjimc/AgileStructure/tree/master/program) contains ‘Any CPU’ binaries that may not run on Zorin, but the binaries in the AgileStructure_x86 subfolder are suitable for a 32-bit environment.

## Running a windows application such as circularMT.exe

 To run ```circularMT``` download the program from [circularMT GitHub repository]( https://githud.com/msjimc/circularMT) to your Downloads folder and execute the following command in a terminal:

> wine ~/Downloads/circularMT.exe 

This will launch the program which can be used as described in the [circularMT guide]( https://github.com/msjimc/circularMT/tree/master/Guide/README.md).

<hr />

![Figure 1](images/Zorin-core-17_figure1.jpg)

Figure 1

<hr />
