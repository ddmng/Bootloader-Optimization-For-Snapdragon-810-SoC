# Bootloader-Optimization-For-Snapdragon-810-SoC
Optimizing Bootloader by Disabling 4 Cores Cluster of Snapdragon 810 SoC 

Near the end of 2016, we saw a volley of reports from multiple users claiming their Nexus 6P units were inexplicably entering random bootloops, a problem seemingly separate from the early shutdowns that plagued the phone around the same time. This was different, and while reduced battery life is certainly bad, the bootloops essentially turned the smartphone into paperweight.

Users who faced this issue quickly sunk into despair as there was no remedy in sight. No amount of data wiping or re-flashing of factory images seemed to solve the problem, indicating that the issue was hardware-related, possibly a problem in the SoC. This wouldn’t be the first time for one of Google’s devices to enter devastating brick or bootloop states: the Nexus 7 saw widespread bricks upon receiving its original Lollipop OTA, and the LG-manufactured Nexus 5X suffered the same fate as many LG phones with a hardware-related bootloop as well.

Download the latest ADB and Fastboot binaries and extract them to an easily accessible folder on your computer.
Download and install the Google USB Driver if you are running Windows.
Download N2G48B_4Cores.img and save it to the same directory where you saved the ADB and Fastboot binaries.
Optional: If you want to use TWRP recovery on your fixed Nexus 6P, you will need to use a modified version. Download twrp3_1_1_4Cores.img and save it to the directory where you saved the ADB and Fastboot binaries.
Optional: If you want to speed up your fixed Nexus 6P, you can flash a modified version of XDA Recognized Developer flar2‘s Elemental X Kernel. Download EX4_1_1_4Cores.zip and save it to your downloads directory.
Plug your phone in to your computer.
Open up a command prompt or terminal in the same directory where you saved the ADB and Fastboot binaries. On Windows, you can easily do this by holding shift and right-clicking, then selecting “open command prompt here.”
Enter the following command: fastboot devices
If you see your device’s serial number, you are ready to move on. If not, you will need to try re-installing the drivers.
Important: your phone’s bootloader MUST be unlocked in order to flash these modified images. If your bootloader is already unlocked, skip the following 2 steps.
Start the process to unlock your phone’s bootloader by entering the following command: fastboot flashing unlock
Using the volume and power keys, confirm that you want to unlock the bootloader. THIS WILL WIPE EVERYTHING ON YOUR PHONE’S INTERNAL STORAGE. But it’s either this or deal with a multi-hundred dollar brick. Your choice!
Now enter the following command to flash the modified boot image: fastboot flash boot N2G48B_4Cores.img
Optional: If you want to flash TWRP, then enter: fastboot flash recovery twrp3_1_1_4Cores.img
Reboot your phone by typing: fastboot reboot
After some minutes (it may take awhile), you should see your phone’s boot animation and eventually the lockscreen. Congrats, you’ve saved your phone!
Optional: If you want to improve the performance and you flashed TWRP, copy the modified Elemental X kernel over to your phone’s storage, boot into TWRP, and flash the custom kernel. You can choose to overclock the little cluster during setup to squeeze a bit more performance out of your phone as well.
