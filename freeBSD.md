# FreeBSD 
FreeBSD 14.0-RELEASE was installed on a 64 bit virtual machine with 4,096 MB of RAM, 4 processors. On VirtualBox it had a 20 GB hard disk while on HyperV it used a dynamically resizing hard disk. The KDE desktop was installed using the following commands:

> pkg install --quiet --yes kde5 plasma5-sddm-kcm sddm xorg  
> sysrc dbus_enable="YES" && service dbus start  
> sysrc sddm_enable="YES" && service sddm start  

Firefox was then installed with: 

> pkg install www/firefox

The circularMT_64.exe file and the sequence.gb file were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Download folder (~/Downloads) using FireFox.

## Preparation and installation

* **The account performing the installation must have admin rights.**

If you have admin rights elevate the terminal to raised privileges with:

> su -l root

and then enter root's password.

The FreeBSD web site contains instructions on how to install Wine [here](https://docs.freebsd.org/en/books/handbook/wine/). It suggests that you first install wine-gecko which contains web browser functions that some programs expect:

>pkg install wine-gecko

Next it suggests installing wine-mono which is needed to run .NET applications:

> pkg install wine-mono

Once these have been installed wine can be installed using:

> pkg install wine

The version of wine64 can then be determined with:

> wine64 --version

This process installs wine64 version 9.0 which is the 64 bit version that requires 64 bit programs.

### Install 32-bit version of Wine

Once the 64 bit version of wine as been installed, a script is saved in /usr/local/share/wine/ to install the 32 bit version of wine using this command:

> /usr/local/share/wine/pkg32.sh install wine mesa-dri

The version of wine can then be determined with:

> wine --version 

This script installs wine32 version 9.0 which is the 32 bit version that required by 32 bit programs.

Finally, configure Wine with the following command:

> winecfg

This will also download wine-mono if you didn't run the pkg install wine-mono step earlier.

## Installing Winetricks and .Net runtime

Winetricks can be installed with the command (as root):

>  pkg install winetricks

and the the runtime installed with:

> winetricks -q dotnetdesktop6

for the .Net 6 runtime.

## Running a Windows program such as circularMT.exe

***Note:***   
FreeBSD will not run an application  with Wine from a terminal using root privileges, so return to your normal account with ```Ctrl``` + ```D``` before running circularMT_64.exe with:

> wine64 ~/Downloads/circularMT_64.exe

This should start circular_64.exe after a configuration step that only occurs when wine is run for the first time (Figure 1).

<hr />

![Figure 1](images/FreeBSD_14.0_figure1.jpg)

Figure 1: circularMT_64.exe running on FreeBSD 14.0-RELEASE with the KDE5 desktop.

<hr />

Once imported, the mitochondrial genome can be modified as described in the [Guide](https://github.com/msjimc/circularMT/tree/master/Guide/README.md) Figure 2.

<hr />

![Figure 2](images/FreeBSD_14.0_figure2.jpg)

Figure 2

<hr />
