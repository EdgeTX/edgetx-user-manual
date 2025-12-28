---
description: Model Independent and Model Dependent audio!
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/2n2y0XsJcrhXt3asceP0/edgetx-how-to/advanced-audio-features
---

# Advanced Audio Features

## Model Independent

These are sounds that are not special to any specific model, and are located in `/SOUNDS/language` and `/SOUNDS/language/SYSTEM` on your radio's SD card/on-board storage when correctly configured.&#x20;

The files in `/SOUNDS/language/SYSTEM` are automatically played by the radio in response to specific events, such as turning the radio on, telemetry being lost, switches being in the wrong position, etc.&#x20;

You can also add `Play Track` Global Functions that will play in response to whatever trigger condition you wish.&#x20;

## Model Dependent

These are sounds that are specific to a  given model, and are located in `/SOUNDS/language` and `/SOUNDS/language/model_name` on your radio's SD card/on-board storage when correctly configured.\
\
The files in `/SOUNDS/language` are available for use with Play Track Special Functions, and will play in response to whatever trigger condition you configure.

In addition to the `Play Track` Special Function, there is also the ability to configure audio be played by simply placing audio files into a directory with the same name as the model.&#x20;

For example, for English, with a model named `Ruxus 5`, you would create a folder named `/SOUNDS/en/Ruxus_5/` (note the need to replace spaces with underscores).&#x20;

Then, just create/copy audio files (of the correct format!) for any of the following trigger events into that folder.&#x20;

### Model Load

Will be played after the startup switch checks are completed when turning the radio on or when switching to the configured model.&#x20;

Filename: `name.wav`&#x20;

### Switches

Played on change of switch position.

Filename structure: `switchID-position.wav`

* `SA-up.wav`
* `SA-mid.wav` (if position present)
* `SA-down.wav`

### Multi-position / Stepped Switches

Played on change of switch position.

Filename structure (hyphens added for clarity): `P-switchNumber-position.wav`

* `P11.wav`  (Pot 1, position 1)
* `P16.wav`  (Pot 1, position 6)

### Logical Switches

Played when the logical switch changes state.

Filename structure: `switchID-condition.wav`

* `L1-up.wav` (true)
* `L1-down.wav` (false)

### Flight Modes

Played on entering or exiting flight mode.&#x20;

Filename structure: `modeName-condition.wav` (Note: No spaces in the flight mode name)

* `ABC–off.wav`
* `ABC–on.wav`



