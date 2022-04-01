# Ubuntu Subsystem İnstallation Guide
Welcome to ubuntu Subsystem installation guide. This guide walks you through ubuntu terminal installation, enabling Windows Subsystem for Linux (WSL) and running Visual Studio Code in WSL using Remote - WSL extension.

## Prerequisites
You need Visual Studio Code installed.

## Install a Linux distro
You can install Linux distributions from the Microsoft Store. You can use the store app, or search for a Linux distro in the Windows search bar. Choose the Linux distribution you want to install (for example Ubuntu) and follow the prompts.

![SharedScreenshot(0)](https://user-images.githubusercontent.com/90481141/146905824-a48ea7bc-61cc-4385-97e5-c4f9b313a90b.jpg)
Select Install.

And when done, select Launch to get started. This will open a Linux terminal and complete the installation. You'll need to create a user ID and password since you are setting up a full Linux instance. You are now running Linux on Windows.

![SharedScreenshot2](https://user-images.githubusercontent.com/90481141/146905879-f837355c-1350-4628-984b-efea503d10e4.jpg)

## Install the extension
The Remote - WSL extension enables you to run Visual Studio Code within the Windows Subsystem for Linux (WSL).

![SharedScreenshot3](https://user-images.githubusercontent.com/90481141/146905911-5a348c52-5732-4b11-861c-27231e9a5e7a.jpg)

## Enable WSL

Windows Subsystem for Linux (WSL) is an optional feature on Windows 10. You can enable it through the Windows Features dialog or PowerShell.

### Windows Features dialog

In the Windows search bar, type 'features' to bring up the Turn Windows Features on and off dialog. Scroll down and check Windows Subsystem for Linux.

![Adsız](https://user-images.githubusercontent.com/90481141/146906134-fb2751d3-b044-4f20-819a-ec70e0839147.png)

Select OK and you will be prompted to restart Windows.

![Adsız1](https://user-images.githubusercontent.com/90481141/146906171-a93df0e8-8863-4460-ab48-458064fef8c7.png)

Finally, you should choose the Ubuntu (WSL) option from the Visual Studio Code terminal options. 
## Congratulations!
Congratulations, you've successfully completed this guide!
