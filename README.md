# iBasso DX150 firmware add-on by Lurker

## Introduction
Android 8.1 for DX150 protects main partitions with [Verity](https://source.android.com/security/verifiedboot), which makes it tricky for end user to flash custom firmware. [Magisk](https://magiskmanager.com/) allows developers to alter system systemless-ly, i.e. without any direct modification of the protected parts of the firmware image. That's why my modifications for 8.1 are distributed as add-ons: you must have installed and running the original firmware, then you apply (flash over) an add-on. It makes the download smaller and update process faster!

To check the current add-on version in Android mode, go to _Settings_, _About DX150_, _Build number_ at the bottom.

**WARNING:** Add-ons are *not* compatible with encrypted devices!

## How to apply or update the add-on
There are two packages to choose from: either Windows-only (using included AndroidTool), or any platform (using [DX150-bootable SD-card](https://github.com/Lurker00/DX150-Firmware-Add-on/tree/master/FirmwareUpdater)). The ZIP archive with add-on contains `readme.txt` file with full instruction. Please read and follow it.

**Note:** Updating an add-on removes additional [Magisk](https://magiskmanager.com/) modules. You'll have to re-install them after the update.

## How to return back to the official firmware
After iBasso released OTA-like update (1.03.036 or later), it is enough to re-apply any official firmare update, then do a factory reset.

## How to update the official firmware
You need to download the update from [iBasso site](http://ibasso.com/down.php), put it to SD-card or Internal storage, and start manual upgrade. Then you may install an add-on compatible with the new firmware version, if any.

## Changes made
It's up to the end user to decide whether these changes affect sound or not. I believe some of them make sound better, and none of them make sound worse.

### Android
* Google Play Store added.
* Reduced power consumption during music playback and in suspend mode.
* Overall performance increased.
* During music playback, the device is managed to prevent idle state tasks.
* Performance tweak for popular music players (Neutron, UAPP, Tidal, Spotify). Such a tweak is used on Rockchip SoC based devices for benchmark apps, iBasso sets it for its Mango Player.
* The process of [device registration](https://www.google.com/android/uncertified/) is much simplified (required to make Google Play Services work on uncertified device).
* [Magisk](https://magiskmanager.com/) can be used to install additional modules, and to provide root access.
* [USB Audio application](https://github.com/Lurker00/DX200-USB-Audio-Release/blob/master/README.md), which is also useful for its [System settings](https://github.com/Lurker00/DX200-USB-Audio-Release/blob/master/README.md#system-settings).
* Custom build of [HibyMusic](https://play.google.com/store/apps/details?id=com.hiby.music), which plays bit perfect PCM up to 32/384kHz with no additional efforts, and is fully compatible with [USB Audio application](https://github.com/Lurker00/DX200-USB-Audio-Release/blob/master/README.md) for bit perfect DSD and SACD ISO playback.
* Removed APKPure, CoolAPK.
* Better thermal control.

### Mango OS
* Added Mango OS mode from DX200.

**Note 1**: Mango OS player was taken from DX200, and, as such, is not 100% compatible. The known restrictions and problems are:
* Only first 5 Digital Filter options actually work, and their names don't correcpond to DX150 actual filter names.

**Note 2**: MagiskManager icon is, actually, a stub injected by Magisk core. It is intended by the developer to help installing full MagiskManager, but I disable it to stop annoying. Should you need [MagiskManager, please install it manually](https://github.com/topjohnwu/Magisk/releases).

## History of public releases
* [**1.22**](https://github.com/Lurker00/DX150-Firmware-Add-on/releases/tag/v1.22) - release for official firmware 1.05.075.
* [**1.18**](https://github.com/Lurker00/DX150-Firmware-Add-on/releases/tag/v1.18) - release for official firmware 1.04.047.
* [**1.17**](https://github.com/Lurker00/DX150-Firmware-Add-on/releases/tag/v1.17) - release for official firmware 1.03.036.
* [**1.15**](https://github.com/Lurker00/DX150-Firmware-Add-on/releases/tag/v1.15) - release for official firmware 1.01.017.
