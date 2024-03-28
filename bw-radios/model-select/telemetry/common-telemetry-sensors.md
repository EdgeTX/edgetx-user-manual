# Common Telemetry Sensors

The following sensors are commonly used and normal automatically detected by EdgeTX:

<table><thead><tr><th width="107">Name</th><th width="419.3333333333333">Description</th><th>Data source</th></tr></thead><tbody><tr><td>1RSS</td><td>Received signal strength antenna 1 (RSSI)</td><td>Receiver</td></tr><tr><td>2RSS</td><td>Received signal strength antenna 2 (RSSI)</td><td>Receiver</td></tr><tr><td>Rqly</td><td>Receiver link quality (valid packets)</td><td>Receiver</td></tr><tr><td>RSNR</td><td>Receiver signal-to-noise ratio</td><td>Receiver</td></tr><tr><td>RFMD</td><td>Receiver packet rate</td><td>Receiver</td></tr><tr><td>TPWR</td><td>Transmitter transmitting power</td><td>Transmitter</td></tr><tr><td>TRSS</td><td>Transmitter signal strength antenna</td><td>Transmitter</td></tr><tr><td>TQly</td><td>Transmitter link quality (valid packets)</td><td>Transmitter</td></tr><tr><td>TSNR</td><td>Transmitter signal-to-noise ratio</td><td>Transmitter</td></tr><tr><td>ANT</td><td>Sensor for debugging only</td><td>Transmitter</td></tr><tr><td>GPS</td><td>GPS Coordinates</td><td>GPS / Flight Controller</td></tr><tr><td>Alt</td><td>GPS Altitudes</td><td>GPS / Flight Controller</td></tr><tr><td>Sats</td><td>GPS Satellites acquired</td><td>GPS / Flight Controller</td></tr><tr><td>Hdg</td><td>Magnetic orientation</td><td>GPS / Flight Controller</td></tr><tr><td>RXBt</td><td>Battery voltage</td><td>Flight Controller</td></tr><tr><td>Curr</td><td>Current draw</td><td>Flight Controller</td></tr><tr><td>Capa</td><td>Current consumption</td><td>Flight Controller</td></tr><tr><td>Ptch</td><td>FC Pitch angle</td><td>Flight Controller</td></tr><tr><td>Roll</td><td>FC Roll angle</td><td>Flight Controller</td></tr><tr><td>Yaw</td><td>FC Yaw angle</td><td>Flight Controller</td></tr><tr><td>FM</td><td>Flight mode</td><td>Flight Controller</td></tr><tr><td>VSPD</td><td>Vertical Speed</td><td>Flight Controller w/ Baro</td></tr></tbody></table>

{% hint style="info" %}
Each sensor has two auto generated sensors for their minimum and maximum values. They share the same name with a negative and positive symbol added to the end. For example: **RXBt +** This dispalys the maximum value that the sensor attained during the flight. Using the [Reset Telemetry](../../main-view/reset.md)[ ](../../main-view/reset.md)or Flight function will reset this value to 0.
{% endhint %}