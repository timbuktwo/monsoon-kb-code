+++
title = "Tc66c"
date = "2022-04-25T12:58:50-07:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["usb-tester", "tc66c"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

## TC66C Notes
[**Product page, documentation, manual**](https://www.aliexpress.com/item/32968303350.html?spm=a2g0o.store_pc_groupList.8148356.7.594165cfWlLoPl)

[**Deep Dive YouTube Video by TheHWcave**](https://www.youtube.com/watch?v=rOlhibDUJgs)

### Current Draw:
* Measuring current draw via the male USB-C plug subtracts the current drawn by the TC66C and only displays the current drawn by the client device.
* Measuring current draw via the female USB-C port will include the current draw from the client device + the current draw from the TC66C combined. To measure current draw from this port correctly, the TC66C must be powered via Micro-USB. Ensure to set the PD and PWR switches to off. This is due to where the shunt resistor is located in the circuit. On the male end of the TC66C, the VBUS line is routed directly to a 3.3V regulator > MCU before it gets to the shunt, so no current is accounted for. On the female end, the VBUS is routed directly to the shunt resistor > 3.3V regulator > MCU, which measures and accounts for the current draw of the TC66C. The TC66C draws ~25mA. The shunt resistor value is very low and similar to the resistance of a standard USB cable. 

### Recording Data: 
The TC66C can record and store 1,440 data points for **Voltage + Current**.  
* Measuring data points can be configured at 1 second intervals all the way up to 60 seconds or 1 minute intervals.
* Once the recording memory is full, it'll stop recording data beyone that point.
* The purple percentage counter indicates the memory used of the 1,440 data points.
* Data is stored in non-volatile memory and will survive a reboot or power loss. Recorded data will persist until it's explicity cleared out via the "Record" menu on the TC66C or via the PC software. 
* To clear data, you need to hold the K2 button and use the white triange to navigate to the `CE` field and short press K1 to clear the time. This will clear the saved Data.
* You can only change the period interval for recording if recording is off and the memory has been cleared.

**Recording Time Table:**
The table below is a good indicator of how long it takes to fill the recording memory at each measurement interval. Recording voltage and current once every second will fill up the NVMemory in 24 minutes.

```
   Interval | Duration
  ====================
  |  1sec   | 24 min |
  |  2sec   | 48 min |
  |  10sec  | 4 Hour |
  |  15sec  |        |
  |  20sec  |        |
  |  30sec  |        |
  |  40sec  |        |
  |  50sec  |        |
  |  60sec  |        |
  ====================
```
### Protocol Detection
During Protocol Detection, only connect the power source and **make sure no other devices are connected to the other USB-C port on the TC66C**. The PD protocol detection software will cycle through each of the PD protocol voltages (5V, 9V, 12V, 20V) during the detection and both of the USB-C ports on the TC66C will see that voltage potential spike.\

**Red protocol color = "Not supported"**
```
Protocols:
==============================
| Qualcomm Quick Charge 2.0  |
| Qualcomm Quick Charge 3.0  |
| Huawei FCP                 | 
| Huawei SCP                 | 
| Samsungf AFC               | 
| Type-C Power Delivery (PD) |
```
1. Disconnect Micro-USB (a power reboot is required to boot into the PD protocol detection software)
2. Set the hardware PD switch to `ON`
3. Set the PD software switch to `ON` in the `Settings` menu

### PD Protocol Triggering
As with Protocol Detection, devices should **NOT be connected when triggering different PD protocols.**\

**RED = protocol selector**
1. Disconnect Micro-USB (a power reboot is required to boot into the PD protocol detection software)
2. Set the hardware PD switch to `ON`
3. Set the PD software switch to `ON` in the `Settings` menu

### PD Switch & software PD Switch:
Sensing: Turning on the PD Switch + software PD Switch enables a pulldown resistor which is outlined in the USB Type-C Power Delivery protocol. This pulldown resistor tells the power source that there is a device connected, turning on V-Bus.

## Note: There is only one pulldown resistor. Unlike previous USB connectors, USB-C connectors can be connected in any orientation, but due to the fact that there is only one pulldown resistor, the USB-C connector must be connected the right way around. If it doesn't power on when in this mode, disconnect the USB cable, flip it over, and reconnect it to the same port. 


