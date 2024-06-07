---
description: Current for all merged PRs as of 31/05/2024 (v2.10.1)
---

# Summary of changes since v2.9

Below is a summary of changes that affect the user interface and/or how EdgeTX functions. It does not cover all bug fixes. For a complete list of changes (including bug fixes), please read the release notes.

### **Color Screen Radios**

* New Hardware Support
  * Flysky PL18
  * Flysky PL18 EV
  * Jumper T15
* General Changes
  * The mixer now runs at 1000Hz when in USB Joystick mode (needed for F.Sim competitors), also displays mixer run time in statistic/debug screen.
  * Minor UI improvements on many pages for better look and consistency&#x20;
  * Bootloader background removed to make the text more legible
  * Default splash screen updated with new EdgeTX Logo and EdgeTX version information.
  * **Source** selection menu has been optimized for easier touch usability and sorting.
  * **Source** selection menu will now display both global variable number and name.
  * Added charging LED animation for PL18 and PL18EV.
* [User interface page](color-radios/user-interface/)
  * The **System \[SYS]** and **Models \[MDL] buttons** have different [functionalities](color-radios/user-interface/#additional-system-and-model-button-functionalities) depending on the screen they are used on.
  * [Trim hat switches](color-radios/user-interface/trim-navigation.md) on NV14 and EL18 can now be used to navigate the menus.
  * Added [hardware shortcut keys to the virtual text and number keyboards](color-radios/user-interface/virtual-keyboards.md).
* [Manage Models page](color-radios/select-model.md)
  * Added 3 additional layouts for the model list.
  * Updated the model image frames size & shape. Also now displays model name on top of the image, instead of clipping the image.
  * Replaced the **New Label** button and **New Model** button with just a **New** button with options for **Model** or **Label**.
  * Replaced confusing model sorting icons with a simple text drop-down menu.
  *   Added a single select option for model labels plus label AND/OR filtering logic (configurable in the [Radio Setup](color-radios/radio-settings/radio-setup/additional-radio-settings.md) screen).


* [Model Setup](color-radios/model-settings/model-setup/)
  * Timers that are enabled will show as highlighted on the **Model Setup** screen.
  * &#x20;MIN can be used as source. When selected it will always returns -100.
  * Added **Interactive** **Checklist** option to **Pre-start checks** section. Allows users to add interactive checkboxes to displayed checklists.
* [Flight Modes](color-radios/model-settings/flight-modes.md)
  * Unused trim switches can now be configured to function as a 3 position momentary switch.
* [Mixes](color-radios/model-settings/inputs-mixes-and-outputs/mixes.md)
  * Added configurable precision for **slow up/dn** to be set to either 10ms or 100ms.
* [Global Variables](color-radios/model-settings/global-variables.md)
  * Added the **Popup** option, which when enabled displays a popup message when the value of a GV changes with the new GV value.
* [Special Functions](color-radios/model-settings/special-functions.md)
  * All special functions now have the **Enable** checkbox.
  * Special functions can be Enabled / Disabled without opening the Edit menu.
  * Added virtual trainer switch (**Tnr**) that can be selected as switch to activate a special function. Switch is ON when the trainer link is active.
  * **Backlight** special function brightness is limited to the On / Off values configured in the **Radio Setup -> Backlight Screen.**
* [Telemetry](color-radios/model-settings/telemetry/)
  * EdgeTX will play "Telemetry connected" when telemetry connects for the first time of the flight.
* [SD Card](color-radios/radio-settings/sd-card.md)
  * Users can configure a custom shutdown image by adding a custom `shutdown.png` to the **IMAGES** folder.
  * **View text** option now available for .lua files
* [Radio Setup](color-radios/radio-settings/radio-setup/)
  * In **GPS settings**, updated the **Time Zone** option to allow configuration in 15 minute intervals.
  * Added the **Splash Screen** option which sets the duration that the splash screen will be displayed.
  * Added the **Startup Sound** option which toggles whether to enable/disable startup sound.
  * Added **PPM Units** option- Previously this was a build option.
  * In the **Enabled Features** section, added the current configuration setting for the active model to the right of the toggle switch.
* [Hardware ](color-radios/radio-settings/hardware.md)
  * Analog inputs, such as pots and sliders can now be configured as a **Switch**, **Axis X** or **Axis Y**. Additionally, they can also be configured to be _**inverted**_.
  * EdgeTX will now detect at runtime if a serial port is available to allow for SBUS trainer on the external module bay. If so, the configuration option will be available.
* [Screen Settings](color-radios/screen-settings/)
  * In the top bar, the radio info, date/time and internal GPS are now configurable widgets, allowing 6 widget slots to be configured.
  * Selecting an empty widget will no longer display the 'Select widget' option and instead go right to the widget selection menu.
* [Widgets](color-radios/screen-settings/widgets.md)
  * Added the alignment option to the **Text** widget to align widget text **Left**, **Center**, or **Right**.
* Alerts
  * Warning will be displayed if you try to shut down the radio while the trainer connection is still active.

### Monochrome Screen Radios

*   New Hardware Support

    * Jumper T-Pro V2
    * Jumper T-14
    * Jumper T-20
    * Flysky Gimbal support for Jumper T-20
    * Flysky Gimbal support for Frsky X9D+2019
    * RadioMaster Pocket
    * RadioMaster MT12


* General Changes
  * The mixer now runs at 1000Hz when in USB Joystick mode (needed for F.Sim competitors), also displays mixer run time in statistic/debug screen.
  * Splash Screen updated with new EdgeTX Logo
  * Radios with unused flexible serial port will now automatically be defined as **AUX Serial** (MT12).
* [Main View](bw-radios/main-view/)
  * Added new view for surface radios with throttle and steering instead of sticks.
* [Model Settings](bw-radios/model-select/)
  * Added **C-Interact** option to Pre-start checks section. Allows users to add Interactive Checkboxes to displayed checklists.
  * On surface radios (EX: MT-12), the throttle trim no longer has an effect on the reverse throttle range.
* [Flight Modes](bw-radios/model-select/flight-modes.md)
  * Unused trim switches can now be configured to function as a 3 position momentary switch.
* [Mixes](bw-radios/model-select/inputs-mixes-and-outputs/mixes.md)
  * Added configurable precision for **slow up/dn** to be set to either 10ms or 100ms.
* [Telemetry](bw-radios/model-select/telemetry/)
  * EdgeTX will play "Telemetry connected" when telemetry connects for the first time of the flight.
  * The number of configured sensors will be displayed in **parentheses** when the sensor list is collapsed.
* [Special Functions](bw-radios/model-select/special-functions.md)
  * All special functions now have the **enable** checkbox.
  * OLED screen brightness can be controlled with **Backlight** special function.
  * Added virtual trainer switch (**Tnr**) that can be selected as switch to activate a special function. Switch is ON when the trainer link is active.
  * Added RGB Led special function to enable and change LED behavior.
* [Radio Setup](bw-radios/radio-settings/radio-setup.md)
  * In **GPS settings**, updated the **Time Zone** option to allow configuration in 15 minute intervals.
  * Added the **Startup Sound** option which toggles whether to enable/disable startup sound.
  * Added **PPM Units** option- Previously this was a build option.
  * In the **Enabled Features** section, added the current configuration setting for the active model to the right of the checkbox.
  * Added the **Rotary Encoder Mode** - **V-N E-I** = Vertical Normal, Edit Inverted (inverted when editing text)
* [Hardware](bw-radios/radio-settings/hardware.md)
  * Analog inputs, such as pots and sliders can now be configured as a **Switch**, **Axis X** or **Axis Y**. Additionally, they can also be configured to be inverted.
  * EdgeTX will now detect at runtime if a serial port is available to allow for SBUS trainer on the external module bay. If so, the configuration option will be available.
* Alerts
  * Warning will be displayed if you try to shut down the radio while the trainer connection is still active.
