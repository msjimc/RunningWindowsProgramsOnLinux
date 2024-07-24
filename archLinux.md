# Arch Linux:

## Starting point
Arch Linux 2024.06.01 was installed on two 64 bit virtual machines with 4,096 MB of RAM, 4 processors. The VirtualBox virtual machine had a 25 GB hard disk while HyperV's virtual machine had a dynamically resizing hard disk. Both installations were installed using the ***archinstall*** script with default settings and the gnome desktop.

The circularMT.exe file and the sequence.gb files were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Download folder using FireFox. 

## Installation

Before ```Wine``` can be installed the multilib repository needs to be enabled. This is done by editing the ***/etc/pacman.conf*** file and uncommenting two lines:

Original: 

> #[multilib]   
> #Include = /etc/pacman.d/mirrorlist

Changed too:

>[multilib]  
> Include = /etc/pacman.d/mirrorlist

It is then recommended to do a full system update:

> sudo pacman -Syu

```Wine``` is installed with the dependencies wine-mono and wine-gecko by:

> sudo pacman -S wine wine-mono wine-gecko

The installation and version can be checked with:
 
> wine --version

and/or 

> wine64 --version

with both commands stating wine 9.11 is installed.

The installation is configured with:

> winecfg

If this hangs try:

> rm -rf ~/.wine ; WINEDLLOVERRIDES="winegstreamer=" winecfg

and rerun winecfg.

## Installing Winetricks and a .Net runtime

Winetricks can be installed with the command:

> pacman -S winetricks

and the the runtime installed with:

> winetricks -q dotnetdesktop6

for the .Net 6 runtime. If the installation hangs try the command:

> rm -rf ~/.wine ; WINEDLLOVERRIDES="winegstreamer=" winecfg

and rerun winetricks -q dotnetdesktop6


## Running circularMT.exe

 To run ```circularMT``` download the program from https://githud.com/msjimc/circularMT to your Downloads folder and issue the command below:

> wine ~/Downloads/circularMT.exe 

This will open the program which can be used as described in the [guide]( https://github.com/msjimc/circularMT/tree/master/Guide/README.md).

<hr />

![Figure 1](images/arch_2024_06_01_figure1.jpg)

Figure 1

<hr />
