+++
title = "Flash Vesc Based Bootloader"
date = "2021-04-19T22:37:14-07:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["vesc", "stm32"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

# Flash VESC Bootloader

**Step 1.** Download `STM32 ST-LINK Utility`and install it along with the drivers that it prompts during install.

**Step 2.** Launch ST-LINK Utility and connect the ST-LINK V2 programmer to PC by itself (no VESC connected). From the menu, click ST-LINK > Firmware update. Follow instructions to update programmer firmware.

**Step 3.** Wire up the ST-Link V2 (JST PH 2.0MM connector is needed for VESC) and connect it to the VESC.
```
    ST-LINK  |   VESC
  ======================
  |  RST    |   RST    |
  |  SWCLK  |   CLK    |
  |  SWDIO  |   DIO    |
  |  GND    |   -/GND  |
  |  3.3V   |   3.3V   |
  ======================
```
**Step 4.** No external power is needed to flash the bootloader, but note that some recommend using a battery pack connected to the ESC’s XT60 connector in lieu of the ST-LINK’s 3.3V power rail. In the past, we’ve flashed the bootloader on a VESC by using the ST-LINK 3.3V power rail and no external battery pack with no issues. You should choose one or the other, but not both.

**Step 5.** In the ST-LINK Utility, click Target > Connect. A large list of addresses should show up indicating that you’ve connected properly.

**Step 6.** Download and extract the VESC 4.12 Bootloader. In ST-LINK Utility File > Open File > Navigate to BLDC_4_Bootloader_git_f507a7e4affa.hex and click Open. Click Target > Program & Verify > Start. This may take some time, but once it’s done verifying, you’re all done! The Bootloader flashed successfully!