# 🚧 Setup

<figure><img src="../.gitbook/assets/bwsetup.png" alt=""><figcaption></figcaption></figure>

The **Setup** screen is where you start to configure your model. It contains the following settings:

**Name** - Enter the desired name for the model. The maximum number of characters is 10.

* To edit the text,with the **\[roller]** or **\[dial]**, press the button, scroll to select the desired letter, then press the button again to move to the next space. To toggle between lower and upper case, long-press the button. Press the **\[RTN]** button to exit out of text editing mode.

**Timer 1/2/3**  - There are 3 configurable timers in EdgeTX. They all have the same options:

#### Timer 1   \[Mode]   \[Switch]&#x20;

**Mode**: The options include:

* **OFF**- The timer is not used
* **ON** - The timer runs all the time
* **Start** -The timer starts once the configured switch is activated. After the time is started, the timer ignores the switch position.
* **Throttle** - The timer starts once the throttle is raised and the configured switch is activated. The timer will stop counting if either the throttle position is lowered back to the minimum value or the configured switch is deactivated.
* **Throttle %** - The timer counts proportionally to the throttle. It counts in real time at full throttle and at half speed at 50% throttle.
* **Throttle Start** - The timer starts once the throttle is raised and the configured switch is activated. After starting, the timer ignores the throttle position and will keep counting unless the switch is deactivated.

**Switch-** Select the switch that will trigger the timer to start.  If no switch is selected, the timer will trigger based only on the configured mode. In addition to a switch, you can also select a trim, a telemetry source (triggered when telemetry data is received from that source), or physical activity (stick movement or button press) (labeled as **ACT**)

{% hint style="info" %}
Those items with a "!" mark in front of the trigger name mean that the condition is reversed. For example, "!SA-" means "when SA switch is not in middle/center position (= up or down)".
{% endhint %}

**Name:**  Name of the timer

**Start-** The time used for the timer's advanced functions.  The default value is 00:00 and when left as such, the timer operates like a stopwatch, counting upward until stopped.  If a different time is entered in this box, then the additional field will appear next to the time with the options: **Remain** or **Elaps**.

If set to **Remain**, the counter will function like a countdown timer - counting down from the designated time to zero and then alerting the user.  If set to **Elaps**, the timer functions like an alarm, counting up from zero until the designated time and then alerting the user.

**Persist (Persistence):**

* **Off** - The timer value is reset when switching models or when the radio is turned off / on.
* **Flight** - The timer value is NOT reset when switching models or when radio is turned off / on. The timer value is only reset when the **Reset flight** option is selected in the [Reset](main-view/reset.md) menu.
* **Manual Reset -** The timer value is reset only when it is individually selected to be reset (example: Reset timer1) in the [Reset](main-view/reset.md) menu.

**Minute (Minute Call)** - If selected, you will be notified every minute that passes as described in the **Count Down** option.

**Count Down:**

* **Silent** - No notification is given until the timer reaches zero. When it reaches zero, you will hear one beep.
* **Beeps** - The radio will beep every second starting at the time designated.
* **Voice** - The radio will count down by second starting at the time designated.
* **Haptic** -The radio will vibrate every second starting at the time designated.

<figure><img src="../.gitbook/assets/setup2.png" alt=""><figcaption><p>Trims settings</p></figcaption></figure>

**E.Limits (Extended Limits)** - When enabled, it increases the minimum and maximum range for the output values to -150 and 150. Extended limits are may be necessary if the full range of the control surface cannot be reached with standard limits.

**E. Trims) Extended Trims**: Increases the maximum trim adjustment value from **±**25% to **±**100%.

**Reset** - This resets all trim values to zero.

**Show trims:** When set to **Yes**, it will display the numerical trim value on the trim bar.  When set to **CHANGE**, it will display the numerical value once the trim is no longer at zero.

**Trim Step:** Defines the amount of increase/decrease in trim when the trim switch is pressed.&#x20;

* Course = 1.6%
* Medium = 0.8%
* Fine = 0.4%
* Extra Fine = 0.2%
* Exponential = 0.2% near the center and the step value increases exponentially as the distance from the center increases.

<figure><img src="../.gitbook/assets/bwsetup3.png" alt=""><figcaption><p>Throttle Settings</p></figcaption></figure>

**T-Reverse:** When enabled, this option reverses the output direction of the configured throttle channel.

**T-Source:** The source that will be used for the throttle.&#x20;

**T-Trim-Idle**: When enabled, the throttle trim will only affect the bottom portion of the throttle band.&#x20;

{% hint style="info" %}
For example, with **Trim idle only** enabled, the throttle stick at the lowest point might have a value of -80 and the center point will still be 0 and the highest point of 100. Without this enabled, the throttle stick at the lowest point might have a value of -80 however, the center point will be 20 and the highest point of 100.&#x20;
{% endhint %}

**T-Trim-SW:** The trim switch that will be used to trim the throttle. It is possible to substitute the throttle trim switch with the aileron, rudder, or elevator trim switches.

<figure><img src="../.gitbook/assets/bwsetup4.png" alt=""><figcaption><p>Prefligh Checks options</p></figcaption></figure>

Whenever a new model is loaded, EdgeTX will conduct pre-flight checks based on the checks that are configured on this page. If any of the checks are failed, EdgeTX will give the user an audio and visual warning that must be acknowledged before using the model. The following preflight checks are configurable:

**Checklist** - When this option is selected, the model notes file will be displayed when the model is loaded. A valid model notes file must be in the **Models** folder on the SD card. The model notes file must be a .txt file and must have the EXACT same name as the model it is for, for example: Mobula6.txt. The text in the file is up to the user.

**T-Warning** - When selected, the radio will check that the throttle is at the minimum range value for the configured throttle source in the [Throttle](../edgetx-user-manual/user-manual-for-color-screen-radios/model-settings/model-setup/throttle.md) menu.

**Cust-Pos** - When this option is selected, the value designated in **POS.%** will be used for the T.Warning.

**Pos.%** - user-defined value for the throttle state check.&#x20;

**S-Warning** - The section displays all the switches that are configured on the radio and allows you to select which position is the correct position for the switch state check. Selecting the switch will cycle through the available switch positions or turn the check off for the switch completely.

**Pot warn**- When activated, this option checks the position of the pots & sliders. There are three options - OFF, ON and AUTO. When ON or AUTO is selected, buttons for the available pots and sliders will appear.&#x20;

* **OFF** - Pot and slider positions are not checked.
* **Manual** - Positions are checked against manually configured pot and slider positions. To manually set the check position, select manual from menu, select the item that you want to set and long-press the \[Enter] button to set its current position for the check.&#x20;
* **AUTO** - Positions are checked for pots and sliders and compared to the last automatically saved position before the radio was turned off or the model was changed.
