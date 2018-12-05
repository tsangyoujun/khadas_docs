title: VIM1 Beginners Guide
---

# VIM1 Power Supply
Although your VIM1 SBC is compatible with various types of power supplies, these are the recommended specs for the best performance-output and stability.*

1. 5V, 2000mA Power Adapter
2. USB-A to USB-C Cable

**Learn More:**
* [Extra Power Input For Khadas VIMs](https://docs.khadas.com/vim1/ExtraPowerInput.html)
* [Khadas VIM Specifications](https://www.khadas.com/vim)
* [Khadas Shop - Power Adapter](https://www.khadas.com/product-page/power-adapter)
* [Khadas Shop - USB-C Cable](https://www.khadas.com/product-page/usb-c-cable)

# Displays & User Input
These items are useful when you need to connect your VIM1 SBC to an external display + keyboard mouse + remote control, for use as a desktop computer or media center.

1. 4K HDMI 2.0 Cable
2. HDMI-Compatible 1080P/4K Monitor
3. Wireless USB Keyboard + Mouse
4. CeC-Compatible Remote Control

**Learn More:**
* [Khadas Shop - HDMI Cable](https://www.khadas.com/product-page/hdmi-cable)
* [Khadas Shop - Remote Control](https://www.khadas.com/product-page/ir-remote)
* [Amazon - Wireless Keyboard + Mouse](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Delectronics&field-keywords=wireless+keyboard+and+mouse&rh=n%3A172282%2Ck%3Awireless+keyboard+and+mouse)

# Making Bootable/Burning SD-Cards/Thumbdrives
These items are useful when you want to upgrade your VIM1 SBC's operating system via SD-Card or Thumbdrive (Burning Cards). Or if you want to run operating systems that can only be run from external media (Booting Cards) like LibreELEC.

1. 8GB or Larger, SD-Card
2. SD-Card Reader
3. Laptop / Desktop PC
4. 8GB or Larger, USB-Thumbdrive (U-Disk)

**Learn More:**
* [Booting Card Vs Burning Card](https://docs.khadas.com/vim1/BootingCardVsBurningCard.html)
* [Upgrade Using SD-Card](https://docs.khadas.com/vim1/UpgradeViaTFBurningCard.html)
* [Boot From External Media](https://docs.khadas.com/vim1/BootFromExtMedia.html)
* [Enter Upgrade Mode](https://docs.khadas.com/vim1/HowtoBootIntoUpgradeMode.html)

**Tips:**
* **eMMC image** should be burned directly to the eMMC using a USB-C data cable, from a Ubuntu or Windows Host. It must not be burned into an SD-Card. For Example: Android and Ubuntu distributions containing the `EMMC` mark.
* **SD/USB image** should be copied into an SD-Card, before that card is then used to reformat the eMMC storage with a new OS. For Example: Armbian, Ubuntu distributions containing the `SD_USB` mark, as well as LibreELEC and CoreELEC.
* In order to bootup from **SD/USB images**, you need Android (V180209 or newer) or Ubuntu (V180531 or newer) running on your eMMC with Multi-Boot activated.

# Upgrading eMMC Operating System Using USB-Cable
You'll need these items if you want to use your laptop or desktop PC to upgrade your VIM1 SBC's operating system stored in its eMMC storage. For example, changing the bootup operating system from Android to Ubuntu, or installing a more exotic 3rd-party OS.

1. USB-A to USB-C Data Cable (Legacy Computers)
2. USB-C to USB-C Data Cable (Modern Computers)
3. Laptop / Desktop PC

**Learn More:**
* [Upgrade Using USB-Cable](https://docs.khadas.com/vim1/UpgradeViaUSBCable.html)
* [Enter Upgrade Mode](https://docs.khadas.com/vim1/HowtoBootIntoUpgradeMode.html)
* [Android OS](https://docs.khadas.com/vim1/FirmwareAndroid.html)
* [Ubuntu OS](https://docs.khadas.com/vim1/FirmwareUbuntu.html)
* [LibreELEC](https://docs.khadas.com/vim1/FirmwareLibreelec.html)
* [Dual OS](https://docs.khadas.com/vim1/FirmwareDualos.html)
* [U-Boot](https://docs.khadas.com/vim1/FirmwareUboot.html)
* [Third Party OSes](https://docs.khadas.com/vim1/FirmwareThirdparty.html)

# Watching Movies, Expanding Internal eMMC Storage
These items are useful if you wish to use your VIM1 SBC as a media center, for storing/downloading large movie files. A microSDXC UHS-I card is expensive, but its also fast enough for 4K video playback. In addition, you can connect external USB-2.0/3.0 SSDs or HDDs for storage that can encompass your entire media library.

1. 64GB or larger, USB-2.0/3.0 HDD / SSD
2. 64GB or larger, *microSDXC UHS-I* SD-Card

**Learn More:**
* [Amazon - Samsung T5 Portable SSD](https://www.amazon.com/Samsung-T5-Portable-SSD-MU-PA1T0B/dp/B073H552FJ/ref=sr_1_1_sspa?ie=UTF8&qid=1543995277&sr=8-1-spons&keywords=external+usb+ssd&psc=1)
* [Amazon - microSDXC UHS-I SD-Card](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Daps&field-keywords=microSDXC+UHS-I&rh=i%3Aaps%2Ck%3AmicroSDXC+UHS-I)

# Software Development / Advanced Crash Recovery
Extreme cases of crash-recovery will require you to use the MRegister to reset your VIM1 SBC. A USB Serial Debug Tool is also useful for developers debugging complex software issues.

1. Conductive Metal Tweezers (For resetting a dead SBC via MRegister)
2. USB Serial Debug Tool (For diagnosing software/hardware issues)

**Learn More:**
* [MRegister Upgrade Mode](https://docs.khadas.com/vim2/HowtoBootIntoUpgradeMode.html)
* [Amazon - Metal Tweezers](https://www.amazon.com/s/ref=nb_sb_noss_2?url=search-alias%3Daps&field-keywords=metal+tweezers)
* [Amazon - USB Serial Debug Tool](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Daps&field-keywords=usb+serial+debug+tool&rh=i%3Aaps%2Ck%3Ausb+serial+debug+tool)

# VIM1 Website
For more information, please see our website, read more documentation, or visit our forum.
* [Khadas VIM1 Homepage](https://www.khadas.com/vim)
* [Khadas VIM1 Forum](https://forum.khadas.com/c/khadas-vim)

# VIM1 Review Video
{% youtube dLAX8nwcTvo %}
