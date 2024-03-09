# Joystick Information for Game Developers


1. EdgeTX can output joystick / gamepad information via USB HID with ID (VID_1209&PID_4F54 / 1209:4F54).
2. EdgeTX performs configurable input processing including dead bands, mixing, and non-linear scaling.
3. A wide variety of [controllers](https://edgetx.org/supportedradios/) run EdgeTX. By default all devices output the same "Classic Joystick" report format with 8 11-bit analog axis and 24 digital buttons.


## Linux: evdev

Linux's [evdev API](https://www.kernel.org/doc/html/latest/input/input.html) uses **open** (fcntl.h) with **/dev/input/event**[...] and **read** (unistd.h) to read **input_event** (linux/joystick.h).

### identity

1. EVIOCGID : device_id.vendor is 4617 / 0x1209
2. EVIOCGID : device_id.product is 20308 / 0x4F54

### input labels

| EdgeTX | event name        | event code
| -      | -                 | -
| CH1    | ABS_X             | EV_ABS 0
| CH2    | ABS_Y             | EV_ABS 1
| CH3    | ABS_Z             | EV_ABS 2
| CH4    | ABS_RX            | EV_ABS 3
| CH5    | ABS_RY            | EV_ABS 4
| CH6    | ABS_RZ            | EV_ABS 5
| CH7    | ABS_THROTTLE      | EV_ABS 6
| CH8    | ABS_RUDDER        | EV_ABS 7
| CH9    | BTN_SOUTH         | EV_KEY 304 / 0x130
| CH10   | BTN_EAST          | EV_KEY 305 / 0x131
| CH11   | BTN_C             | EV_KEY 306 / 0x132
| CH12   | BTN_NORTH         | EV_KEY 307 / 0x133
| CH13   | BTN_WEST          | EV_KEY 308 / 0x134
| CH14   | BTN_Z             | EV_KEY 309 / 0x135
| CH15   | BTN_TL            | EV_KEY 310 / 0x136
| CH16   | BTN_TR            | EV_KEY 311 / 0x137
| CH17   | BTN_TL2           | EV_KEY 312 / 0x138
| CH18   | BTN_TR2           | EV_KEY 313 / 0x139
| CH19   | BTN_SELECT        | EV_KEY 314 / 0x13A
| CH20   | BTN_START         | EV_KEY 315 / 0x13B
| CH21   | BTN_MODE          | EV_KEY 316 / 0x13C
| CH22   | BTN_THUMBL        | EV_KEY 317 / 0x13D
| CH23   | BTN_THUMBR        | EV_KEY 318 / 0x13E
| CH24   | (no name)         | EV_KEY 319 / 0x13F
| CH25   | BTN_TRIGGER_HAPPY1| EV_KEY 704 / 0x2C0
| CH26   | BTN_TRIGGER_HAPPY2| EV_KEY 705 / 0x2C1
| CH27   | BTN_TRIGGER_HAPPY3| EV_KEY 706 / 0x2C2
| CH28   | BTN_TRIGGER_HAPPY4| EV_KEY 707 / 0x2C3
| CH29   | BTN_TRIGGER_HAPPY5| EV_KEY 708 / 0x2C4
| CH30   | BTN_TRIGGER_HAPPY6| EV_KEY 709 / 0x2C5
| CH31   | BTN_TRIGGER_HAPPY7| EV_KEY 710 / 0x2C6
| CH32   | BTN_TRIGGER_HAPPY8| EV_KEY 711 / 0x2C7


## Linux: joystick

Linux's [joystick API](https://www.kernel.org/doc/html/latest/input/joydev/index.html) uses **open** (fcntl.h) with **/dev/input/js** and **read** (unistd.h) to read **js_event** (linux/joystick.h).

### identity

JSIOCGNAME is "EdgeTX [...] Joystick" or "OpenTX [...] Joystick". The middle part ("[...]") is device specific.

### input labels

| EdgeTX  | read js_event
| -       | -
| CH1     | JS_EVENT_AXIS 0
| CH2     | JS_EVENT_AXIS 1
| [...]   | [...]
| CH8     | JS_EVENT_AXIS 7
| CH9     | JS_EVENT_BUTTON 0
| CH10    | JS_EVENT_BUTTON 1
| [...]   | [...]
| CH32    | JS_EVENT_BUTTON 23


## Windows: DirectInput

Windows's [DirectInput](https://learn.microsoft.com/en-us/previous-versions/windows/desktop/ee416842(v=vs.85)) uses IDirectInputDevice8::**GetDeviceState** to read **DIJOYSTATE** (dinput.h). DIJOYSTATE2 (c_dfDIJoystick2) outputs the same information.

### identity

DIDEVICEINSTANCE.guidProduct starts with "4F541209-". The trailing part of the GUID is device specific.

### input labels

| EdgeTX | DIJOYSTATE
| -      | -
| CH1    | lX
| CH2    | lY
| CH3    | lZ
| CH4    | lRx
| CH5    | lRy
| CH6    | lRz
| CH7    | rglSlider[1]
| CH8    | rglSlider[0]
| CH9    | rgbButtons[0]
| CH10   | rgbButtons[1]
| [...]  | [...]
| CH32   | rgbButtons[23]


## Windows: Multimedia

Windows' [Multimedia API](https://learn.microsoft.com/en-us/windows/win32/api/joystickapi/) uses **joyGetPosEx** to read **JOYINFOEX** (joystickapi.h). The older joyGetPos / JOYINFO only support CH1-CH3 and CH9-CH32 with the same mapping as the newer JOYINFOEX.

### identity

1. JOYCAPS.wMid is 4617 / 0x1209
2. JOYCAPS.wPid is 20308 / 0x4F54

### input labels

| EdgeTX | JOYINFOEX
| -      | -
| CH1    | dwXpos
| CH2    | dwYpos
| CH3    | dwZpos
| CH4    | dwVpos
| CH5    | (not available)
| CH6    | dwRpos
| CH7    | dwUpos
| CH8    | (not available)
| CH9    | dwButtons & 0x000001
| CH10   | dwButtons & 0x000002
| CH11   | dwButtons & 0x000004
| [...]  | [...]
| CH32   | dwButtons & 0x800000


## Windows: Raw Input

Windows' [Raw Input API](https://learn.microsoft.com/en-us/windows/win32/inputdev/about-raw-input) uses **GetRawInputData** (WinUser.h), **HidP_GetUsageValue** and **HidP_GetUsages** (hidpi.h).

### identity

1. RID_DEVICE_INFO_HID.dwVendorId is 4617 / 0x1209
2. RID_DEVICE_INFO_HID.dwProductId is 20308 / 0x4F54

### input labels

| EdgeTX | HidP_Get[...]Value | UsagePage | Usage
| -      | -                       | -    | -
| CH1    | HidP_GetValueCaps [7]   | 0x01 | 0x30
| CH2    | HidP_GetValueCaps [6]   | 0x01 | 0x31
| CH3    | HidP_GetValueCaps [5]   | 0x01 | 0x32
| CH4    | HidP_GetValueCaps [4]   | 0x01 | 0x33
| CH5    | HidP_GetValueCaps [3]   | 0x01 | 0x34
| CH6    | HidP_GetValueCaps [2]   | 0x01 | 0x35
| CH7    | HidP_GetValueCaps [1]   | 0x01 | 0x36
| CH8    | HidP_GetValueCaps [0]   | 0x01 | 0x37
| CH9    | HidP_GetButtonCaps [0]  | 0x09 | 0x01
| CH10   | HidP_GetButtonCaps [0]  | 0x09 | 0x02
| [...]  | [...]                   | [...]| [...]
| CH32   | HidP_GetButtonCaps [0]  | 0x09 | 0x18


## Windows: Windows.Gaming.Input

Windows' [RawGameController](https://learn.microsoft.com/en-us/uwp/api/windows.gaming.input.rawgamecontroller) uses **winrt::Windows::Gaming::Input::RawGameController** (winrt/Windows.Gaming.Input.h).

### identity

1. RawGameController::HardwareVendorId is 4617 / 0x1209
2. RawGameController::HardwareProductId is 20308 / 0x4F54

### input labels

| EdgeTX | GetCurrentReading
| -      | -
| CH1    | axisArray[0]
| CH2    | axisArray[1]
| [...]  | [...]
| CH8    | axisArray[7]
| CH9    | buttonArray[0]
| CH10   | buttonArray[1]
| [...]  | [...]
| CH32   | buttonArray[23]
