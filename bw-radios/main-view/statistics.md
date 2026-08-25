---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/2n2y0XsJcrhXt3asceP0/bw-radios/main-view/statistics
---

# Statistics

<figure><img src="../../.gitbook/assets/bwstats.png" alt=""><figcaption><p>Statistics screen</p></figcaption></figure>

The **Statistics** screen presents you with statistics regarding radio usage. All data is reset once the radio is powered off. The following information is provided:

* **SES** - The amount of time that the radio has been turned on.
* **TOT** - The total accumulated time the radio has been turned on, across all sessions (not reset when the radio is powered off).
* **THR** - The amount of time that the throttle has been above the 0% stick position.
* **TH%** - The amount of time that the throttle has been above the 50% stick position.
* **TM1 / TM2 / TM3** - The current values of Timer 1, Timer 2, Timer 3.

Long pressing the **\[Roller]** or **\[Dial]** button will reset the Statistics and Debug screens.

Pressing **\[PAGE>]** will take you to the **Debug** screens.

<div><figure><img src="../../.gitbook/assets/bwdebug.png" alt=""><figcaption><p>Debug screen 1</p></figcaption></figure> <figure><img src="../../.gitbook/assets/bwdebug2.png" alt=""><figcaption><p>Debug screen 1</p></figcaption></figure></div>

The **Debug** screen provides data points used by the developers when debugging issues in the software. Most users will not find the information useful on this screen unless debugging issues with developers. The following debug information is provided, and may change depending on handset capabilities and options configured.

* **Free mem** - Current free radio memory in bytes.
* **Lua scripts**
  * **\[D] -** Maximum Lua duration in milliseconds.
  * **\[I]** - Maximum Lua interval in milliseconds.
* **TMix max** - Maximum mixer task duration, followed by the mixer scheduler's configured period in parentheses.
* **Free stack - \[Menu] / \[Mix] /\[Audio]**
  * **\[Menu]** - Minimum free stack memory for menu tasks.
  * **\[Mix]** - Minimum free stack memory for mixer tasks.
  * **\[Audio]** - Minimum free stack memory for audio tasks.
* **BT status** (select radios) - Whether the Bluetooth chip is detected. Only shown on radios with Bluetooth hardware.
