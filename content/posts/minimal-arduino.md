+++
title = "Minimal Arduino"
date = "2021-04-19T22:11:24-07:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["arduino", "transmitter"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

# Programming ATMega328P-PU 8MHz

## Things you’ll need for the Transmitter:

* Arduino Uno
* ATmega328-PU
* RF24 Library (Via Library Manager in Arduino)
* Adafruit GFX Library (Via Library Manager in Arduino)
* Adafruit SSD1306 Library (Via Library Manager in Arduino)
* LowPower Library (GitHub | Blog | Our Link)
* 8 MHz Arduino Board (Arduino Website | Our Link)

## Burning 8 MHz Bootloader & Programming Sketch:

1. Add the libraries to the Arduino folder (User/Documents/Arduino/libraries)
2. Add the 8 MHz board to the Arduino folder (User/Documents/Arduino/hardware)
3. Program the ArduinoISP sketch to the Arduino Uno in the IDE
4. Throw the ATmega328-PU onto a breadboard and wire it according to this image
5. In the IDE, click Tools > Board > ATmega 328 on a breadboard (8 MHz internal clock)
6. Click Tools > Programmer > Arduino as ISP
7. Click Tools > Burn Bootloader
8. Open sketch in the IDE and click Sketch > Upload Using Programmer

## Troubleshooting:

* If using a MAC, put a 10uF capacitor between reset and ground pin on the Uno during Bootloader Burn and Programming
* Last tested and working on Arduino version 1.8.5 on MAC & Windows

