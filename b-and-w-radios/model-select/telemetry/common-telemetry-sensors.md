# Common Telemetry Sensors

The following sensors are commonly used and normal automatically detected by EdgeTX:

| Name | Description                               | Data source               |
| ---- | ----------------------------------------- | ------------------------- |
| 1RSS | Received signal strength antenna 1 (RSSI) | Receiver                  |
| 2RSS | Received signal strength antenna 2 (RSSI) | Receiver                  |
| Rqly | Receiver link quality (valid packets)     | Receiver                  |
| RSNR | Receiver signal-to-noise ratio            | Receiver                  |
| RFMD | Receiver packet rate                      | Receiver                  |
| TPWR | Transmitter transmitting power            | Transmitter               |
| TRSS | Transmitter signal strength antenna       | Transmitter               |
| TQly | Transmitter link quality (valid packets)  | Transmitter               |
| TSNR | Transmitter signal-to-noise ratio         | Transmitter               |
| ANT  | Sensor for debugging only                 | Transmitter               |
| GPS  | GPS Coordinates                           | GPS / Flight Controller   |
| Alt  | GPS Altitudes                             | GPS / Flight Controller   |
| Sats | GPS Satellites acquired                   | GPS / Flight Controller   |
| Hdg  | Magnetic orientation                      | GPS / Flight Controller   |
| RXBt | Battery voltage                           | Flight Controller         |
| Curr | Current draw                              | Flight Controller         |
| Capa | Current consumption                       | Flight Controller         |
| Ptch | FC Pitch angle                            | Flight Controller         |
| Roll | FC Roll angle                             | Flight Controller         |
| Yaw  | FC Yaw angle                              | Flight Controller         |
| FM   | Flight mode                               | Flight Controller         |
| VSPD | Vertical Speed                            | Flight Controller w/ Baro |
