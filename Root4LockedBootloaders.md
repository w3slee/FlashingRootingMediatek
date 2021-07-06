This script uses mtk-su to launch Magisk on compatible devices, including locked down ones! It runs entirely from the data partition--no need to modify the firmware. Root is available for any app that wants it.

**NEW FEATURES**

- MagiskHide & SafetyNet pass now work under Android 9
- Modules pass minimum version check
- Faster and more efficient loading
- Logging works properly

**General warnings**
Read this whole post before starting. Only use this on devices on which you can recover the firmware outside of Android such as recovery mode, download tool, etc. While precautions have been taken to block flashing of the boot partition, not everything has or can be accounted for. You must anticipate when a superuser action might alter your boot or system partitions and avoid doing that command. Do not try to update Magisk through Magisk Manager's Direct Install. Even though testing has shown that that feature will fail, it might succeed in some cases.
