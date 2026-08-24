# Sensor Configuration Options

The below options can be configured for sensors:

* **Name:** Name of the sensor - up to 4 characters.
* **Type:** Options are **custom** or **calculated**. Custom sensors are defined by the hardware. Calculated sensors are a sensors whose value is calculated using other sensors values. See below for more information on calculated sensors.
* **ID:** This number indicates what type of sensore it is. It contains two parts. The first part is the ID number which defines the sensor type. The second part is the instance number for the hardware. If multiple sensors of the same type are configures, the instance numbers must be unique.
* **Unit:** The unit for the sensor. This unit is used when the sensor value is displayed on the screen or read aloud.
* **Precison:** Specifies the number of digits after the decimal point when the sensor value is displayed on the screen. The number is truncated based on this setting.
* **Ratio:** Specifies the ratio value to multiply with the sensor value as needed by some sensors.
* **Offset:** Specifies the offset value to add to the sensor value.
* **Auto Offset:** When selected, the first received value is used as offset. You can use the [Reset telemetry](../../reset-telemetry.md) option to reset the offset on already configured sensors.
* **Positive:** When selected, the value of the sensor will be displayed only when it is a positive number. Displays zero when the sensor value becomes a negative number.
* **Filter:** When selected, the sensor value becomes a rolling average of the last 5 received values.
* **Logs:**  When selected, the value of this sensor will be saved in the log file. SD Card logging is configured in [Special Functions](../special-functions.md) or Global Functions.

Calculated sensors contain the additional configuration options:

* **Formula:** Type of calculation to use. Options include:
  * **Add:** Add the values of up to 4 designated sensors.
  * **Average:** Calculates the average value of up to four designated sensors.&#x20;
  * **Minimum:** Find the minimum value of up to 4 designated sensors.
  * **Maximum:** Find the maximum value of up to 4 designated sensors.
  * **Multiply:** Multiplies the value of 2 sensors.
  * **Totalize:** Calculate the cumulative value of one sensor.
  * **Cell:** This is the formula for FrSKY Lipo battery sensor. It displays cell voltage specified by the number in "Cell index" field.\
    If you specify "Lowest" in "Cell index" field, the voltage of the cell with the lowest is displayed. \
    If you specify "Highest" in "Cell index" field, the voltage of the cell with the highest is displayed.\
    If you specify "Delta" in "Cell index" field, the voltage difference between lowest and highest cell is displayed
  * **Consumpt:** Calculates the power consumption (mAh) by cumulatively add the values of current sensor.
  * **Distance:** Calculates the distance between the receiver and the radio using GPS sensor and altimeter values.
* **Source 1, 2, 3, 4:** The sensors that will provide the argument values that are used in the formula defined above.
* **Persistent:** When selected the sensor values will be saved when switching between models or powering down the radio.
