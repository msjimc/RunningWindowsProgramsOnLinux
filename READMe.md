# Windows programs on a Linux desktop with Wine

While mainy programs designed to work only run on a Windows PC, it is possible to run many of them on Linux or macOS using [```Wine```](https://www.winehq.org/). According to Wine's [website](https://www.winehq.org): 
> Wine (originally an acronym for "Wine Is Not an Emulator") is a compatibility layer capable of running Windows applications on several POSIX-compliant operating systems, such as Linux, macOS, & BSD. Instead of simulating internal Windows logic like a virtual machine or emulator, Wine translates Windows API calls into POSIX calls on-the-fly, eliminating the performance and memory penalties of other methods and allowing you to cleanly integrate Windows applications into your desktop.

Basically, ```Wine``` sits in between a Windows application and the operating system and catches any messages they sent to each other and converts them from what they don't understand to something they do understand, a bit like how an translator allows a German speaker to have a conversation with a Spanish speaker. 

```Wine``` can work on a range of Unix inspired operating systems, so how it is installed depends on which flavour of Linux (or BSD or macOS) you are using. The ```Wine``` website has instructions for installing ```Wine``` on Ubuntu, Debian, Fedora, macOS, SUSE, Slackware and FreeBSD on its [downloads page](https://wiki.winehq.org/Download). However, unlike installing applications on Windows, the process can be a little involved for some systems. Consequently, below are links to four short guides that show how I installed ```Wine``` on openSUSE, Ubuntu, Debian and Centos via different routes. These guides expect you to have a reasonable understanding of how to install applications on Linux or the willingness to search online for the solution to any issues.

***Note***: The operating systems used in this guide were installed on two different types of virtual machines hosted: Oracle's VirtualBox on a Windows 10 computer and on Microsoft's Hyper-V on a Windows 11 computer, however, this should not affect how they functioned. The installation was performed on a freshly installed OS.

***Note***: The commands described to install ```Wine``` require admin/superuser rights which may mean that the installation needs to be done by the IT department on a work's computer. 

# Install guides 

While the guides below discuss the operation of ```circularMT``` on various Linux OS's, the installation of other programs is the same. If the program available as a ___*.msi___ files, install the application by issuing the command:

> wine ~/Downloads/myProgram.msi>

where the file "myProgram.msi' in the installation file that was downloaded to the Downloads folder in your Linux account Home folder.

* [Centos - Stream 8 and 9](centos_8_9.md)
 
* [Debian trixie](debian.md)

* [FreeBSD](FreeBSD.md)
  
* [openSUSE - 'Leap' 15.5:](openSUSE.md)

* [SlackWare - 15.0_RELEASE](slackware.md)

* [Ubuntu - 'Noble Numbat' 24.04:](ubuntu.md)

* [macOS](macOS.md)

## Common issues

* [wine32 is missing](#wine32-is-missing)
* [wine-mono is missing](#wine-mono-is-missing)

### "wine32" is missing

If you get the message below:

> it looks like wine32 is missing, you should install it.  
as root, please execute "apt-get install wine32"

open the Software & Updates form and select the Security and recommended updates option (Figure 1), enter your admin password (multiple times), close the form, update/reload if requested and then run the command:

> sudo apt-get install wine32

<hr />

![Figure 1](images/ubuntu_figure1b.jpg)

Figure 1

<hr />

### "wine-mono" is missing

If not prompted to do so during the set up you may have to add a wine-mono package to the installation. This can be downloaded from the wine-mono [web page](https://dl.winehq.org/wine/wine-mono/) (https://dl.winehq.org/wine/wine-mono/), for this installation the [wine-mono-9.1.0-x86.msi](https://dl.winehq.org/wine/wine-mono/9.1.0/wine-mono-9.1.0-x86.msi) file was used. To link this file to the ```wine``` installation use the ```wine``` uninstaller by entering:

> wine uninstaller   

in a terminal, pressing the ```Install``` button and selecting the file (Figure 2).

<hr />

![Figure 2](images/ubuntu_figure1.jpg)

Figure 2

<hr />
