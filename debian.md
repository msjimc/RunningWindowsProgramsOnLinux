# Debian 
Debian GNU/Linux trixie/sid was installed on a 64 bit virtual machine with 4,096 MB of RAM, 4 processors. VirtualBox used a 20 GB hard disk while HyperV used a dynamically resizing hard disk. Both installations were configured with default settings with the Xfce desktop.

The circularMT_64.exe file and the sequence.gb file were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Download folder (~/Downloads) using FireFox.

## Preparation and installation

* **The account performing the installation must have admin rights.**

The ```Synaptic package Manager``` app was opened and the ```Search``` icon was pressed to display the ```Find``` dialogue box. After entering the term: ***Wine*** and pressing the ```Search``` button, a list of packages was displayed. Scrolling down the list revealed the wine package.  Clicking on the check box by ***wine*** item displayed the dependencies, while pressing the ```Apply``` button installed ```wine``` and ```wine64``` (Figure 1).

<hr />

![Figure 1](images/debian_figure1.jpg)

Figure 1

<hr />

A terminal was opened and the installation checked (Figure 2) by entering the command:

>$  wine --version  
wine-9.0

(However on a Debian 11.9 installation this will install wine version 5.0 due to the packages available to the earlier build. This version is sufficient to run most programs without issue.) 

<hr />

![Figure 2](images/debian_figure2.jpg)

Figure 2: Wine 9.0 is installed on Debian GNU/Linux trixie/sid

<hr />

### Linking to the wine-mono file

You can either manually download the wine-mono file and link it to the Wine installation or run the winecfg command that will both link Wine to the wine-mono file and configure Wine.

#### winecfg

The command 
:

> winecfg

will both download the wine-mono file and link it to the Wine installation as well as configure your Wine environment.


#### Manually link to wine-mono

The [wine-mono-9.1.0-x86.msi](https://dl.winehq.org/wine/wine-mono/9.1.0/wine-mono-9.1.0-x86.msi) file was downloaded from https://dl.winehq.org/wine/wine-mono/9.1.0/ to the user's Download folder and in a terminal the following command was entered:

> wine uninstaller

or 

> wine64 uninstaller

which opened the ```Add/remove Programs``` dialogue box (Figure 3). Press the ```Install``` button to select the ***wine-mono-9.1.0-x86.msi*** (Figure 2: note the lower panel will remain blank and will only become populated when reopened). 

<hr />

![Figure 3](images/debian_figure2a.jpg)

Figure 3

<hr />

## Using Wine to run a Windows .Net program

```Wine``` was then used to run circularMT with the following command:

> wine ~/Downloads/circularMT.exe

When first run, ```Wine``` may undergo a configuration step before displaying the circularMT interface (Figure 3) if you didn't run winecfg after installing Wine.

Once running, data can be imported as described in the [Guide](https://github.com/msjimc/circularMT/tree/master/Guide/README.md). While circularMT is running on Debian, the file system will appear like a Windows based system rather than a Linux file system. While the user's Download folder is in /home/username/Downloads on Debian it appears to be in c:/users/<username>/Downloads/ to programs running with Wine. Once imported, the mitochondrial genome can be modified as described in the [Guide](https://github.com/msjimc/circularMT/tree/master/Guide/README.md) Figure 3.

<hr />

![Figure 3](images/Debian-trixie-Xfce.jpg)

Figure 3

<hr />

