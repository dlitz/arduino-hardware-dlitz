# DLitz.net custom board definitions for Arduino IDE

**Note:** This repository contains board definitions for some of my custom
hardware designs, some/all of which is unpublished.  It probably does not make
sense to use these files unless you have that hardware.

## Usage

To clone this repo:

    git clone --recurse-submodules https://github.com/dlitz/arduino-hardware-dlitz ~/Arduino/hardware/dlitz

To burn the bootloader, connect an FT232R to the ICSP port, then run something like:

    arduino-cli burn-bootloader -b dlitz:avr:pwmfanctl -P arduino_ft232r -v

## Bugs

This forces the use of the system 'avrdude' because the built-in one isn't
compiled to support the 'arduino-ft232r' programmer.
