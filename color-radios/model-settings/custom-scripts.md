---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/2n2y0XsJcrhXt3asceP0/color-radios/model-settings/custom-scripts
---

# Custom Scripts

<figure><img src="../../.gitbook/assets/color_model_custom-lua.png" alt=""><figcaption><p>Custom Mixer Scripts</p></figcaption></figure>

Custom (Mixes) Scripts take one or more values as inputs, do some processing in Lua code, and output one or more values. Each model can have several Mixes Scripts associated with it, and these scripts are run periodically. They behave similarly to standard EdgeTX mixers, but at the same time they provide a much more flexible and powerful tool.

Typical use cases:

* replacement for complex mixes that are _not critical_ to model function
* complex processing of inputs and reaction to their current state and/or their history
* filtering of telemetry values

{% hint style="warning" %}
If the script output is used as a `mixer source` , and the **script is killed** for whatever reason, then _the_ **whole mixer line is disabled**! Exercise caution when using them for primary controls. It is advisable to have a fallback mixer line, that will be used if for whatever reason the Mixer Script is terminated.
{% endhint %}

<figure><img src="../../.gitbook/assets/color_model_custom-lua_edit.png" alt=""><figcaption><p>Inputs and Outputs for Mixer Scripts</p></figcaption></figure>

Here is an example of mixer script that accepts a source and constant value, and has two outputs that will be selectable in the mixer as sources.

Selecting an empty line lets you pick a **Script/File** from `/SCRIPTS/MIXES/` on the SD card and give it a **Name**. Once selected, the **Inputs** and **Outputs** the script defines are listed automatically and can be configured (inputs can be set to a source, constant, or other value; outputs are named per the script). Long-pressing an existing script line gives **Edit** and **Delete** options. A script line shows a status indicator if there's a **Script Error** or if its file is missing (**Needs File**).
