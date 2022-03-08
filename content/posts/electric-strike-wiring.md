+++
title = "Electric Strike Wiring"
date = "2022-03-03T15:24:10-07:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["ota", "locker"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

# Wiring Instructions:  

==CAUTION: You will be dealing with 120V AC mains voltage. Proceed cautiously.==  

Note: The locker power supply unit (PSU), backup battery (UPS), and circuit breaker are all located behind the tablet locker door.

1. Open the door, disconnect the locker from power, and turn off the locker breaker 
2. Make sure the backup battery (UPS) is powered off and disconnected
3. Unscrew 2 silver screws securing the locker power supply housing to the locker
4. Carefully flip over the locker power supply housing to expose the power supply unit
5. On the power supply unit, flip the plastic terminals cover to reveal the terminal screws
6. ==Carefully== connect the 2 ==RED== Uhppote wires to the locker power supply as shown in the diagram
7. Connect the UHPPOTE to the electric strike as shown in the diagram
8. Connect the UHPPOTE to port ==S20== on the locker controller board as shown in the diagram

# Configuration (WIP):  

8. In OTA Slack, message #Mobile channel to “update the locker context and installer mapping files, along with the lock record linked to the laundry room space.” 
9. On tablet, tap service provider > cancel >tap “are you sure” rapidly > 5411 > installer flow > Production > enter complex installer code > log in with credentials
10. Tablet will pull down locker controller mapping
11. To test, power everything up and try to control locker 19 
    1. On tablet, tap service provider > cancel >tap “are you sure” rapidly > 5411 > view locker statuses > Open locker 19 (you should hear the UHPPOTE relay click if everything is wired up correctly. 
    2. Tune UHPPOTE potentiometer for 5 Second delay

# Wiring Diagrams:  

The Wiring diagram below illustrates how the wires from port `S20` on the locker controller circuit board and the 12V electric door-strike wires terminate to the UHPPOTE module.

```
=========================================
|    S20    |   Uhppote   | Door Strike |
=========================================
|   BLK----->   CONTROL-  |             |
|   RED----->   CONTROL+  |             |
|           |    PUSH     |             |
|           |     GND     |             |
|           |    +12V     |             |
|           |    -COM     <-----BLK     |
|           |     +NC     |             |
|           |     +NO     <-----RED     |
=========================================
```

The wiring diagram below illustrates how the two red 120V AC input wires from the UHPPOTE module terminate to the locker power supply(PSU). Note, these two red wires are not not polarized and can be connected in any orientation to the Live and Neutral AC connnections on the PSU.

```
=====================
| Uhppote |   PSU   |
=====================
|   RED---> NEUTRAL |
|   RED--->  LIVE   |
=====================
```