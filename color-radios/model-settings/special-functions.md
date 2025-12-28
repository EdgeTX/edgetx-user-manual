---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/2n2y0XsJcrhXt3asceP0/color-radios/model-settings/special-functions
---

# Special Functions

The **Special Functions** section of Model Setup, as the name implies, is where you can configure the special functions that are included in EdgeTX. These special functions add additional functionality beyond normal model controls such as enabling trainer mode, playing a sound, adjusting the radio backlight, adjusting radio volume, etc. On the special functions screen you will see all configured special functions as well as some of the configured options such as function name, activation switch, if the function is enabled, and other configuration options.

<figure><img src="../../.gitbook/assets/specialfunctions.png" alt=""><figcaption><p>Special Functions</p></figcaption></figure>

Selecting the **+** button will allow you to select an unused special function to configure and the special function configuration window will appear. See [configuring special functions](special-functions.md#configuring-special-functions) below for information about configuring new special functions.

Selecting an already configured special function will give you the following options:

* **Edit** - Opens the special function configuration page
* **Copy** - Copies the selected special function
* **Paste** - Pastes a copied special function to the selected special function. Note: this will overwrite the value of the selected special function with the copied special function.
* **Insert** - Inserts a blank special function above the selected special function
* **Clear** - Clears all configured options from the selected special function.
* **Delete** - Deletes the selected special function.
* **Enable** - Enables special function
* **Disable** - Disables special function&#x20;

### Configuring Special Functions

All special functions have the configuration options below. Additional options may be added based on the selected function. See the **Functions** section below for these additional options.

* **Trigger**- The switch that will make the special function active.
* **Function** - The function that will be used. See below for function descriptions.
* **Enable** - Toggle on / off to enable the function. To be able to activate the special function by a switch, it must be enabled. Disabled special functions will not function regardless of the configured switch position.

### Functions

Below are all the available functions in EdgeTX, what they do, as well as what other configuration options exist specifically for that function.

**Adjust** (Adjust Global Variable) - Changes the value of the specified global variable.

* **Global var** - Select the global variable that you want to adjust.
* **Mode** - Select the mode to change the global variable. Options are: **Constant, Mixer Source, Global var, Inc/Decrement**
  * **Constant** - Sets the specified global variable to the defined constant value.
  * **Mixer Source** - Sets the specified global variable to the defined mixer source value.
  * **Global Var** - Sets the specified global variable to the defined global variable value.
  * **Inc/Decrement** - Increments/decrements the specified global variable by the specified amount.

**Audio Amp Off** (select radios) - Disables the Audio Amplifier so that no sound comes from the speaker, including annoying feedback or interference.

**Backlight** - Adjusts the brightness of the radio screen based on the source defined in the value dropdown. Brightness is limited to the On / Off values configured in the **Radio Setup -> Backlight Screen.**

**BgMusic** - Plays the .wav file selected in the value field on a loop when enabled. The file shall be in the SOUNDS/(language)/ folder on the SD card.

**BgMusic II** - Temporarily pauses the .wav file playback specified in the **BgMusic**

**Haptic** - Causes the radio to vibrate (haptic feedback) when enabled.

* **Value** - Type of vibration pattern. Options are: 0 - 4.
* **Repeat** - Frequency to repeat the vibration pattern. Options are **!1x** (do not vibrate at startup even if the switch is active), **1x** (vibrate once), **1s** thru **60s** (vibrate every xx seconds).

**Inst. Trim** (Instant Trim)- Sets all trims to the current values of their respective sticks.

**Lua Script** - Executes the Lua script defined in the value field. The Lua script must be located in `/SCRIPTS/FUNCTIONS/` folder on the SD card. Lua scripts that display information on the screen cannot be executed with this special function.

* **Value** - LUA script file to play from the SD card.
* **Repeat** - Frequency to repeat the Lua script. Options are: **ON** (repeat indefinitely as long as switch is active) or **1x** (once)

**No Touch** - Disables the touch interface for touchscreen-enabled radios.

**Override** (Channel Override) - Overrides the defined channel with the defined value.

* **CH** - Channel to be overridden
* **Value** - Value to replace the normal channel value. (Range -100 to +100)

**Play Sound** - Plays the sound selected in the value field when activated.

* **Value** - Sound to play. Possible values are **Beep1/2/3, Warn1/2, Cheep, Ratata, Tick, Siren, Ring, SciFi, Robot, Chirp, Tada, Crickt, AlmClk**. _Note: SD card sound pack is not required._
* **Repeat** - Frequency to repeat the sound. Options are **!1x** (do not play at startup even if the switch is active), **1x** (play once), **1s** thru **60s** (play every xx seconds).

**Play Track** - Plays the .wav sound file selected in the value field when activated.

* **Value** - .wav sound file to play from the SD card.
* **Repeat** - Frequency to repeat the track. Options are **!1x** (do not play at startup even if the switch is active),  **1x** (play once), **1s** thru **60s** (play every xx seconds).

**Play Value -** Announces the value of the selected element in the value field.

* **Value** - The source for the value to announce. It can be an input, stick, pot, slider, trim, physical and logical switch, trainer import channel value, global variable, telemetry sensor or channel.
* **Repeat** - Frequency to repeat the announcement. Options are **!1x** (do not announce at startup even if the switch is active), **1x** (announce once), **1s** thru **60s** (announce every xx seconds).

**RacingMode** - Enables racing mode (low latency) for FrSky Archer RS receivers. Racing mode must also be enabled in External RF Module Settings.

**Reset** (Reset Timer)- Resets the timer or telemetry specified in the value back to their initial values.

* **Reset** - Options are **Timer 1, Timer 2, Timer 3, Flight,** and **Telemetry.** See[ **Reset Telemetry**](../reset-telemetry.md) for more information on what data is reset for each option.

**Screenshot** -  Creates screenshot as a .bmp file in the SCREENSHOT folder on the SD Card.

**SD Logs** - Creates a log .csv file of the radio and telemetry values in the LOGS folder on the SD Card. The radio will create a new entry into the log file based on the frequency configured in the **Interval** setting.  The value options are **0.1s** - **25.5s.** Each time the function is activated the radio will create a new log file provided that the function is activated at least as long as the value setting. **Note:** Logging will not start if SD card has less than 50mb of free space.&#x20;

**Set** (Set Timer) - Sets the specified timer to the specified value.

* **Timer** - Options are **Timer 1, Timer 2, Timer 3**
* **Value** - The range is 00:00:00 to 08:59:59&#x20;

**SetFailsafe** - Sets the custom failsafe values for the selected module (Internal/External) to the current stick position when activated. For this option to work, the Failsafe mode for the RF module must be set to **custom**.

**Set Main Screen** - Changes the current visible screen to the screen number defined.

* **Value** - The screen number as defined in the [Screens settings.](../screen-settings/)
* **Repeat** - When the switch remains active, the repeat value determines how often the special function will change the screen to the defined screen. Options are **!1x** (do not change at startup even if the switch is active), **1x** (change once), **1s** thru **60s** (change every xx seconds). This is useful because when the switch has been activated, the user can still manually switch screens, and then it will change back to the defined screen after the defined duration.

**Trainer -** Enables trainer mode.

* **Value** - Specifies which controls will be given over to the student. Options include **Axis** (all sticks / primary controls), **Rud** (Rudder), **Ele** (Elevator), **Thr** (Throttle), **Ail** (Aileron), and **Chans** (all channels).&#x20;

**Vario** - Enables the variometer beeping sound for the ascent and descent of the model.

**Volume** - Changes the radio volume. The change source is specified in the Volume dropdown.
