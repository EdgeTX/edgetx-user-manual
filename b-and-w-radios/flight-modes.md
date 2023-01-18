---
description: Under Construction
---

# 🚧 Flight Modes

Flight modes allow you to have different trim settings for each flight mode. Once multiple flight modes are configured, you can adjust the trim settings in each flight mode without affecting the trim settings in other flight modes (unless they are configured to do so). There are 9 possible flight modes to use, with Flight Mode 0 being the default flight mode.

<figure><img src="../.gitbook/assets/bwFM.png" alt=""><figcaption><p>Flight Modes Overview screen</p></figcaption></figure>

The Flight Modes Overview screen shows an overview of the configured Flight Modes. The information below is displayed for each flight mode row:

* Flight Mode
* Flight Mode Name
* Switch
* Trim settings (RETA)

**Check FM Trims:** When check FM trim is pressed, the trims for the current flight mode are temporarily disabled. This is used to test the impact of the current flight mode’s trims on the outputs

<figure><img src="../.gitbook/assets/bwFM2.png" alt=""><figcaption><p>Flight Mode Configuration screen</p></figcaption></figure>

Selecting a Flight Mode from the overview screen will open the configuration page, which has the following options:

**Name:** The custom name for the flight mode. If configured, this name will be shown on the lower center position of the main screen between the trims.

**Switch:** The trigger to enable that flight mode. It can be a switch, pot, telemetry, trim or logical switch.

**Trims** - To configure the trims, select the trim that you want to configure (each column is on trim). Then scroll to select the the flight mode (**0-8**) that will provide the initial trim value and modifier (**=** or **+**). Select **--** to disable the trim.

_**Modifier**_ - there are two possible value modifiers **=** and **+.** The **=** modifier uses the trim value directly from the selected flight mode. The **+** modifier uses the trim value from the selected flight mode and then adds the trim value from the flight mode you are configuring.

_Example 1:_ If you are configuring FM1 and set the value to =0, FM1 will have the trim value of the current value of the same trim in FM0. In this case, changes made to the trim in FM1 will also affect the trim in FM0 and vice-versa.

_Example 2:_ If you are configuring FM1 and set the value to +0, FM1 will have the trim value of the same trim in FM0, plus any trim changes made while in FM1, In this case, changes made to the trim in FM1 do not affect the trim in FM0. However, changes to trim values FM0 will affect trim values in FM1.

**Fade in:** Gradually change the trim value when this flight mode is enabled. Specify the time in seconds (0.0 - 25.0) until the value change is completed.

**Fade out:** Gradually change the trim value when this flight mode is disabled. Specify the time in seconds (0.0 - 25.0) until the value change is completed.

{% hint style="info" %}
If the trim is turned off (**--**) on the setup page, you will not be able to adjust it at all on the main view screen.
{% endhint %}
