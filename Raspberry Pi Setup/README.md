# Raspberry Pi Setup

## Create bootable SD with raspios to update EEPROM
Boot to raspios
sudo rpi-eeprom-update -a
sudo reboot

## Prepare the disk for UEFI firmware
sudo diskutil eraseDisk FAT32 NAME MBRFormat /dev/disk2

download firmware-master.zip and RPI4_UEFI_Firmware_vX.X.zip
wget https://codeload.github.com/raspberrypi/firmware/zip/master 
wget https://github.com/pftf/RPi4/releases/

Copy all the folder boot from firmware-master.zip to SD card and remove all kernel img files
Copy all files from RPI4_UEFI_Firmware_vX.X to SD card

Download VMware-VMvisor-Installer-7.0.0-xxxx.aarch64.iso
Copy iso to tempoary USB using a program like unetbootin

Boot drive pressing ESC to access UEFI menu
Device Manager > Raspberry Pi Configuration > Advanced Configuration
Limit RAM to 3 GB > Disabled

Boot Maintenance Manager > Boot Options > Change Boot Order

On main menu click Continue to exit the BIOS and start the ESXi Installer

The familiar ESXi installation wizard starts.

Quickly hit the SHIFT and O (letter O) key at the same time
At the bottom of the screen, append to the existing text: autoPartitionOSDataSize=8192

Press Enter to continue standard install, ESXi will use 8GB for installation and the rest should be available for a datastore.

Remove install media and reboot.  Login to DCUI.
Check storage, you should see datastore1 pre-configured with remaining USB storage.
