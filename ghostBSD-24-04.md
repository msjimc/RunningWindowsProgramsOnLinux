# GhostBSD 
GhostBSD 14.0-RELEASE was installed on a 64 bit virtual machine with 4,096 MB of RAM, 4 processors and a 20 GB hard drive on VirtualBox or  dynamically resizing hard disk with HyperV. The default desktop 'Mate' was installed.

## Preparation and installation

* **The account performing the installation must have admin rights.**

If you have admin rights elevate the terminal to raised privileges with:

> su -l root

and then enter root's password.

The FreeBSD web site contains instructions on how to install Wine [here](https://docs.freebsd.org/en/books/handbook/wine/). Since GhostBSD is based on FreeBSD the instructions should work here too. It suggests that you first install wine-gecko which contains web browser functions that some programs expect:

>pkg install wine-gecko

Next it suggests installing wine-mono which is needed to run .NET applications:

> pkg install wine-mono

Once these have been installed wine can be installed using:

> pkg install wine

The version of wine can then be determined with:

> wine64 --version

This installation installs wine64 which is the 64 bit version that requires 64 bit programs 

***Note:***  
GhostBSD will not run an application from a terminal using root privileges, so return to your normal account with ```Ctrl``` + ```D``` before running circularMT_64.exe with:

> wine64 ~/Downloads/circularMT_64.exe

This should start circular_64.exe after a configuration step that only occurs when wine is run for the first time (Figure 1).

<hr />

![Figure 1](images/GhostBSD_24-04_figure1.jpg)

Figure 1: circularMT_64.exe running on GhostBSD - 24.04 with the default Mate desktop.

<hr />

Once imported, the mitochondrial genome can be modified as described in the [Guide](https://github.com/msjimc/circularMT/tree/master/Guide/README.md) Figure 2.

<hr />

![Figure 2](images/GhostBSD_24-04_figure2.jpg)

Figure 2

<hr />
