# Configure Advanced Joystick with EdgeTX

### General

1. Please try the **classic mode first**. Handling joystick input has undergone many different designs. For example Windows has 6 joystick APIs - all with different quirks.
2. **Interface mode Gamepad** is usually the right one.
3. To ease switching between Advanced and Classic mode try using **channels 1 - 8 for axis** and **channels 9 - 32 for buttons**.
4. After **changing the joystick** configuration you likely have to disconnect and then reconnect the USB cable. Otherwise systems might still use the old joystick description to read the new data.

### Analog Axis

1. Most modern applications use the **USB HID ID** to identify the meaning of an axis.
2. Legacy applications frequently use the **order** the axis where configured in.
3. A few applications use the **reverse order** the axis where configured in.
4. **Duplicate axis** are rarely supported. Some APIs do support two Slider axis.
5. **Inverted axis**: Many applications expect the left and right Y axis to go the other way. The direction can be reversed with Weight -100% or in the advanced Joystick configuration.
6. **Windows** does support "axis" and "sim". However mixing both types is not always supported.
7. **Linux** maps following inputs onto the same axis and uses the input value with the lowest channel number.
   * sim Thr + axis Slider → ABS\_THROTTLE
   * sim Rud + axis Dial → ABS\_RUDDER
   * axis Wheel + sim Steer → ABS\_WHEEL
8. **Android** treats **sim Acc** and **sim Brk** as half axis. EdgeTX channel outputs \[-100%, 0% and +100%] are interpreted by Android as \[0%, 50% and 100%]. Consider following configuration if your physical input is one analog stick:
   * sim Acc = input (axis 1: Offset -50%, Func "x>0") mixed with (Weight 200%)
   * sim Brk = input (axis 1: Offset -50%, Func "x<0") mixed with (Weight -200%)

#### Common Axis Mapping

| channel | Android   | Betaflight  | Dualsense | EdgeTX Classic | EdgeTX pre 2.9 |
| ------- | --------- | ----------- | --------- | -------------- | -------------- |
| CH1     | axis X    | axis X      | axis X    | axis X         | axis X         |
| CH2     | axis Y    | axis Y      | axis Y    | axis Y         | axis Y         |
| CH3     | axis Z    | axis Z      | axis Z    | axis Z         | axis Z         |
| CH4     | axis rotZ | axis rotX   | axis rotZ | axis rotX      | axis rotX      |
| CH5     | sim Brk   | axis rotZ   | axis rotX | axis rotY      | axis rotY      |
| CH6     | sim Acc   | axis rotY   | axis rotY | axis rotZ      | axis rotZ      |
| CH7     |           | axis Slider |           | axis Slider    | axis Slider    |
| CH8     | sim Dpad  | axis Dial   | sim Dpad  | axis Dial      | axis Slider    |

Similar layouts:

| other controller | use layout     |
| ---------------- | -------------- |
| OpenTX           | EdgeTX pre 2.9 |
| Orqa FPV.Ctrl    | EdgeTX pre 2.9 |
| Stadia           | Android        |
| XBox             | Android        |

#### sim Dpad

Sim Dpad emulates a **directional pad** also known as **hat switch** or point of view switch. Most application decode the 8 ordinal directions and "center". Some applications only decode the 4 cardinal directions and "center" (e.g. Northeast is treated as North).

| direction  | from    | to     |
| ---------- | ------- | ------ |
| North      | -100.0% | -88.1% |
| Northeast  | -88.0%  | -76.4% |
| East       | -76.3%  | -64.6% |
| Southeast  | -64.6%  | -52.9% |
| South      | -52.8%  | -41.2% |
| Southwest  | -41.1%  | -29.5% |
| West       | -29.4%  | -17.8% |
| Northwest  | -17.7%  | -6.1%  |
| **Center** | -6.0%   | 5.7%   |
| North      | 5.8%    | 17.4%  |
| Northeast  | 17.5%   | 29.1%  |
| East       | 29.2%   | 40.8%  |
| Southeast  | 40.9%   | 52.5%  |
| South      | 52.6%   | 64.3%  |
| Southwest  | 64.4%   | 76.0%  |
| West       | 76.1%   | 87.7%  |
| Northwest  | 87.8%   | 100.0% |

#### Axis IDs

| EdgeTX      | HID name    | USB HID ID |
| ----------- | ----------- | ---------- |
| axis X      | X           | 0x00010030 |
| axis Y      | Y           | 0x00010031 |
| axis Z      | Z           | 0x00010032 |
| axis rotX   | Rx          | 0x00010033 |
| axis rotY   | Ry          | 0x00010034 |
| axis rotZ   | Rz          | 0x00010035 |
| axis Slider | Slider      | 0x00010036 |
| axis Dial   | Dial        | 0x00010037 |
| axis Wheel  | Wheel       | 0x00010038 |
| sim Ail     | Aileron     | 0x000200B0 |
| sim Ele     | Elevator    | 0x000200B8 |
| sim Rud     | Rudder      | 0x000200BA |
| sim Thr     | Throttle    | 0x000200BB |
| sim Acc     | Accelerator | 0x000200C4 |
| sim Brk     | Brake       | 0x000200C5 |
| sim Steer   | Steering    | 0x000200C8 |
| sim Dpad    | Hat switch  | 0x00010039 |

### Buttons

1. Buttons are **identified** by their USB HID ID.
2. The **meaning** of a specific button ID is not standardized.
3. **Duplicate buttons** (_e.g. button 1, button 1_) are not supported. The button with the higher channel number is used.
4. **Buttons as axis**: Some applications need analog button information. Use a mixer to forward the digital button state to an analog axis.
5. **Ghost buttons**: For Joysticks and Gamepads the required minimum amount of buttons is automatically created. Similarly if only button 15 is configured the missing buttons 0 - 14 are automatically created. These buttons have no input and are always off.
6. **Android** generally supports buttons 0 to 14 with the same mapping as Linux. Support for buttons in bold is [mandatory](https://source.android.com/docs/compatibility/14/android-14-cdd#7261\_button\_mappings) for all Android devices.
7. **Widows** generally supports buttons 0 to 9 with the same mapping as Xbox.

| EdgeTX    | **Android** / Linux         | Dualsense | **Windows** / XBox | USB HID ID |
| --------- | --------------------------- | --------- | ------------------ | ---------- |
| button 0  | **BTN\_A** - 304            | square    | **A**              | 0x00090001 |
| button 1  | **BTN\_B** - 305            | cross     | **B**              | 0x00090002 |
| button 2  | BTN\_C - 305                | circle    | **X**              | 0x00090003 |
| button 3  | **BTN\_X** - 307            | triangle  | **Y**              | 0x00090004 |
| button 4  | **BTN\_Y** - 308            | L1        | **left bumper**    | 0x00090005 |
| button 5  | BTN\_Z - 309                | R1        | **right bumper**   | 0x00090006 |
| button 6  | **BTN\_TL** - 310           | L2        | **back**           | 0x00090007 |
| button 7  | **BTN\_TR** - 311           | R2        | **start**          | 0x00090008 |
| button 8  | BTN\_TL2 - 312              | create    | **left stick**     | 0x00090009 |
| button 9  | BTN\_TR2 - 313              | options   | **right stick**    | 0x0009000A |
| button 10 | BTN\_SELECT - 314           | L3        | left trigger       | 0x0009000B |
| button 11 | BTN\_START - 315            | R3        | right trigger      | 0x0009000C |
| button 12 | BTN\_MODE - 316             | home      | guide              | 0x0009000D |
| button 13 | **BTN\_THUMBL** - 317       | touchpad  |                    | 0x0009000E |
| button 14 | **BTN\_THUMBR** - 318       | mute      |                    | 0x0009000F |
| button 15 |                             |           |                    | 0x00090010 |
| button 16 | BTN\_TRIGGER\_HAPPY1 - 704  |           |                    | 0x00090011 |
| button 17 | BTN\_TRIGGER\_HAPPY2 - 705  |           |                    | 0x00090012 |
| button 18 | BTN\_TRIGGER\_HAPPY3 - 706  |           |                    | 0x00090013 |
| button 19 | BTN\_TRIGGER\_HAPPY4 - 708  |           |                    | 0x00090014 |
| button 20 | BTN\_TRIGGER\_HAPPY5 - 709  |           |                    | 0x00090015 |
| button 21 | BTN\_TRIGGER\_HAPPY6 - 710  |           |                    | 0x00090016 |
| button 22 | BTN\_TRIGGER\_HAPPY7 - 711  |           |                    | 0x00090017 |
| button 23 | BTN\_TRIGGER\_HAPPY8 - 712  |           |                    | 0x00090018 |
| button 24 | BTN\_TRIGGER\_HAPPY9 - 713  |           |                    | 0x00090019 |
| button 25 | BTN\_TRIGGER\_HAPPY10 - 714 |           |                    | 0x0009001A |
| button 26 | BTN\_TRIGGER\_HAPPY11 - 715 |           |                    | 0x0009001B |
| button 27 | BTN\_TRIGGER\_HAPPY12 - 716 |           |                    | 0x0009001C |
| button 28 | BTN\_TRIGGER\_HAPPY13 - 717 |           |                    | 0x0009001D |
| button 29 | BTN\_TRIGGER\_HAPPY14 - 718 |           |                    | 0x0009001E |
| button 30 | BTN\_TRIGGER\_HAPPY15 - 719 |           |                    | 0x0009001F |
| button 31 | BTN\_TRIGGER\_HAPPY16 - 720 |           |                    | 0x00090020 |
