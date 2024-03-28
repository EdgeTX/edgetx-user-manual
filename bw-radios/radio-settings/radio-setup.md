# Radio Setup

<figure><img src="../../.gitbook/assets/bwRadioSetup.png" alt=""><figcaption><p>Radio Setup</p></figcaption></figure>

The **Radio Setup** screen is where you configure basic settings for your radio. It contains the following options:

**Date** - The current date.  This date is used for the SD card log files.

**Time** - The current time. This time is used for the SD card log files.

**Batt. range** - Sets the maximum and minimum voltage for the battery meter. This should be set based on the type of battery you are using.



<figure><img src="../../.gitbook/assets/bwRadioSetup2.png" alt=""><figcaption><p>Sound Settings</p></figcaption></figure>

### **Sound**&#x20;

**Mode** - configures when to play sounds.

* **All -** Beeps when the buttons are pressed and sounds are played when there are alerts or warnings.
* **No Key -** No beeps when buttons are pressed or the scroll wheel is turned but does play sounds when there are alerts or warnings. Also plays sounds triggered by special functions.
* **Alarm -** Only plays alarm or warning sounds. Also plays sounds triggered by special functions.
* **Quiet -** No Beeps or sounds are played.&#x20;

**Volume -** The master volume for the radio.

**Beep Volume** - Self-explanatory

**Beep Length** - Self-explanatory

**Beep Pitch** - Self-explanatory

**Wav volume -** The volume for alerts and warnings and sounds that are played with the **Play track** special function

**Bg volume -** The volume for background .wav files (music) that are played with the **BGMusic** special function

<figure><img src="../../.gitbook/assets/bwRadioSetup3 (1).png" alt=""><figcaption><p>Variometer Settings</p></figcaption></figure>

### **Vario  (Variometer)**

**Volume** - Volume for variometer beeps

**Pitch zero** - Low pitch frequency

**Pitch max** - High pitch frequency

**Repeat Zero -** The time before the tone repeats in milliseconds

{% hint style="info" %}
Note: In order for the variometer to function, it must be turned on via the **Vario** special or global function. See [Special Functions](../../color-radios/model-settings/special-functions.md) for more information on how to configure this.
{% endhint %}

<figure><img src="../../.gitbook/assets/bwRadioSetup4.png" alt=""><figcaption><p>Haptic Settings</p></figcaption></figure>

### Haptic

**Mode** - configures when the radio vibrates.

* **All -** Vibrates when the buttons are pressed and when there are alerts or warnings.
* **No Key -** No vibrations when buttons are the pressed or scroll wheel is turned but does vibrate when there are alerts or warnings.&#x20;
* **Alarm -** Only vibrates for alarms or warning sounds.
* **Quiet -** No vibrations are made

**Length** - Duration of vibration.

**Strength** - Strength of vibration

<figure><img src="../../.gitbook/assets/bwRadioSetup5.png" alt=""><figcaption><p>Alarms Settings</p></figcaption></figure>

### Alarms

**Battery Low** - Voltage to trigger low battery alarm.

**Inactivity** - Time to trigger inactivity warning.

**Memory low** - Enable/disable low memory warning.

**Sound Off** - An "alarms disabled" visual warning is displayed when the transmitter is turned on if the sound mode is set to quiet.

**RSSI Shutdown** - Checks if a receiver is still connected to the radio on attempted shutdown. Makes a audio and visual alert if one is detected.&#x20;

<figure><img src="../../.gitbook/assets/bwRadioSetup6.png" alt=""><figcaption><p>Backlight Settings</p></figcaption></figure>

### Backlight

**Mode**

* **Off** – Always off.
* **Keys** – Turns on when buttons are pressed.
* **Ctrl** – Turns on when sticks, switches, and knobs are used.
* **Both** – Turns on when buttons, sticks, switches, and knobs are used.
* **ON** – Always on.

**Duration** - The length in seconds that the backlight is on. The minimum value is 5 seconds. The maximum value is 600 seconds.

**Brightness** - Adjusts the screen backlight brightness level.

**Alarm** - The backlight turns on when there are alarms or warnings.

<figure><img src="../../.gitbook/assets/bwRadioSetup7.png" alt=""><figcaption></figcaption></figure>

**Contrast** - For LCD displays, adjusts the screen contrast setting. For OLED displays. adjusts the OLED brightness level.

**Splash Screen** - Duration to display the splash screen.

**Startup Sound** - Toggles whether to enable/disable startup sound.

**Power On delay** - The delay between when the power button is pushed and when the radio turns on. The options are: **0s, 1s, 2s, 3s**

**Pwr Off delay** - The delay between when the power button is pushed and when the radio shuts off. The options are: **0s, 1s, 2s, 3s, 4**s. _It is recommended to set at least a 1s delay in order to prevent the radio from being shut off in the case of an accidental button press._

**Owner ID** - Custom registration ID used only for users with ISRM modules.

**Time Zone** - The time offset from UTC where the radio is being used. Can be configured in 15 minute increments.

<figure><img src="../../.gitbook/assets/bwRadioSetup8.png" alt=""><figcaption></figcaption></figure>

**Adjust RTC** - Adjust the transmitter's real-time clock to match the time determined by the GPS.

**GPS Coords** - The GPS coordinate format that will be displayed.

**Country code** - Used by some RF modules to ensure adherence to local regulatory RF requirements. Options are **America, Japan, Europe.**

**Voice language** - Language for the voice pack. This setting and the voice pack folder on the SD card must match for the sounds to be played.

**Units** - Units of measure. Options are **metric** or **imperial**.

**PPM Units** - Level of accuracy for PPM values are displyed. Options are **0.-** or **0.0**

**Play delay** (sw. mid pos) - The minimum time in milliseconds a switch must be in the middle position before a special function will get activated. This is used to prevent the middle position from being activated on a three-position switch when switching from low position to high position.

<figure><img src="../../.gitbook/assets/bwRadioSetup9.png" alt=""><figcaption></figcaption></figure>

**USB Mode** - Sets the default action when a USB cable is plugged into the USB data port and the radio is powered on.  Options are: **Ask**, **Joystick**, **Storage**, and **Serial**.

**Def Chan Ord** - The default channel order for new models and the trainer screen.  The letters stand for: **A** = Aileron, **E** = Elevator, **T** = Throttle,  **R** = Rudder.  Changing this setting does not affect existing models. On Surface Radios, the letters stand for **S**=Steering, **T**=Throttle.

**RotEnc Mode** (Rotary Encoder Mode) - Sets the direction of the rotary encode for the Roller. The options are:

* **Normal** (default)
* **Inverted** = Reverses the direction of the roller
* **V-I H-N** = Vertical Inverted, Horizontal Normal
* **V-I H-A** = Vertical Inverted, Horizontal Alternate (Inverted)
* **V-N E-I** = Vertical Normal, Edit Inverted (inverted when editing text)

**Mode** - The stick mode that will be used for the transmitter. Defined by what actions the left stick takes. The options are:

<table><thead><tr><th width="181">Option</th><th width="168">Left stick  H</th><th width="149">Left stick  V</th><th width="133">Right stick H</th><th>Right stick V</th></tr></thead><tbody><tr><td>1: Left = Rud+Ele </td><td>Rudder (Yaw)</td><td>Elevator (Pitch)</td><td>Aileron (Roll)</td><td>Throttle</td></tr><tr><td>2: Left = Rud+Thr</td><td>Rudder (Yaw)</td><td>Throttle</td><td>Aileron (Roll)</td><td>Elevator (Pitch)</td></tr><tr><td>3: Left = Ail+Ele</td><td>Aileron (Roll)</td><td>Elevator (Pitch)</td><td>Rudder (Yaw)</td><td>Throttle</td></tr><tr><td>4: Left = Ail+Thr</td><td>Aileron (Roll)</td><td>Throttle</td><td>Rudder (Yaw)</td><td>Elevator (Pitch)</td></tr></tbody></table>



<figure><img src="../../.gitbook/assets/bwEnabledFeatures.png" alt=""><figcaption><p>Enabled Features</p></figcaption></figure>

### Enabled Features

The **Enabled Features** section of Radio Setup allows you to configure the _**Global**_ _**settings**_ for which tabs are visible in the Radio Setup and Model Settings area of EdgeTX. The configuration setting for the active model will show to the right of the checkbox. The model configuration will override the global configuration.

{% hint style="info" %}
_**Note:**_ Turning off a tab only hides the tab and does not change the items already configured in that tab.

**EXCEPTION:** Turning off the Global / Special Functions tab will disable configured global / special functions for that model.
{% endhint %}

Pressing the **\[PAGE>]** button will take you to the **Global Functions** screen.
