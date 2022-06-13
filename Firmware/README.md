# Firmware
This directory contains the ESP32 C3 firmware for the ESP32C3 FPGA board. The
default firmware supports power-on initialization of the ICE40UP5k FPGA as well
as wireless programming of the FPGA, SPI access after configuration and battery
voltage monitoring.

## Prerequisites
Prior to building this firmware you'll need to have a working installation of the
Espressif ESP32 IDF V5.0 toolchain. You can find it here:

https://github.com/espressif/esp-idf

Make sure you get V5.0 and that you've done all the proper installation and
setup steps.

## Building
Use the normal IDF build command:

idf.py build

# Installation
Connect the USB-C port of the ESP32C3 FPGA board to the build host machine and
use the command

idf.py -p <serial device> flash

where <serial device> is the USB serial device which is created when the board
enumerates.

# Monitoring
The board generates a fair amount of status information that is useful for
debugging and tracking performance. Use the command

idf.py -p <serial device> monitor

to view this information.
