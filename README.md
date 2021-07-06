# FlashingRootingMediatek
Compilation of useful manuals to help during the tedious process of flashing and rooting Mediatek based devices with already available exploits

# Compatible chipsets

These notes are based for devices with Mediatek :

- MT67xx,
- MT816x,
- MT817x,
- MT6580 chipsets

There is no support for 32-bit chips eg MT65xx or MT8127
---

**WARNING**
If you have a device with Android 6 or higher, it likely has **dm-verity** enabled. On such a device one does not simply remount the system partition as read/write.
The remount command will probably fail. But if you succeed in forcing it somehow it will trigger dm-verity, which will result in a very bad day. Your device will become inoperable until you restore the stock system partition.

**DISCLAIMER**
Anything you do that is described in this thread is at your own risk. No one else is responsible for any data loss, corruption or damage of your device, including that which results from bugs in this software. There is a nonzero chance of any of these events happening as a result of using the tools or methods here.

**PREREQUISITES**
1. A phone or tablet based on Mediatek MT67xx, MT816x, MT817x or MT6580 chipsets

Either:

2. A PC with ADB installed to interact with your device or terminal emulator app

Familiarity with ADB (if using PC) and basic Linux shell commands

**INSTRUCTIONS FOR ADB**

Make sure you meet all the requirements listed above, especially the first and last ones.

1. Unzip mtk-su zip from tools folder
2. Inside will be 2 directories: 'arm' & 'arm64' with an 'mtk-su' binary in each. Pick one for your device. Differences between the flavors:

- arm64: 64-bit kernel and userspace
- arm: 32-bit userspace on a 64-bit or 32-bit kernel (will also work in 64-bit userspace)

3.  Connect your device to ADB and push mtk-su to your /data/local/tmp folder
4.  `adb push path/to/mtk-su /data/local/tmp/`
5.  Open an adb shell
6.  `adb shell`
7.  Change to your tmp directory
8.  `cd /data/local/tmp`
9.  Add executable permissions to the binary
10. `chmod 755 mtk-su`

- At this point keep your device screen on and don't let it go to sleep.

Run the command `./mtk-su`

It should only take a second or two. If the program gets stuck for more than a few seconds and your device is awake, press Ctrl+C to close it.

The -v option turns on verbose printing, which is necessary to debug any problems

**NOT SUPPORTED**
If your device has Android 10+ or a security patch level at 03-2020 or higher, you will get an error `Firmware support not implemented`.
