# Elite-C Board w/XInput

This repository contains support for the Elite-C MCU board (Pro Micro clone), modified to work as an XInput device.

This boards package is meant to be used in conjunction with the [ArduinoXInput library](https://github.com/dmadison/ArduinoXInput).

## Included Boards

* [Elite-C](https://deskthority.net/wiki/Elite-C)

## Installation

<pre>
└───Arduino Installation
	├───drivers
	├───examples
	├───hardware
	│   ├───arduino
	│   ├───tools
	│   ├───<b>xinput</b>
	│   └───<b>xinput_elitec
	│       └───avr
	│           └───variants</b>
	├───java
	├───lib
	├───libraries
	├───reference
	├───tools
	└───tools-builder
</pre>

To install, you first need to install the latest version of the Arduino XInput AVR Core, [which can be found here](https://github.com/dmadison/ArduinoXInput_AVR). Follow [the installation instructions](https://github.com/dmadison/ArduinoXInput_AVR/#installation) provided in that repository and verify that those boards are installed correctly before proceeding.

This boards package uses the same process for installation. Download [the latest version](../../releases/latest) of this repository to your PC. Navigate to the directory containing your Arduino installation, and then open up the 'hardware' folder. Extract the contents of the .zip file into this directory. You should have a new 'xinput_elitec' folder with an 'avr' folder inside of it, containing the files from this repository (see the tree view above).

Restart the Arduino IDE. If the Elite-C board is installed correctly, you should see a new collection of "Elite-C w/ XInput" in the `Tools -> Boards` menu.

To uninstall, delete the 'xinput_elitec' folder in the 'hardware' directory, and then restart the Arduino IDE.

## Upload Warning and Instructions

**!!!!!!! IMPORTANT !!!!!!!**

The Elite-C uses the Atmel USB DFU bootloader instead of the typical Caterina bootloader including with typical Arduino devices. In order to program, you must bridge the Reset pin to low once to enter DFU mode, then you may program directly via the Arduino IDE. `avrdude` is not able to automatically start the program after flashing. You may power cycle the Elite-C, or use Atmel FLIP to start the program.
