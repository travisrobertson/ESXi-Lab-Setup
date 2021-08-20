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

Continue standard install, ESXi will be installed on a dedicated USB drive.  A second USB drive will be required if you wish to create a local datastore.

