# Firmware update from SD-card
**WARNING: The only Android 6.1 based firmware image compatible with this SD-card is [2.11.293-L0 full flash firmware image](https://github.com/Lurker00/DX150-firmware/releases/download/v2.11.293/DX150FirmwareV2.11.293-L0-fullflash.zip). Do not use this SD-card with any Android 6.1 based firmware image!**

**Note:** Boot from this SD-card when DX150 has Android 6.1 based firmware may not show initial logo, and the screen can be wrapped from right to left, and you may see an error message at the end. These problems are cosmetic. You may repeat flashing Android 8.1 firmware, without those glitches, if you are unsure.

RockChip SoC based devices support firmware updates by booting from a specially prepared SD-card. The official way requires a Windows-based application from RockChip ("Create Upgrade Disk Tool", aka "SD Firmware Tool"), and a suitable device boot loader file. Using them, I've prepared such an SD-card for you.

[`DX150FirmwareUpdater.zip`](https://github.com/Lurker00/DX150-Firmware-Add-on/releases/download/DX150FirmwareUpdater/DX150FirmwareUpdater.zip) archive contains ready to use SD-card image file with 4GB partition, to update firmware on iBasso DX150.

## Prepare bootable SD-card
You may use any SD-card with capacity of 4GB or more.

**WARNING:** writing the SD-card image file erases all the data on the card! To restore the SD-card for normal use, please use [SD Memory Card Formatter](https://www.sdcard.org/downloads/formatter_4/), available for MacOS and Windows.

You need to unzip the downloaded archive ([`DX150FirmwareUpdater.zip`](https://github.com/Lurker00/DX150-Firmware-Add-on/releases/download/DX150FirmwareUpdater/DX150FirmwareUpdater.zip)) and write the `DX150FirmwareUpdater.img` file directly to SD-card. Under Windows, [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/) can be used. Under Linux and MacOS, [Etcher](https://en.wikipedia.org/wiki/Etcher_(software)) GUI application performs the task (see [below](#an-instruction-for-macos-users) for example). Experienced users may use [`dd` command](https://en.wikipedia.org/wiki/Dd_(Unix)) from console, though great caution is required!

If all went right way, you should have SD-card labeled as `DX150UPDATE`, with the following content:
* `sd_boot_config.config`
* `sdupdate.img`
* `rksdfw.tag`

`sdupdate.img` is empty (0 bytes), and it is the placeholder for the real firmware update image file.

## Update firmware

**WARNING:** Firmware update from bootable SD card is performed only when DX150 is not connected to a power supply or USB port. Charge it before starting firmware update!

You need firmware update image file. For Android Oreo, iBasso provides `update.img` in its download. My firmware releases, to be used with RockChip FactoryTool (*not* files to be used with rkflashtool!), contain compatible `.img` file as well.

1. Rename required `.img` file to `sdupdate.img`.
2. Copy resulting `sdupdate.img` to the prepared bootable SD-card, confirming to overwrite existing file.
3. Safely remove (unmount) SD-card from the computer.
4. Disconnect DX150 from a charger or USB port (if it is connected).
5. If your DX150 boots to Mango, switch it to boot to Android.
6. Turn DX150 off.
7. Insert SD-card into DX150.
8. Turn DX150 on.

In a few seconds it should start updating the firmware. At the end, it will prompt you to remove the SD-card from the slot, and will continue update, then erase storages and boot the device.

## Useful notes

You may keep several firmware images on the bootable SD-card under different file names. Only the one named `sdupdate.img` is used for the firmware update.

You may use this SD-card to revert back from Android 8.1 to 2.11.293-L0 using [full flash firmware image](https://github.com/Lurker00/DX150-firmware/releases/download/v2.11.293/DX150FirmwareV2.11.293-L0-fullflash.zip). **Do not use any other Android 6.1-based firmware images with this SD-card!**

## An instruction for MacOS users

[AnakChan](https://www.head-fi.org/members/anakchan.194497/) has [published](https://www.head-fi.org/threads/791531/page-1266#post-14613722) the following instruction, based on his successful experience, on how to update to Android Oreo:

**Pre-requisites**

a. Download & install [Etcher](https://en.wikipedia.org/wiki/Etcher_(software))<br />
b. Download & unzip [DX150FirmwareUpdater.zip](https://github.com/Lurker00/DX150-Firmware-Add-on/releases/download/DX150FirmwareUpdater/DX150FirmwareUpdater.zip)<br />
c. Download & unzip [iBasso’s Oreo](http://ibasso.com/down.php)<br />

**Install Steps**
1. Run the balenaEtcher app
1. Select Image `DX150FirmwareUpdater.img`
1. Select Drive (Pick your microSD card) & Continue
1. Select Flash!
1. Enter your MacOS privileged password
1. Exit balenaEtcher app
1. Physically eject microSD and reinsert
1. MicroSD should mount as `DX150UPDATE`
1. Doubleclick into `DX150UPDATE`
1. Open another Finder window
1. Navigate to the unzipped iBasso Oreo (c) above
1. Go to `DX150-android8.1-Beta/DX150-8.1FW-Beta`
1. Copy `update.img` to the `DX150UPDATE` finder window
1. Right-click the `sdupdate.img` (Zero bytes) and Move to Bin
1. Right-click `update.img` and Rename to `sdupdate.img`
1. Eject the `DX150UPDATE` MicroSD from Finder
1. Switch off the DX150
1. Put the `DX150UPDATE` MicroSD into the DX150
1. Power on the DX150
1. The DX150 should be “Installing system update”
1. It takes just over 3 mins. The first 50% fo the bar is fast, but the remaining 50% of the bar is slower. It’s not hanging
1. When it finishes, it’ll say :-<br />
    `Supported API: 3`<br />
    `Doing Actions succeeded.please remove the sdcard……`<br />
1. Remove the MicroSD and it’ll auto boot
1. You now have iBasso's Oreo
