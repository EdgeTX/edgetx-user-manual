# Trims

<figure><img src="../../../.gitbook/assets/trims.png" alt=""><figcaption><p>Trims settings page</p></figcaption></figure>

Trims are used adjust the center position of a given stick axis. EdgeTX has the following time configuration options:

**Reset** - This resets all trim values to zero.

**Trim Step:** Defines the amount of increase/decrease in trim when the trim switch is pressed.&#x20;

* Course = 1.6%
* Medium = 0.8%
* Fine = 0.4%
* Extra Fine = 0.2%
* Exponential = 0.2% near the center and the step value increases exponentially as the distance from the center increases.

**Extended Trims**: Increases the maximum trim adjustment value from **±**25% to **±**100%.

{% hint style="info" %}
When switching from extended trims to normal trims, the extended trim value will remain until the trim is adjusted, then it will jump to the max/min normal trim value.
{% endhint %}

**Display trims:** Option to display the numerical trim value on the trim bar. Options are:

* **No -** Does not display the numerical trim value on the trim bar
* **Yes** - Displays the numerical trim value on the trim bar once the trim is no longer at zero.
* **Change -** Momentarily displays the numerical trim value on the trim bar (2 seconds) once the trim is no longer at zero.
