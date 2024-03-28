# Pre-start Checks

<figure><img src="../../../.gitbook/assets/prestart checks.png" alt=""><figcaption><p>Pre-start Checks page</p></figcaption></figure>

Whenever a new model is loaded, EdgeTX will conduct pre-flight checks based on the checks that are configured on this page. If any of the checks are failed, EdgeTX will give the user an audio and visual warning that must be acknowledged before using the model. The following preflight checks are configurable:

**Display checklist** - When this option is selected, the model notes file will be displayed when the model is loaded. A valid model notes file must be in the **Models** folder on the SD card. The model notes file must be a .txt file and must have the EXACT same name as the model it is for, for example: Mobula6.txt. The text in the file is up to the user.

**Interactive checklist** - This option is used with the **Display checklist** option. When this option is selected, any line of text in the checklist file that begins with = will display as a check box when the checklist is displayed. All displayed checkboxes must be **checked** by selecting them in order to close the checklist.

**Throttle state** - When selected, the radio will check that the throttle is at the minimum range value for the configured throttle source in the [Throttle](throttle.md) menu.

**Custom Position?** - When this option is selected, a number box will be shown that can be configured with a user-defined value for the throttle state check. &#x20;

**Switches** - The section displays all the switches that are configured on the radio and allows you to select which position is the correct position for the switch state check. Selecting the switch will cycle through the available switch positions or turn the check off for the switch completely. Yellow switches have the switch position check activated. White switches e de-activated.

**Pots & Sliders**- When activated, this option checks the position of the pots & sliders. There are three options - OFF, ON and AUTO. When ON or AUTO is selected from the drop-down menu, buttons for the available pots and sliders will appear.&#x20;

* **OFF** - Pot and slider positions are not checked.
* **ON** - Positions are checked against manually configured pot and slider positions that are set to active (yellow). To manually set the check position, select ON from the drop-down menu, put the pots and sliders into the desired position, and activate them by selecting them (yellow).
* **AUTO** - Positions are checked for activated pots and sliders and compared to the last automatically saved position before the radio was turned off or the model was changed.

**Center Beep** - Allows you to turn on / off the center beep function for the individual sticks, pots, and sliders by selecting them (yellow).&#x20;
