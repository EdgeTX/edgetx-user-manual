# Having trouble updating?

If you're here reading this, you probably got stuck with something either while trying to update or after updating. So checkout the list of issues and possible resolution steps below, to see if something matches the problem you are having. If there isn't, either join us on [Discord](https://discord.gg/wF9wUKnZ6H) (there is usually someone around who can help out), drop by our  [GitHub Discussions](https://github.com/EdgeTX/edgetx/discussions) forum, or the [RCGroups forum thread](https://www.rcgroups.com/forums/showthread.php?3916381-Official-EdgeTX-Discussion-Thread) if that is more your thing.&#x20;

#### **I'm trying to flash using EdgeTX Buddy, but my handset isn't detected**

1. Make sure when you plug the radio into the computer, that your handset is **turned off**. If you are getting a prompt about what mode to put the USB into, you will not be able to update. DFU mode, which used to flash the firmware, only operates when the handset is plugged in when in the **OFF** state.&#x20;
2. Does your radio have a boot / DFU button? Check the [access-dfu-and-bootloader-mode.md](../edgetx-how-to/access-dfu-and-bootloader-mode.md "mention") page to see if your handset is one of those listed where you need to hold a button down when plugging the USB in.&#x20;
3. You could be facing driver issues. If you are on Windows, you could firstly try the [ImpulseRC Driver Fixer](https://impulserc.com/pages/downloads) tool. Alternately, you could go to the STMicroelectronics website, and download their free [STM32CubeProgrammer tool](https://www.st.com/en/development-tools/stm32cubeprog.html#get-software), which includes the necessary drivers, and works with all the major operating systems. It does however require creating a (free) account at the the STMicroelectronics website, but it is the official tool for programming the micro-controller being used in all supported radio handsets.&#x20;
4. Check with another USB cable... not all cables are created equally, and some cables are "charge only" cables.&#x20;

#### I updated EdgeTX, and now my radio doesn't turn on, or acts strangely

1. Firstly, double check that you selected the correct name / target for your handset. Some incorrect selections will still boot, but buttons and controls will work incorrectly, or the screen will be upside down. Other combinations simply won't work at all, or make the radio seemingly go crazy, and you need to unplug the battery to get it to turn off. If you flashed the wrong target, simply go to EdgeTX Buddy, select the correct radio model, and flash the firmware.&#x20;
2. Some handsets can have the wrong option bits set on the microcontroller, and as a result, will refuse to boot with EdgeTX 2.10 or later. The exact cause of this is unknown, but the fix is _relatively_ simple. See the (collapsed) instructions below for more information.

<details>

<summary>Resetting Option Bits</summary>

1. Once you have installed the STM32CubeProgrammer tool (which requires creation of a free account on the STMicroelectronics website), plug your radio in while switched off, in order to enter DFU mode. Double check the [access-dfu-and-bootloader-mode.md](../edgetx-how-to/access-dfu-and-bootloader-mode.md "mention") page if you are unsure if your handset has a boot / DFU mode button that needs to be held down whilst plugging it in.
2. Start the STM32CubeProgrammer tool if you don't already have it running. You should have a screen that looks somewhat like this (click the image for a larger view):\
   ![STM32CubeProgrammer main screen](../.gitbook/assets/2024-08-28\_11-46.png)\
   \
   Ensure the device type (1) says USB, and then press the Connect button (2). If the port field is empty, try pressing the refresh button (3).
3. Go to the "Option bytes" page (1). Then select User Configuration (2). Check the status of  "BFB2" (3). If it is ticked, remove the tick so that it is as shown, and click the Apply button (4). You can then click the "Disconnect" button and disconnect your handset.\
   ![STM32CubeProgrammer: Option bytes](../.gitbook/assets/2024-08-28\_11-44.png)
4. That should be it... your handset should boot up now if this was the issue.&#x20;

</details>

3. If you are really stuck, you can follow this guide on [how to unbrick your radio](https://github.com/EdgeTX/edgetx/wiki/Unbrick-your-radio).&#x20;

