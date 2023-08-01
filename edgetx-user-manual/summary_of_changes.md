---
description: Current for all merged PRs as of 03/07/2023 (v2.9 RC1)
---

# Summary of changes since v2.8

Below is a summary of changes that affect the user interface and/or how EdgeTX functions. It does not cover all bug fixes. For a complete list of changes (including bug fixes), please read the release notes.

### **Color Screen Radios**

* General Changes
  * LVGL conversion of all pages is now complete.
  * Adjusted padding and spacing on many pages and buttons for a better look.
  * No more on-radio model conversions from .otx format. Users migrating from OpenTX will need to import their models to EdgeTX Companion. See [EdgeTX Migration guide](installing-and-updating-edgetx/update-from-opentx-to-edgetx.md) for instructions how to migrate from OpenTX to EdgeTX.
  * Only SD card is mapped to device in USB Storage Mode.&#x20;
* [User interface page](user-manual-for-color-screen-radios/user-interface.md)
  * Long press the **\[SYS]** button to go to the Radio Setup page.
* [Model Select page](user-manual-for-color-screen-radios/select-model.md)
  * Now named **Manage Models** instead of **Model Select.**
  * **Edit Labels** option is now called **Label Models**
  * Added **model quick select**. When enabled in [radio settings](user-manual-for-color-screen-radios/radio-settings/), this feature allows you to select a model as active model in the manage model screen by _**double tapping**_ on it.
* [External RF](user-manual-for-color-screen-radios/model-settings/model-setup/internal-external-rf.md)
  * Added mode **R9M ACCESS** to enable R9M Access Mod. Compilation option is no longer needed.
  * PPM Frames automatically adjust based on number of configured channels
* [Trainer](user-manual-for-color-screen-radios/model-settings/model-setup/trainer.md) (Model Setup)
  * PPM Frames automatically adjust based on number of configured channels
* [Timers](user-manual-for-color-screen-radios/model-settings/model-setup/timer-1-2-3.md)
  * Added **Beeps & Haptic** and **Voice & Haptic** as options for countdown option
* [Enabled Features](user-manual-for-color-screen-radios/model-settings/model-setup/enabled-features.md)
  * New section in Model Setup - allows you to configure which tabs are visible in the selected model's radio setup and model settings area of EdgeTX.
* [USB Joystick](user-manual-for-color-screen-radios/model-settings/model-setup/usb-joystick.md)
  * New section in Model Setup - allows users to select between Classic and Advaced Mode.
  * Adds advanced joystick configuration options in **Advanced Mode**.
* [Flight Modes](user-manual-for-color-screen-radios/model-settings/flight-modes.md)
  * New screen layout to allow better overview of configured flight modes.
* [Inputs ](user-manual-for-color-screen-radios/model-settings/inputs-mixes-and-outputs/inputs.md)
  * New screen layout, only shows configured inputs.
  * New **+** button to add additional inputs.
* [Curves](user-manual-for-color-screen-radios/model-settings/curves.md)
  * Updated screen layout
  * Moving the control sticks will update the stick position on the curve in real time.
* [Logical switches](user-manual-for-color-screen-radios/model-settings/logical-switches.md)
  * Updated screen layout
* [Special Functions](user-manual-for-color-screen-radios/model-settings/special-functions.md)
  * New screen layout, only shows configured special functions
  * New + button to add special functions
  * _**Lua Script**_ function adds **repeat** option
* [Telemetry](user-manual-for-color-screen-radios/model-settings/telemetry/)
  * Updated screen layout
  * Added option to Show Instance ID On/Off
* [SD Card](user-manual-for-color-screen-radios/radio-settings/sd-card.md)
  * Added OTA flashing for FrSky X10s & X12s receivers for transmitters with internal ISRM/Access modules.
* [Radio Setup](user-manual-for-color-screen-radios/radio-settings/radio-setup/)
  * Added **Enabled Features** settings to configure the _**Global**_ _**settings**_ for which tabs are visible in the Radio Setup and Model Settings area of EdgeTX.
  * Added **model quick select** configuration option. When enabled, this feature allows you to select a model as active model in the manage model screen by double tapping on it.
  * Image and Sound folders limited to 799 files each. If the folders contain more than 799 files, the file selection dropdown in model settings will not work properly. This is a limitation of LVGL.
* [Trainer](user-manual-for-color-screen-radios/model-settings/model-setup/trainer.md) (Radio Settings)
  * Changed mode options from **+=** and **:=** to **Replaced** and **Add** for easier configuration.
* [Hardware ](user-manual-for-color-screen-radios/radio-settings/hardware.md)
  * Updated debug analog screen and touch screen response.
  * Added **External module** option to Aux1 and Aux2 to enable configuring R9M Access Mod in Model Settings.
  * Added **Mute if no sound** option - puts the transmitter in mute mode until a sound needs to be played. This prevents interference noise from high-powered TX modules from coming out of the transmitter speakers.&#x20;
* [Screen Settings](user-manual-for-color-screen-radios/screen-settings/)
  * Added 4x2B screen layout.
  * Increased the max views from 5 to 10.
* [Widgets](user-manual-for-color-screen-radios/screen-settings/widgets.md)
  * **Value** widget added align left, center, right option for label and value.
  * **Text** widget added align left, center, right option for label and value.
  * Added **Value2** widget to display telemetry data better.
  * All widgets are now sorted alphabetical by name.&#x20;
  * Updated color picker for widgets, can select system theme colors. Colors are not applied until saved.
* Alerts
  * Alerts now display a "press any key" prompt.
  * Long press of the touchscreen can close an alert.
  * All buttons can be used to close an alert. Buttons will not open other UI pages over the alert.
* [Channel Monitor](user-manual-for-color-screen-radios/channel-monitor.md)
  * Logical switch page updated
* [Statistics](user-manual-for-color-screen-radios/statistics.md)
  * Small changes to labels on debug page.
* Languages
  * Added Hebrew language support.
* New Hardware Support
  * Flysky FRM303 Support (External RX Module)
  * Segger RTT debug support

### Monochrome Screen Radios

* General Changes
  * No more on-radio model conversions from .otx format. Users migrating from OpenTX will need to import their models to EdgeTX Companion. See [EdgeTX Migration guide](installing-and-updating-edgetx/update-from-opentx-to-edgetx.md) for instructions how to migrate from OpenTX to EdgeTX.
  * Only SD card is mapped to device in USB Storage Mode.
* [Main View](../b-and-w-radios/main-view/)
  * Added clock to main view pages.
* [Model Settings](../b-and-w-radios/model-select/)
  * Timer configuration options are hidden when timer is set to **Off**.
  * Throttle configuration options are hidden in collapsible menu.
  * Preflight Checklist configuration options are hidden in collapsible menu.
  * Added **Enabled Features** option - allows you to configure which pages are visible in the selected model's radio setup and model settings area of EdgeTX; configuration options are hidden in collapsible menu.
  * Adds **USB Joystick** mode- allows users to select between Classic and Advaced Mode; adds advanced joystick configuration options when in **Advanced Mode**.
  * Added Bluetooth trainer mode with FrSky bluetooth module.
  * PPM Frames automatically adjust based on number of configured channels
* [Telemetry](../b-and-w-radios/model-select/telemetry/)
  * **RSSI Source** option was removed - set to "default" permanently
* [Special Functions](../b-and-w-radios/model-select/special-functions.md)
  * _**Lua Script**_ function adds repeat option.
* [Display](../b-and-w-radios/model-select/display.md)
  * Added clock to Telemetry screens.
* [Radio Setup](../b-and-w-radios/radio-settings/radio-setup.md)
  * **Rx channel ord** option renamed to **Def Chan Ord** for better understanding.
* [Hardware](../b-and-w-radios/radio-settings/hardware.md)
  * **Audio Mute** option added - puts the transmitter in mute mode until a sound needs to be played. This prevents interference noise from high-powered TX modules from coming out of the transmitter speakers.&#x20;
* Language
  * Added Hewbrew language support.
* New Hardware Support
  * RadioMaster Boxer&#x20;
  * Flysky FRM303 Support (External RX Module)
  * Flysky digital gimbal support for Radio Master Boxer
  * Segger RTT debug support
