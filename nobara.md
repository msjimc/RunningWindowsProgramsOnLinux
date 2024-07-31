# Nobara: 
Nobara 39 - Official (2024-01-24) was installed on a 64-bit virtual machine with 4,096 MB of RAM, and 4 processors. VirtualBox used a 20 GB hard disk, while Hyper-V used a dynamically resizing hard disk. Both installations were configured with default settings and the KDE desktop.

The circularMT_64.exe and the sequence.gb files were downloaded from the GitHub (https://github.com/msjimc/circularMT) 'Program' and 'Example data' folders to the user's Downloads folder (~/Downloads) using Chromium.

## Installation

When first installed, Nobara has Wine 8.2 (Staging) installed. After the strongly advised system update, Wine was upgraded to Wine 9.9 (Staging) (Figure 1)

<hr />

![Figure 1](images/nobara_figure1.jpg)

Figure 1

<hr />

While Wine is preinstalled it is not configured and requires winecfg to be run to download and install wine-mono:

> winecfg

## Installing Winetricks and .NET runtime

Winetricks may already be installed, and the command:

> winetricks

should launch Winetricks as a GUI application. If it isn't installed, try:

> sudo dnf install winetricks

Install the .NET runtime with:

> winetricks -q dotnetdesktop6

for the .NET 6 runtime. If the installation hangs, try the command:

> rm -rf ~/.wine ; WINEDLLOVERRIDES="winegstreamer=" winecfg

and rerun:

> winetricks -q dotnetdesktop6

If this fails to work or you don't want to install Winetricks, download the .NET 6 runtime (or 8/9) from  [here]
(https://dotnet.microsoft.com/en-us/download/dotnet/6.0), selecting the appropriate ***Windows*** 64-bit version from the __.NET Desktop Runtime 6.0.32__ section. Install the runtime with the command (the runtime file name may differ):

> wine windowsdesktop-runtime-6.0.32-win-x64.exe

This will open a dialogue box asking whether you want to install the runtime.

## Running circularMT.exe

 To run ```circularMT``` download the program from https://github.com/msjimc/circularMT to your Downloads folder and issue the command below:

> wine ~/Downloads/circularMT.exe 

This will open the program, which can be used as described in the [guide]( https://github.com/msjimc/circularMT/tree/master/Guide/README.md).

<hr />

![Figure 1](images/nobara_figure2.jpg)

Figure 1

<hr />
