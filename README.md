# Windows programs on a Linux or macOS desktop with Wine

<img align="right" src="images/macOS_circularMT_intro.png">

While many programs are designed to run only on Windows PCs, it is possible to run most of them on Linux, BSD or macOS computers using [```Wine```](https://www.winehq.org/). According to Wine's [website](https://www.winehq.org): 
> Wine (originally an acronym for "Wine Is Not an Emulator") is a compatibility layer capable of running Windows applications on several POSIX-compliant operating systems, such as Linux, macOS, & BSD. Instead of simulating internal Windows logic like a virtual machine or emulator, Wine translates Windows API calls into POSIX calls on-the-fly, eliminating the performance and memory penalties of other methods and allowing you to cleanly integrate Windows applications into your desktop.

Basically, ```Wine``` sits in between a Windows application and the operating system, intercepts any messages they send to each other and converts them from what they don't understand to something they do understand. This results in a program running as if it is on a Windows PC while in fact, it running in a Linux environment.

```Wine``` can work on a range of Unix inspired operating systems, such as various flavours of Linux, BSD and macOS. While these operating systems have many similarities they tend to differ in how software is installed and which software repositories they favour. Consequently, how ```Wine``` is installed varies from operating system to operating system. The ```Wine``` website has instructions for installing ```Wine``` on Ubuntu, Debian, Fedora, macOS, SUSE, Slackware and FreeBSD on its [downloads page](https://wiki.winehq.org/Download). However, unlike installing applications on Windows, the process can be a little involved for some systems. Consequently, this repository contains a number of short guides that show how I installed ```Wine``` on:  

|OS|Comments|
|-|-|
|Arch Linux 2024.06.01 |Installs .NET Runtime plus Wine-Mono|   
|CentOS - Stream 9|Installs just 64-bit Wine|
|Debian - Trixie|Installs .NET Runtime plus Wine-Mono|  
|Elementary OS 7.1|Installs .NET Runtime plus Wine-Mono|  
|EndeavourOS - Gemini|Installs .NET Runtime plus Wine-Mono|
|Febora 40| Installs .NET Runtime plus Wine-Mono|  
|FreeBSD - 14.0_RELEASE|Installs .NET Runtime plus Wine-Mono|   
|Garuda - Xfce (240428)|Installs .NET Runtime plus Wine-Mono|
|GhostBSD - 24.04| Installs .NET Runtime plus Wine-Mono|   
|KDE Neon (20240624)|Installs .NET Runtime plus Wine-Mono| 
|macOS|Installs .NET Runtime plus Wine-Mono (but not Winetricks)|
|Manjaro - Cinnamon 23.0.1| Installs .NET Runtime plus Wine-Mono (but not Winetricks)|
|Mint 21.3 (with Mate)| Installs .NET Runtime plus Wine-Mono|
|MX Linux 23.3 (KDE)|Installs .NET Runtime plus Wine-Mono|
|Nobara 39|Installs .NET Runtime plus Wine-Mono|
|openSUSE - Leap 15.5| Installs .NET Runtime plus Wine-Mono|
|POP! OS 22.02 (Gnome)|Installs .NET Runtime plus Wine-Mono (but not Winetricks)| 
|Raspberry Pi Desktop|Not attempted yet|  
|SlackWare - 15.0_RELEASE|Installs .NET Runtime plus Wine-Mono|  
|Ubuntu - Noble Numbat 24.04|Installs .NET Runtime plus Wine-Mono|  
|Zorin - Core 17 |Installs .NET Runtime plus Wine-Mono|

***Note:*** Wine-Mono is required for programs using the .NET 2 to 5 frameworks.  
***Note:*** .NET Runtime is required for programs using the .NET 6 to 9 Runtime installation.  
***Note:*** Winetricks helps with some tasks, but is not essential for this work. Where the .NET Runtime was installed with Winetricks it could also have been installed by downloading the Runtime installation file and installing with Wine as shown for the [Elementary OS](elementaryOS.md#installing-winetricks-and-net-runtime).

The distros were chosen because they were on the Wine download page, in the top 10 most popular distros over the last 12 months (ending June 2024) on the [DistroWatch.com](https://distrowatch.com/dwres.php?resource=popularity) or because I'd worked with them in the recent past. For example, CentOS is a popular OS for HPC and headless servers in British universities.

I attempted to use a few other distros that ultimately ended in failure. These include a number of BSD distros which failed as their maintainers viewed desktops with disdain! I give up on Gentoo as the installation seemed to be a task that was never going to end: The installation videos on YouTube were over 2 hours long. I also tried Scientific Linux as it seemed to be geared toward science-type users, but give up since it has now been superseded by CentOS and none of the package managers seemed to work. Finally, CachyOS would not run on either a VirtualBox or Hyper-V for different reasons.  
     
These guides assume you to have the OS installed and posses a reasonable understanding of how to install applications on them, or the willingness to search online for the solution to any issues. 

***Note***: The operating systems used in this guide were installed on two different types of virtual machines hosts: Oracle's VirtualBox on a Windows 10 computer and on Microsoft's Hyper-V on a Windows 11 PC, however, this should not affect how they functioned. The installation was performed on a freshly installed and updated virtual machine.

***Note***: The commands describing how to install ```Wine``` require admin/superuser rights which may mean that the installation needs to be done by the IT department on a work computer. 

While the guides below discuss the operation of ```circularMT``` on various Linux OSs, the installation of other programs is the same. If the program is available as a ___*.msi___ file, install the application by issuing the command:

> wine ~/Downloads/myProgram.msi

where the file "myProgram.msi' in the installation file that was downloaded to the Downloads folder in your account's Home folder. If the program doesn't need installing and was just downloaded on to your computer it can be run by issuing the following command in a terminal:

> wine ~/Downloads/myProgram.exe

or for 64-bit programs

> wine64 ~/Downloads/myProgram_64.exe

where myProgram is the executable files which in this case is in your account's downloads folder.

## Install guides 

* [Arch Linux 2024.06.01](archLinux.md)
* [CentOS - Stream 9](centos_9.md) 
* [Debian trixie](debian.md)
* [Elementary OS](elementaryOS.md)
* [EndeavourOS Gemini 2024-04-20](endeavourOS.md)
* [Fedora release 40](fedora.md)
* [FreeBSD 14.0-RELEASE](freeBSD.md)
* [Garuda - Xfce](garuda.md)
* [GhostBSD 24.04](ghostBSD-24-04.md)
* [KDE Neon](kde-neon.md)
* [macOS Mojave 10.14.6](macOS.md)
* [Manjaro - Cinnamon 23.0.1](manjaro.md)    
* [Mint 21.3](mint-21-3-mate.md)
* [MX Linux 23.2 KDE](mx-Linux-KDE.md)
* [Nobara 39](nobara.md)
* [openSUSE - 'Leap' 15.5:](openSUSE.md)
* [POP! OS](pop_os.md)
* [SlackWare - 15.0_RELEASE](slackware-15-0_RELEASE.md)
* [Raspberry Pi Desktop](raspberry_Pi_Desktop.md)
* [Ubuntu - 'Noble Numbat' 24.04:](ubuntu.md)
* [Zorin - Core 17.1](zorin-17.md)


## Installing the .NET framework

Some .NET applications require the .NET Runtime/Frame work to be installed. Currently there are versions 6 to 8 with version 9 in preview. The installation of these Runtimes requires WineTrick to be installed as described in each guide above.

## Common issues

* [wine32 is missing](#wine32-is-missing)
* [Wine-Mono is missing](#Wine-Mono-is-missing)

### "wine32" is missing

If you get the message below when attempting to run wine on Ubuntu:

> it looks like wine32 is missing, you should install it.  
as root, please execute "apt-get install wine32"

open the Software & Updates form and select the Security and recommended updates option (Figure 1), enter your admin password (multiple times), close the form, update/reload if requested and then run the command:

> sudo apt-get install wine32

<hr />

![Figure 1](images/ubuntu_figure1b.jpg)

Figure 1

<hr />

### "Wine-Mono" is missing

If not prompted to do so during the set up step, you may have to add a Wine-Mono package to the installation. This can be downloaded from the Wine-Mono [web page](https://dl.winehq.org/wine/Wine-Mono/) (https://dl.winehq.org/wine/Wine-Mono/), for this installation the [Wine-Mono-9.1.0-x86.msi](https://dl.winehq.org/wine/Wine-Mono/9.1.0/Wine-Mono-9.1.0-x86.msi) file was used. To link this file to the ```wine``` installation use the ```wine``` uninstaller by entering:

> wine uninstaller

or 

> wine64 uninstaller

in a terminal, pressing the ```Install``` button and selecting the file (Figure 2). The Wine Mono Runtime and Wine Mono Windows Support entries will only appear if the form is closed and then reopened.

<hr />

![Figure 2](images/ubuntu_figure1.jpg)

Figure 2

<hr />
