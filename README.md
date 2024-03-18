# ubuntu_in_desktop
Troubleshoot booting Ubuntu on Lenovo ThinkCentre desktop alongside Windows 10 Pro. Address errors like missing graphics drivers and framebuffer issues for a seamless dual-boot setup.

# Booting Ubuntu on Lenovo ThinkCentre Desktop (Dual Boot with Windows 10 Pro)

## Overview

This guide documents the process of troubleshooting and booting Ubuntu on a Lenovo ThinkCentre desktop alongside Windows 10 Pro. It covers the errors encountered during boot, along with the solutions implemented to resolve them.

### System Specifications

- **Operating System:** Microsoft Windows 10 Pro
- **System Name:** DESKTOP-MK9FVKM
- **Manufacturer:** Lenovo
- **System Model:** 3157NW5
- **BIOS Version:** LENOVO 9QKT34AUS
- **BIOS Mode:** Legacy
- **Secure Boot State:** Unsupported
- **PCR7:** Binding not possible
- **Hardware Abstraction Layer Version:** "10.0.19041.3636"
- **Graphics:** Intel Corporation 2nd Gen Core Processor Family Integrated Graphics Controller

## Errors Encountered

1. **Error: /dev/dri/card0: no such file or directory**
   - Description: The system was unable to find the directory for the Direct Rendering Infrastructure (DRI).
   - Solution: Check kernel modules, update graphics drivers, and review Xorg configuration.

2. **Error: unable to find the valid framebuffer in device**
   - Description: The system was unable to find a valid framebuffer device, essential for displaying graphics.
   - Solution: Check GRUB configuration, reset Xorg configuration, and try a different display manager.

3. **Error: Graphics Drivers Not Installed**
   - Description: Graphics drivers were not installed, leading to display-related problems during boot.
   - Solution: Manually add `nomodeset` parameter to GRUB bootloader configuration.

## Troubleshooting Process

1. **Access GRUB Bootloader Terminal**
   - During boot, access the GRUB bootloader terminal by pressing a designated key (e.g., F12) on startup.

2. **Identify Errors**
   - Identify errors encountered during boot, such as missing directories, framebuffer issues, or graphics driver problems.

3. **Implement Solutions**
   - Based on the identified errors, implement appropriate solutions:
     - For DRI and framebuffer errors, check kernel modules, update drivers, and review configuration files.
     - For missing graphics drivers, manually add `nomodeset` parameter to GRUB bootloader configuration.

4. **Boot Ubuntu**
   - Manually add the `nomodeset` parameter to the boot command line:
     ```
     linux /boot/vmlinuz root=/dev/sda6 nomodeset
     initrd /boot/initrd.img
     boot
     ```
   - This command disables kernel mode setting and allows Ubuntu to boot successfully without encountering graphics-related issues.

## Conclusion

By following the troubleshooting process outlined in this guide, you were able to successfully boot Ubuntu on your Lenovo ThinkCentre desktop alongside Windows 10 Pro. These steps can be helpful for users facing similar issues during the dual-boot setup process.
