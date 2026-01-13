# Updating STM32H7

Due to a different architecture design, radio transmitters using STM32H7 MCUs update differently to what you may have become familiar with on older STM32F2 and STMF4 based designs.&#x20;

There are basically two methods of flashing them at present:

* Bootloader and UF2 file copy
* EdgeTX Companion (v2.12 or later)



## UF2 File Copy

This method of flashing is relatively simple:

1. Put the radio into bootloader mode (on most radios, this is done by powering up the radio, with the horizontal trims held inwards - but you can [check here for your specific radio](../edgetx-how-to/access-dfu-and-bootloader-mode.md).&#x20;
2. Plug the radio USB in (don't use a USB-C to USB-C cable, always use a USB-A to USB-C cable - most likely one came with your radio, and use a converter/hub if needed).&#x20;
3. Download / copy the UF2 firmware for your radio to the `EDGETX_UF2` drive that should now be available. The screen of the radio should change to show the update progress.&#x20;
4. Once the update has completed, you can safely eject / disconnect your radio. Both the radio firmware and bootloader will now be up to date!



## EdgeTX Companion

TODO



