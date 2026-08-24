# Use Bluetooth with EdgeTX

The support for Bluetooth in EdgeTX is limited to:

* Bluetooth Trainer Mode
* Bluetooth Telemetry Streaming

The following Bluetooth options are **not** supported.

* Bluetooth Audio
* Wireless file access and transfers
* Bluetooth joystick

### Firmware

To use Bluetooth, you will need a custom compiled version of EdgeTX that needs to be built with the **BLUETOOTH=YES** CMake flag. You can create customized versions of EdgeTX using the CloudBuild tab on the[ EdgeTX Buddy website](https://buddy.edgetx.org/).

Once the correct version of EdgeTX firmware is installed in your radio, the Bluetooth configuration options will be available on the **Hardware** page of **Radio** Settings.

### Hardware

The only off-the-shelf bluetooth modules supported by EdgeTX are:&#x20;

[FrSky Bluetooth Module](https://de.aliexpress.com/item/4001192317700.html?gatewayAdapt=glo2deu)

[FrSky ACCESS PARA Wireless Module](https://www.horusrc.com/en/frsky-horus-x10-para-wireless-module.html)

You can also create your own Bluetooth module by purchasing an ESP32 development kit and flashing it with the firmware from following project:[ https://btwifimod.gitbook.io/untitled/getting-started/hardware](https://btwifimod.gitbook.io/untitled/getting-started/hardware)

### Telemetry Applications

The [INAV Telemetry Viewer app](https://play.google.com/store/apps/details?id=crazydude.com.telemetry) can be used on your Android smartphone to view your telemetry data over bluetooth.

### Other Important Notes:

* Bluetooth is only supported on radios that have at least one AUX serial port.
* The compile time option **Bluetooth** will reserve one AUX port (on radios with 2 AUX ports, AUX2 is reserved for Bluetooth) and it will NOT be available in the normal user interface for other purposes.
* EdgeTX Bluetooth trainer or telemetry has nothing to do with internal or external RF module Bluetooth functionality.
* EdgeTX Bluetooth can NOT be used for Bluetooth joystick functionality at the moment.
