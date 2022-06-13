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

## Provisioning
At this time the ESP32C3 FPGA firmware does not automatically handle WiFi
provisioning so the SSID and password of the local WiFi router must be provided
at compile time. To do this you must follow these steps:

1) copy the file main/credentials_template.h to main/credentials.h
2) edit the main/credentials.h file to reflect the proper SSID and password for
your network

## Building
Use the normal IDF build command:

idf.py build

## Installation
Connect the USB-C port of the ESP32C3 FPGA board to the build host machine and
use the command

idf.py -p <serial device> flash

where <serial device> is the USB serial device which is created when the board
enumerates.

## Monitoring
The board generates a fair amount of status information that is useful for
debugging and tracking performance. Use the command

idf.py -p <serial device> monitor

to view this information.
