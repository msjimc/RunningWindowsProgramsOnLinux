# Centos stream  9:

Centos Stream  9 were installed on a 64 bit virtual machine with 4,096 MB of RAM, 4 processors and VirtualBOX: 20 GB hard disk or HyperV: dynamically resizing hard disk and was configured with default settings for a workstation with Gnome as the desktop.

***Note*** Centos appears not to have access to all the dependencies for Wine on run on Centos 64 bit to run 32 bit applications, but can run 64 bit Windows applications. Consequently, I download circularMT_64.exe below and not circular.exe.
If you need 32 bit programs to run on your installation, at the very bottom of this page is a section on installing from [source code](#installing-from-source-code) which may help.

The circularMT_64.exe file and the sequence.gb files were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Download folder (~/Downloads) using FireFox. 


## Preparation 

It is suggested that the computer is updated and rebooted before starting the installation:

> sudo dnf -y update  
> sudo reboot

## Installation

* **The account performing the installation must have admin rights.**

### Using the yum package manager

Wine can be installed on Centos Stream 9 using the yum package manager (with admin rights). Wine is not in the standard repositories and so you need to link to the Extra Packages for Enterprise Linux (EPEL) plus the crb repositories with the following command:

> sudo dnf install epel-release   
> sudo yum install dnf-plugins-core   
> sudo yum config-manager --set-enabled crb 

and then install the wine package with: 

> sudo yum install wine 

 This will start the installation process by downloading and then installing a number of packages after asking for permission to install them. Once completed, run winecfg to configure the installation:

 > winecfg

 This will ask to install wine-mono (Figure 1) and end when it shows a 2nd configuration dialogue box, which requires no modification.

![Figure 1](images/centos9_config.jpg)

Figure 1  Centos Stream 9

<hr />

## Running circularMT

Once installed, download circularMT_64.exe and the sequence.gb file from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to our Downloads folder (~/Downloads) using FireFox and the issue the following commands 64 bit programs:
 
> wine64 ~/Downloads/circularMT_64.exe  

<hr />

![Figure 1](images/centos9_figure1.jpg)

Figure 1  Centos Stream 9

<hr />

As with the other installations on other Linux and BSD systems, circularMT displays the file system in the style of a Windows OS rather than a Linux system (Figure 2).

<hr /> 

![Figure 2](images/centos9_figure3.jpg)

Figure 2 Centos Stream 9

<hr />

Once, a mitochondrial genome has been imported, it's map can be modified as shown in the [Guide](https://github.com/msjimc/circularMT/tree/master/Guide/README.md) (Figure 3).

<hr />

![Figure 3a](images/centos9_figure3.jpg)

Figure 3a Centos 9

<hr />

## Installing from source code

This folder contains a file [install.txt](install.txt) which contains the instructions to run from source code. The script refers to a wine-8.0.tar.xz, if you look in https://dl.winehq.org/wine/source/ you may find an earlier version of wine that will install correctly, however, the script takes a long time to run and I make no promises that it will work! 

```Wine``` was also installed on Centos by compiling the source code as described by __onlycliches__ on the AlmaLinux forum: [[Script] Compile WINE with 32-Bit App Support](https://forums.almalinux.org/t/script-compile-wine-with-32-bit-app-support/2556). This page contains a script that compiles both the 32 and 64 - bit versions of ```wine```. It appears that things have changed a little since it was written and so the script needed two extra lines adding.

For Centos Stream 9:

sudo yum install dnf-plugins-core
sudo yum config-manager --set-enabled crb

For Centos Stream 8:

sudo yum install dnf-plugins-core
sudo yum config-manager --set-enabled powertools

It seems powertools was renamed crb in Centos Stream 9

The script can be viewed as containing 3 stages the first downloads the require files and packages and requires user interaction to authorise the downloads, this may take ~5 mins. The next part compiles wine and may take serval hours, but doesn't require user interaction. The final part installs and configures wine and requires you to OK a few steps via dialogue box(es). This means you can start the installation and then after a few minutes leave it to run overnight and then finish off in the morning.

To run the installation script download the install.txt files from [here](install.txt) and then run it from a terminal with bash:

bash ~/Downloads/install.txt

(Assumes the file is in your accounts Downloads folder.)
