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
