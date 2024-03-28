# Additional Radio settings

Selecting one of the 6 buttons on the **Radio Setup** screen will take you to one of the additional setting screens below.

Many of the additional settings here are self-explanatory. Only those settings needing clarification will be mentioned below.

### Sound

<figure><img src="../../../.gitbook/assets/Sound.png" alt=""><figcaption><p>Sound Options</p></figcaption></figure>

**Mode** - configures when to play sounds.

* **All -** Beeps when the buttons are pressed and sounds are played when there are alerts or warnings.
* **No Key -** No beeps when buttons are pressed or the scroll wheel is turned but does play sounds when there are alerts or warnings. Also plays sounds triggered by special functions.
* **Alarm -** Only plays alarm or warning sounds. Also plays sounds triggered by special functions.
* **Quiet -** No Beeps or sounds are played.&#x20;

**Volume**

The master volume for the radio.

**Wav volume**

The volume for alerts and warnings and sounds that are played with the **Play track** special function

**Background volume**

The volume for background .wav files (music) that are played with the **BGMusic** special function&#x20;

### Variometer

<figure><img src="../../../.gitbook/assets/variometer.png" alt=""><figcaption><p>Variometer options</p></figcaption></figure>

**Repeat Zero**

The time before the tone repeats in milliseconds.

{% hint style="info" %}
Note: In order for the variometer to function, it must be turned on via the **Vario** special or global function. See [Special Functions](../../model-settings/special-functions.md) for more information on how to configure this.
{% endhint %}

### Haptic

<figure><img src="../../../.gitbook/assets/haptic.png" alt=""><figcaption><p>Haptic (vibration) options</p></figcaption></figure>

**Mode** - configures when the radio vibrates.

* **All -** Vibrates when the buttons are pressed and when there are alerts or warnings.
* **No Key -** No vibrations when buttons are the pressed or scroll wheel is turned but does vibrate when there are alerts or warnings.&#x20;
* **Alarm -** Only vibrates for alarms or warning sounds.
* **Quiet -** No vibrations are made.

### Alarms

<figure><img src="../../../.gitbook/assets/alarms.png" alt=""><figcaption><p>Alarm options</p></figcaption></figure>

#### Sound Off

An "alarms disabled" visual warning is displayed when the transmitter is turned on if the sound mode is set to quiet.

#### Check RSSI on Shutdown

Checks if a receiver is still connected to the radio on attempted shutdown. Makes a audio and visual alert if one is detected.&#x20;

### Backlight

<figure><img src="../../../.gitbook/assets/backlight.png" alt=""><figcaption><p>Backlight options</p></figcaption></figure>

**Mode**

* **Off** – Always off.
* **Keys** – Turns on when buttons are pressed.
* **Ctrl** – Turns on when sticks, switches, and knobs are used.
* **Both** – Turns on when buttons, sticks, switches, and knobs are used.
* **ON** – Always on.

#### Time&#x20;

The length in seconds that the backlight is on. The minimum value is 5 seconds. The maximum value is 600 seconds.

#### Alarm

The backlight turns on when there are alarms or warnings.

### GPS

<figure><img src="../../../.gitbook/assets/gps.png" alt=""><figcaption><p>GPS options</p></figcaption></figure>

{% hint style="info" %}
The GPS configuration settings are only for when a GPS has been installed on the radio, not the model's GPS.
{% endhint %}

#### Time Zone:

The time offset from UTC where the radio is being used. Can be configured in 15 minute increments.

#### Adjust RTC

Adjust the transmitter's real-time clock to match the time determined by the GPS.

#### Coordinate Format

The GPS coordinate format that will be displayed.

### Enabled Features

<figure><img src="../../../.gitbook/assets/EnabledFeatures.png" alt=""><figcaption><p>Enabled Reatures</p></figcaption></figure>

The **Enabled Features** section of Radio Setup allows you to configure the _**Global**_ _**settings**_ for which tabs are visible in the Radio Setup and Model Settings area of EdgeTX. The configuration setting for the active model will show to the right of the toggle switch. The model configuration will override the global configuration.

{% hint style="info" %}
_**Note:**_ Turning off a tab only hides the tab and does not change the items already configured in that tab.

**EXCEPTION:** Turning off the Global / Special Functions tab will disable configured global / special functions for that model.
{% endhint %}

### Manage Models

<figure><img src="../../../.gitbook/assets/RSManageModels.png" alt=""><figcaption><p>Manage Models settings</p></figcaption></figure>

**Model quick select** - Affects Manage Model screen. Both options require you first to select the desired model using the scroll wheel or short tap.

* When OFF: short/long tap (short/long ENTER) on the selected model will show the menu, where you can "Select model" to set it to active.
* When ON: short tap (short ENTER) on the selected model will set it active immediately. To activate the menu, make a long tap or long ENTER.

**Label select** - '**Multi select**' or '**Single select**' (Multi select is the default). If Single select is chosen then only a single label can be selected.

**Label matching** - '**Match all**' or '**Match any**' (Match all is the default). Match all is the current logic - only models having all selected labels are shown. Match any will show models with any of the selected labels.

**Favorites matching** - Only available when '**Match any'** is selected for Label matching. Options are '**Must match**' and '**Optional match**' (Must match is the default). Only applies when 'Favorites' is in one of the selected labels. If 'Must match' is selected then only shows models that have Favorites AND the other selections. If 'Optional match' is selected then models that match Favorites OR any of the other labels are shown.
