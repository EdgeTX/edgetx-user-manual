# Joystick Mapping Information for Game Developers

### General

1. EdgeTX can output joystick / gamepad information via USB HID with ID (VID\_1209\&PID\_4F54 / 1209:4F54).
2. EdgeTX performs configurable input processing including dead bands, mixing, and non-linear scaling.
3. A wide variety of [controllers](https://edgetx.org/supportedradios/) run EdgeTX. By default all devices output the same "Classic Joystick" report format with 8 analog axis and 24 digital buttons.
4. Buttons are digital (0 = off, 1 = on).
5. Analog axis have 11 bit resoultion.

### Linux: evdev

Linux's [evdev API](https://www.kernel.org/doc/html/latest/input/input.html) uses **open** (fcntl.h) with **/dev/input/event**\[...] and **read** (unistd.h) to read **input\_event** (linux/joystick.h).

#### identity

1. EVIOCGID : device\_id.vendor is 4617 / 0x1209
2. EVIOCGID : device\_id.product is 20308 / 0x4F54

#### input labels

| EdgeTX | event name           | event code          |
| ------ | -------------------- | ------------------- |
| CH1    | ABS\_X               | EV\_ABS 0           |
| CH2    | ABS\_Y               | EV\_ABS 1           |
| CH3    | ABS\_Z               | EV\_ABS 2           |
| CH4    | ABS\_RX              | EV\_ABS 3           |
| CH5    | ABS\_RY              | EV\_ABS 4           |
| CH6    | ABS\_RZ              | EV\_ABS 5           |
| CH7    | ABS\_THROTTLE        | EV\_ABS 6           |
| CH8    | ABS\_RUDDER          | EV\_ABS 7           |
| CH9    | BTN\_SOUTH           | EV\_KEY 304 / 0x130 |
| CH10   | BTN\_EAST            | EV\_KEY 305 / 0x131 |
| CH11   | BTN\_C               | EV\_KEY 306 / 0x132 |
| CH12   | BTN\_NORTH           | EV\_KEY 307 / 0x133 |
| CH13   | BTN\_WEST            | EV\_KEY 308 / 0x134 |
| CH14   | BTN\_Z               | EV\_KEY 309 / 0x135 |
| CH15   | BTN\_TL              | EV\_KEY 310 / 0x136 |
| CH16   | BTN\_TR              | EV\_KEY 311 / 0x137 |
| CH17   | BTN\_TL2             | EV\_KEY 312 / 0x138 |
| CH18   | BTN\_TR2             | EV\_KEY 313 / 0x139 |
| CH19   | BTN\_SELECT          | EV\_KEY 314 / 0x13A |
| CH20   | BTN\_START           | EV\_KEY 315 / 0x13B |
| CH21   | BTN\_MODE            | EV\_KEY 316 / 0x13C |
| CH22   | BTN\_THUMBL          | EV\_KEY 317 / 0x13D |
| CH23   | BTN\_THUMBR          | EV\_KEY 318 / 0x13E |
| CH24   | (no name)            | EV\_KEY 319 / 0x13F |
| CH25   | BTN\_TRIGGER\_HAPPY1 | EV\_KEY 704 / 0x2C0 |
| CH26   | BTN\_TRIGGER\_HAPPY2 | EV\_KEY 705 / 0x2C1 |
| CH27   | BTN\_TRIGGER\_HAPPY3 | EV\_KEY 706 / 0x2C2 |
| CH28   | BTN\_TRIGGER\_HAPPY4 | EV\_KEY 707 / 0x2C3 |
| CH29   | BTN\_TRIGGER\_HAPPY5 | EV\_KEY 708 / 0x2C4 |
| CH30   | BTN\_TRIGGER\_HAPPY6 | EV\_KEY 709 / 0x2C5 |
| CH31   | BTN\_TRIGGER\_HAPPY7 | EV\_KEY 710 / 0x2C6 |
| CH32   | BTN\_TRIGGER\_HAPPY8 | EV\_KEY 711 / 0x2C7 |

### Linux: joystick

Linux's [joystick API](https://www.kernel.org/doc/html/latest/input/joydev/index.html) uses **open** (fcntl.h) with **/dev/input/js** and **read** (unistd.h) to read **js\_event** (linux/joystick.h).

#### identity

JSIOCGNAME is "EdgeTX \[...] Joystick" or "OpenTX \[...] Joystick". The middle part ("\[...]") is device specific.

#### input labels

| EdgeTX | read js\_event       |
| ------ | -------------------- |
| CH1    | JS\_EVENT\_AXIS 0    |
| CH2    | JS\_EVENT\_AXIS 1    |
| \[...] | \[...]               |
| CH8    | JS\_EVENT\_AXIS 7    |
| CH9    | JS\_EVENT\_BUTTON 0  |
| CH10   | JS\_EVENT\_BUTTON 1  |
| \[...] | \[...]               |
| CH32   | JS\_EVENT\_BUTTON 23 |

### Windows: DirectInput

Windows's [DirectInput](https://learn.microsoft.com/en-us/previous-versions/windows/desktop/ee416842\(v=vs.85\)) uses IDirectInputDevice8::**GetDeviceState** to read **DIJOYSTATE** (dinput.h). DIJOYSTATE2 (c\_dfDIJoystick2) outputs the same information.

#### identity

DIDEVICEINSTANCE.guidProduct starts with "4F541209-". The trailing part of the GUID is device specific.

#### input labels

| EdgeTX | DIJOYSTATE      |
| ------ | --------------- |
| CH1    | lX              |
| CH2    | lY              |
| CH3    | lZ              |
| CH4    | lRx             |
| CH5    | lRy             |
| CH6    | lRz             |
| CH7    | rglSlider\[1]   |
| CH8    | rglSlider\[0]   |
| CH9    | rgbButtons\[0]  |
| CH10   | rgbButtons\[1]  |
| \[...] | \[...]          |
| CH32   | rgbButtons\[23] |

### Windows: Multimedia

Windows' [Multimedia API](https://learn.microsoft.com/en-us/windows/win32/api/joystickapi/) uses **joyGetPosEx** to read **JOYINFOEX** (joystickapi.h). The older joyGetPos / JOYINFO only support CH1-CH3 and CH9-CH32 with the same mapping as the newer JOYINFOEX.

#### identity

1. JOYCAPS.wMid is 4617 / 0x1209
2. JOYCAPS.wPid is 20308 / 0x4F54

#### input labels

| EdgeTX | JOYINFOEX            |
| ------ | -------------------- |
| CH1    | dwXpos               |
| CH2    | dwYpos               |
| CH3    | dwZpos               |
| CH4    | dwVpos               |
| CH5    | (not available)      |
| CH6    | dwRpos               |
| CH7    | dwUpos               |
| CH8    | (not available)      |
| CH9    | dwButtons & 0x000001 |
| CH10   | dwButtons & 0x000002 |
| CH11   | dwButtons & 0x000004 |
| \[...] | \[...]               |
| CH32   | dwButtons & 0x800000 |

### Windows: Raw Input

Windows' [Raw Input API](https://learn.microsoft.com/en-us/windows/win32/inputdev/about-raw-input) uses **GetRawInputData** (WinUser.h), **HidP\_GetUsageValue** and **HidP\_GetUsages** (hidpi.h).

#### identity

1. RID\_DEVICE\_INFO\_HID.dwVendorId is 4617 / 0x1209
2. RID\_DEVICE\_INFO\_HID.dwProductId is 20308 / 0x4F54

#### input labels

| EdgeTX | HidP\_Get\[...]Value     | UsagePage | Usage  |
| ------ | ------------------------ | --------- | ------ |
| CH1    | HidP\_GetValueCaps \[7]  | 0x01      | 0x30   |
| CH2    | HidP\_GetValueCaps \[6]  | 0x01      | 0x31   |
| CH3    | HidP\_GetValueCaps \[5]  | 0x01      | 0x32   |
| CH4    | HidP\_GetValueCaps \[4]  | 0x01      | 0x33   |
| CH5    | HidP\_GetValueCaps \[3]  | 0x01      | 0x34   |
| CH6    | HidP\_GetValueCaps \[2]  | 0x01      | 0x35   |
| CH7    | HidP\_GetValueCaps \[1]  | 0x01      | 0x36   |
| CH8    | HidP\_GetValueCaps \[0]  | 0x01      | 0x37   |
| CH9    | HidP\_GetButtonCaps \[0] | 0x09      | 0x01   |
| CH10   | HidP\_GetButtonCaps \[0] | 0x09      | 0x02   |
| \[...] | \[...]                   | \[...]    | \[...] |
| CH32   | HidP\_GetButtonCaps \[0] | 0x09      | 0x18   |

### Windows: Windows.Gaming.Input

Windows' [RawGameController](https://learn.microsoft.com/en-us/uwp/api/windows.gaming.input.rawgamecontroller) uses **winrt::Windows::Gaming::Input::RawGameController** (winrt/Windows.Gaming.Input.h).

#### identity

1. RawGameController::HardwareVendorId is 4617 / 0x1209
2. RawGameController::HardwareProductId is 20308 / 0x4F54

#### input labels

| EdgeTX | GetCurrentReading |
| ------ | ----------------- |
| CH1    | axisArray\[0]     |
| CH2    | axisArray\[1]     |
| \[...] | \[...]            |
| CH8    | axisArray\[7]     |
| CH9    | buttonArray\[0]   |
| CH10   | buttonArray\[1]   |
| \[...] | \[...]            |
| CH32   | buttonArray\[23]  |
