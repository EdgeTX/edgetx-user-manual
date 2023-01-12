# Statistics

<figure><img src="../../.gitbook/assets/bwstats.png" alt=""><figcaption><p>Statistics screen</p></figcaption></figure>

The **Statistics** screen presents you with statistics regarding radio usage. Except for Battery, all data is reset once the radio is powered off. The following information is provided:

* **SES** - The amount of time that the radio has been turned on.&#x20;
* **THR**  - The amount of time that the throttle has was above the 0% stick position.
* **TH%** - The amount of time that the throttle has was above the 50% stick position.
* **TM1/2/3** - The current values of Timer 1, Timer 2, Timer 3.

<figure><img src="../../.gitbook/assets/bwdebug.png" alt=""><figcaption></figcaption></figure>

The **Debug** screen provides data points used by the developers when debugging issues in the software. Most users will not find the information useful on this screen unless debugging issues with developers. The following debug information is provided.

* **Free mem** - Current free radio memory in bytes.
* **Lua scripts**&#x20;
  * **\[Dur] -** Maximum Lua duration in milliseconds.
  * **\[Int]** - Maximum Lua interval in milliseconds.
* **TMix max** - Maximum mixer task duration.
* **Free stack**
  * **\[Menu]** - Minimum free stack memory for menu tasks.
  * **\[Mix]** - Minimum free stack memory for mixer tasks.
  * **\[Audio]** - Minimum free stack memory for audio tasks.
