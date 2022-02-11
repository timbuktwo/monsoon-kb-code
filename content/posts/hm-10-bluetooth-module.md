+++
title = "HM-10 Bluetooth Module"
date = "2022-02-11T15:42:24-07:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["configs", "hm-10", "gemini"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

# Wiring diagram

```
     HM-10  |   VESC
  ======================
  |   VCC   |    5V    |
  |   GND   |   -/GND  |
  |   RXD   |    TX    |
  |   TXD   |    RX    |
  ======================
```

# VESC Tool Configuration
1. Connect to ESC
2. Read App configuration
3. Navigate to App Settings > UART
4. Set Baudrate value to 9600

When configuring a dual VESC setup like the [Flipsky Dual FSESC4.20 100A](https://cdn.shopify.com/s/files/1/0011/4039/1996/files/Dual_FSESC4.20_100A_MANUAL_20181106.pdf.pdf?14152829648107869006), you'll need to configure each VESC "side" individually. For example, the Gemini longboard uses 2 different baud rates for each of the peripherals connected to the UART ports. 

## Left side (secondary) ESC UART Config:
HM-10 BLE Module - 9600 bps

## Right side (primary) ESC UART Config:
Flipsky VX1 Remote - 115200 bps
