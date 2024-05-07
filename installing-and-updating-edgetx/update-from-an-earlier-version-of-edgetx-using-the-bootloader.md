# Update from an earlier version of EdgeTX using the Bootloader

### Back-up SD Card Contents

**Before making any updates to your radio, we ALWAYS recommend that you back up your current SD Card contents using the following steps.**&#x20;

With your radio powered on, plug your radio into your computer via USB. When prompted by your radio for the USB mode, select **USB Storage**.&#x20;

With your computer, copy the entire contents of your SD card to a safe place on your computer. You can use these files again if you need to roll back the update.

### SD Card Preparation

Download and extract the EdgeTX SD card content for your radio type to your computer. The SD card contents can be found here: [https://github.com/EdgeTX/edgetx-sdcard/releases](https://github.com/EdgeTX/edgetx-sdcard/releases)

The list below shows which .zip file to use for different radio types:

* c480x272zip (480x272 Horizontal Color Screen) - TX16s, T16, Horus x10s,Horus x12s, most color screen radios...
* c480x320 (480x320 Horizontal Color Screen)
* c320x480zip (320x480 Verticle Color Screen)- FlySky Nirvana NV14, EL18
* bw128x64.zip (128x64 BW Screens) -All monochrome screen radios _except_ X9D series.
* bw212x64zip (212x64 BW Screens) - X9D, X9D Plus, X9D Plus 2019

Copy the extracted files to your radio's SD card. If asked, overwrite the existing files. This will only update the SD card files that are part of the default EdgeTX installation. It will not modify or delete any additional files you have added (LUA scripts, sound files, images, custom themes, model files, radio setup file, etc) that are already existing on the SD card.&#x20;

Download the desired sound pack ([https://github.com/EdgeTX/edgetx-sdcard-sounds/releases](https://github.com/EdgeTX/edgetx-sdcard-sounds/releases)), unzip and copy to the "Sounds" folder on your SD card.  If asked, overwrite the existing files.&#x20;

### Flashing the EdgeTX Bootloader and Firmware

Download the current EdgeTX firmware. You can download the latest release .zip file (edgetx-firmware-vX.X.X.zip) directly from Github - [https://github.com/EdgeTX/edgetx/releases/latest](https://github.com/EdgeTX/edgetx/releases/latest)

Unzip the file and save the correct .bin file (same name as your radio type) to the "**Firmware**" folder on the SD card for your radio.

Turn on your radio and navigate to the SD card screen. Open the "Firmware" folder and select the EdgeTX firmware file that you just copied to your SD card. Once the file is selected, select the option to "**Flash bootloader"**. The bootloader will be updated.

{% hint style="info" %}
**Note:** When updating the bootloader using EdgeTX, you won't see the "Flash bootloader" option if the bootloader file is meant for a different radio target.
{% endhint %}

Exit back to the main screen and then shut off your radio.

Boot your radio in bootloader mode by holding trim switches T4 and T1 to center while pushing the power button on.

{% hint style="info" %}
On the Jumper T-Pro, you have to plug in the radio while pressing the Boot0 button to enter DFU mode.
{% endhint %}

You will see the EdgeTX bootloader. Select the option "**Write Firmware**". Select the EdgeTX firmware file that you saved to your SD card. Long-press to flash it.

{% hint style="info" %}
**Note:** When you're flashing the firmware with the bootloader and the bootloader detects a different target from what it's currently running, it will display an error message stating that the firmware is invalid.
{% endhint %}

After the flashing is complete, select "**Exit**". The radio will restart and you should be greeted with "**Welcome EdgeTX**".

### Congratulations, you have now successfully updated EdgeTX!



