# MX Linux 
MX Linux 23.3 KDE was installed on a 64 bit virtual machine with 4,096 MB of RAM, and 4 processors. VirtualBox used a 20 GB hard disk while Hyper-V used a dynamically resizing hard disk. Both installations were configured with default settings with the Xfce desktop.

The circularMT.exe and the sequence.gb files were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Downloads folder (~/Downloads) using Firefox.

## Preparation and installation

* **The account performing the installation must have admin rights.**

The ```MX Package Installer``` app was opened, and the term: ***Wine*** was entered in the upper right-hand text area. Initially, a single entry for Wine appeared before the other packages were added to the list. In the larger list, Wine can be found under the Misc subsection (Figure 1). Checking Wine and pressing the Install button installed ```wine``` and ```wine64``` (Figure 1). The installation imported the required wine-mono file and also ran the winecfg configuration step (Figure 2).

<hr />

![Figure 1](images/mx-figure1.jpg)

Figure 1

<hr />

![Figure 2](images/mx-figure2.jpg)

Figure 2

<hr />

A terminal was opened, and the installation checked (Figure 2) by entering the command: 

>  wine --version  

This indicated that Wine 8.12 was installed. 

<hr />

![Figure 3](images/mx-figure3.jpg)

Figure 3

<hr />

## Installing Winetricks and .NET Runtime

Winetricks can be installed with the command (as root):

>  sudo apt-get install winetricks

The runtime installed via Winetricks with:

> winetricks -q dotnetdesktop6

## Using Wine to run a Windows .NET program

```Wine``` was then used to run the .NET application circularMT with the following command:

> wine ~/Downloads/circularMT.exe


Once running, data can be imported as described in the [Guide](https://github.com/msjimc/circularMT/tree/master/Guide/README.md). While circularMT is running on MX Linux, the file system will appear like a Windows-based system rather than a Linux file system. For example, while the user's Downloads folder is in /home/username/Downloads on MX Linux it appears to be in c:/users/<username>/Downloads/ to programs running with Wine. Once imported, the mitochondrial genome can be modified as described in the [Guide](https://github.com/msjimc/circularMT/tree/master/Guide/README.md) (Figure 4).

<hr />

![Figure 4](images/mx-figure4.jpg)

Figure 4

<hr />

