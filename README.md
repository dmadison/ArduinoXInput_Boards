# Arduino XInput Boards Packages

This repository contains board packages for the Arduino XInput project.

## Upload Warning

Due to the nature of how the XInput USB mode works, Arduinos that have XInput sketches on them will ***not*** automatically reset when programmed over USB! You will need to reset the board by hand every time you upload new code. If you do not know how to reset your board you may be unable to reprogram it.

Please read the ["How to Upload"](https://github.com/dmadison/ArduinoXInput_AVR#how-to-upload) section on the AVR core repository for further instructions.

## Installation

Follow the official instructions for [adding third party boards](https://support.arduino.cc/hc/en-us/articles/360016466340-Add-or-remove-third-party-boards-in-Boards-Manager) and [adding boards to the Arduino IDE](https://support.arduino.cc/hc/en-us/articles/360016119519-Add-boards-to-Arduino-IDE).

Add the following line to the "Additional Boards Manager URLs" list:
```
https://raw.githubusercontent.com/dmadison/ArduinoXInput_Boards/master/package_dmadison_xinput_index.json
```

If you've done this correctly, the XInput boards packages will be available within the Boards Manager.

## Available Packages

There are two packages available:

* #### [XInput AVR Boards](https://www.github.com/dmadison/ArduinoXInput_AVR)
  Modifies the Arduino AVR core to emulate an XInput device. Includes support for the Arduino Leonardo, Micro, Yun, and more.

* #### [XInput SparkFun Boards](https://www.github.com/dmadison/ArduinoXInput_SparkFun)
  Provides support for the MaKey MaKey, Pro Micro, Fio, Qduino Mini, and LilyPad USB Plus. Requires the XInput AVR Core boards.

Please note that the Arduino IDE does not currently have a way to mark platform packages as dependencies. In order to use the SparkFun boards package you **must** install the XInput AVR Boards as well.
