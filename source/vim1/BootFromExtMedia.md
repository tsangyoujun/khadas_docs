title: Boot Images from External Media
---

There are many images that are designed to run from an SD Card or Thumbdrive (U-Disk). For example, [LibreELEC](http://forum.khadas.com/t/libreelec-for-khadas-vim-sd-usb-emmc/793), [Armbian images](http://forum.khadas.com/t/armbian-kodi-ubuntu-debian-for-sd-usb-emmc/825) and [Khadas SD images](/vim1/Firmware.html#SD-USB-Installation). This tutorial is about how to boot these images.

In order to boot images from external media you must make sure:
* Android is running on the eMMC
* Activate the Multi-Boot

For different images you may need different Android versions.
* LibreELEC / Ubuntu with Linux 3.14: You need **Android M** or the latest **Android N (V180207 or later)** running on the eMMC.
* Ubuntu with Linux 4.9: You need **Android O** running on eMMC.

### 1. Write image to SD Card or Thumbdrive (U-Disk)
* Use `dd` on Ubuntu command line
```
$ sudo dd if=/path/to/image of=/dev/sdX bs=8M
```
* Use `Win32DiskImager` on Windows. Please refer to [Install LibreELEC Via Windows PC](/vim1/InstallLibreELEC.html#On-Windows-PC).

### 2. Prepare DTB
You need to choose different dtb for VIM1 and VIM2.
* VIM1: Copy `kvim.dtb`, `kvim_linux.dtb` or `meson-gxl-s905x-khadas-vim.dtb` to `/boot` and rename it to `dtb.img`.
* VIM2: Copy `kvim2.dtb`, `kvim2_linux.dtb` or `meson-gxm-khadas-vim2.dtb` to `/boot` and rename it to `dtb.img`.

### 3. Activate the Multi-Boot
Two ways to activate the multi-boot:
1). Via [Keys mode](/vim1/HowtoBootIntoUpgradeMode.html)
2). Activate multi-boot via Android.
* Enter `Settings>About Device->System->updates`
* Click select and choose `aml_autosript.zip`
* Click update, then the system will reboot and boot from external media image
**Note: Don't use PC USB host to supply the power, or will fail to activate multi-boot!**

### NOTICE
* Android N has a permission issue. You cannot use it to boot from your external media image without damaging your SD card.

* Android O also has a permission issue. If you want to boot Ubuntu with Linux 4.9 please refer to [this reply](http://forum.khadas.com/t/armbian-kodi-ubuntu-debian-for-sd-usb-emmc/825/109).
