# Linux_surface_pro
Installing Linux on Microsoft Surface Pro 4
Installing Fedora Linux Workstation 40 on a Microsoft Surface Pro 4 Tablet

Installing Fedora Linux Workstation 40 on a Microsoft Surface Pro 4 Tablet



Hardware Needed:
USB drive
Microsoft Surface Pro 4 Tablet (Obviously)
USB Docking Station (If needed)
USB mouse (If needed)
Other computer to write bootable USB (I used a Windows 11 PC, but any OS will suffice)
Software Needed:
Fedora workstation ISO (here). *** You should be able to do the same with another distro of your liking.***
Any program that will write an ISO to a USB and make it bootable. I used Balena Etcher. You can get it here.



***Backup all of your important files to a cloud platform or to another hard drive before beginning the installation. ***

Creating a bootable USB

Go to  https://fedoraproject.org/workstation/download and download the ISO file. 
Insert your USB drive and open your program that will write the iso to the USB. 
Remember that by writing the iso file to the USB will delete all of the contents of the USB. Be sure to backup any of these files if needed. 
Follow the instructions to write the ISO to the USB. 
Once completed, remove the USB and connect it to the Surface.

*** To be on the safeside, connect the USB dock station and connect the USB drive and mouse, in case you cannot use your trackpad for the next steps.***

Booting from USB on Microsoft Surface
We have to get into the BIOS to make sure that we can boot from the USB.

Turn on your surface device and immediately hold the power and volume up buttons. If it is already on, restart and follow the same instructions.
Once you are in the BIOS, go to the security tab and do the following:
Secure Boot - Change the configuration to NONE. 
Disable TPM
We need to boot from the USB. Go to the boot configuration and do the following:
Uncheck the box Windows Boot Manager.
Check the USB option. 
Exit the BIOS and the computer will restart.


Fedora Live 
***Only do the next step if you intend to install your Linux OS on the current drive.***
You can decide to try Fedora before installing it. I decided to install it, but I ran into an issue. I tried to go through the installation steps but received an error, stating, “Active Drive”. This is due to me not disabling Bitlocker. As I wanted to completely wipe my hard drive for a fresh install, I followed these steps while in the Fedora Live environment:

Open the terminal and install the gdisk command, which will be used to wipe the drive.   sudo dnf install gdisk
Use the following command to see the system’s storage devices:  lsblk
Search for the main drive that should end in /dev/sda or /dev/nvme0n1.
Enter the following command to wipe the drive: sudo gdisk /dev/your_harddrive_name
At this point, your hard drive should be erased and ready for your install. 
Click on the “Install Fedora” icon and follow the prompt to install Fedora OS.
Once the install is complete and the computer restarts, you can remove your USB drive. 
You should be able to boot right into your new install of Fedora. However, if for some reason you cannot, it could be an issue with the boot order. You will need to restart your surface and go into the bios to change the boot order. I did this to be on the safe side, and it automatically changed the boot order to the new Fedora install.

Exploring your new Fedora Install
Observations: Right from my install, I was able to use the keyboard, mouse track pad and wifi. However, my touchscreen was not working. 

Thanks to the kind contributors of the Linux - Surface project, I was able to download the kernel for my surface and Linux distro, which I found here. After installing the proper repositories, linux surface kernel and its dependencies, I was able to successfully use the touch screen functionality. The camera is not working, but that isn’t a problem at this point. I will work on finding a solution to this. I have also installed Waydroid, which runs as a container, to use certain Android apps. I was able to share a folder from my host Linux system to my Android x86 OS on Waydroid. I will upload my procedure at a later time. 
This has been a nice project to reuse an older electronic device. 



