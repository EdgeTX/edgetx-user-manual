# Hardware

<figure><img src="../../../.gitbook/assets/hardware.jpg" alt=""><figcaption><p>Hardware Screen</p></figcaption></figure>

The **Hardware** screen is where you configure hardware specific-settings for your radio. It contains the following configuration options:

**Battery meter range** - Sets the maximum and minimum voltage for the battery meter. This should be set based on the type of battery you are using.

**Battery Calibration** - Set this value to match the transmitter battery voltage.

**Check RTC voltage** - When enabled, checks the RTC battery at startup and warns you if the battery voltage is low.

**ADC Filter** - Enables or disables the ADC Filter. This filter can also be enabled/disabled per model in the model settings.

{% hint style="info" %}
The ADC filter is a filter for the proportional channels (sticks, pots, sliders), smoothing out smaller fast movements that occur due to noise in the system electronics. Normally, this filter should be _disabled_ for models with flight controllers.&#x20;
{% endhint %}

**Internal RF Type** - Select the module type for the internal module bay. Options are: **Multi, XJT, ISRM, CRSF**.  When **CRSF** is selected, you can also select the baud rate. You can read more about baud rates [here](https://www.expresslrs.org/2.0/quick-start/transmitters/tx-prep/).

**External RF Sample Mode** - Options are Normal and OneBit. The default setting of **Normal** should be used by most users. Only users of  X9D+ and X7 radios may want to use **OneBit** mode.

{% hint style="info" %}
The X9D+ and X7 radios have a slow inverter that causes problems with the reception of fast UART signals, resulting in telemetry warnings and issues with LUA scripts using the CRSF protocol. A 10k resistor on the circuit board could be replaced to fix the issue, but this was not always effective. EdgeTX has developed OneBit Mode, which changes the UART sampling behavior to ignore slow leading edges, allowing the CRSF protocol to be run at the full 400k baud rate without hardware modifications to the radio.
{% endhint %}

**Serial Port** - Displays a list of available auxiliary serial ports that can be configured and used. The listed ports are based on the ports that are available in the particular radio hardware. The ports listed below are for example only and may not be present in your radio.

* **AUX1** - First available auxiliary serial port can be configured with the below options:
  * **OFF** - Turned off.
  * **Telem Mirror** - The same telemetry data that goes to the external module bay is sent to the serial port.&#x20;
  * **Telemetry In** - Receive telemetry data over the serial port.
  * **SBUS Trainer** - Connect the Instructor and Student radios over the serial port.
  * **LUA** - Send/receive data to/from Lua script.
  * **GPS** - Receive GPS telemetry data over the serial port.
  * **CLI** - Send commands to the radio via the command line.&#x20;
* **Port Power** - Enables or disables the power output on the power supply pins next to serial ports that are available on some radios (presently only TX16S has this feature).

**Calibration** - For calibrating your physical radio controls (sticks, pots, sliders, & 6-position switch). The radio will prompt you through the calibration steps.&#x20;

{% hint style="info" %}
For your gimbal calibration, use a left-to-right & up-to-down movement for the gimbals, not a circular movement! Additionally, use the normal amount of pressure at the endpoints. Excessive endpoint pressure will cause the gimbal to be miscalibrated. Also, do not forget to calibrate your 6-position switch!
{% endhint %}

<div>

<figure><img src="../../../.gitbook/assets/hardware3.jpg" alt=""><figcaption><p>Inputs screen</p></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/hardware2.jpg" alt=""><figcaption><p>Switches Screen</p></figcaption></figure>

</div>

#### Inputs, Sticks, Pots, and Switches Buttons

Selecting one of the Inputs, Sticks, Pots, or Switches Buttons will open the configuration screen.  On this screen, you will see all the physical radio controls pre-defined by EdgeTX.  Here you can add a 3 character label to the control as well as change the type of control as needed.

#### Debug

The debug section allows for testing and debugging of the analog controls and keys.

<div>

<figure><img src="../../../.gitbook/assets/hardware4.jpg" alt=""><figcaption><p>Debug Analogs screen</p></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/hardware5.jpg" alt=""><figcaption><p>Debug Keys screen</p></figcaption></figure>

</div>

**Debug Analogs**  - These screens will show you the data for your analog controls (Sticks, Sliders, Pots, 6-position switch) and the touch screen on your radio. There are three views - Calibrated analog, Filtered Raw Analog with deviation, Unfiltered raw analog, and Min Max and range.&#x20;

**Debug Keys** - This screen will show you the digital data for your keys, switches, trims, and the rotary encoder (roller).
