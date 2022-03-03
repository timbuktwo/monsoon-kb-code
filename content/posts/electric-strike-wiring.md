+++
title = "Electric Strike Wiring"
date = "2022-03-03T15:24:10-07:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["", ""]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

The Wiring diagram below illustrates how the wires from port `S20` on the locker controller circuit board and the 12V electric door-strike wires terminate to the UHPPOTE module.

```
  |   S20   |   Uhppote   |  Door Strike  |
  ======================================
  |   BLK   >   CONTROL-  |               |
  |   RED   >   CONTROL+  |               |
  |         |    PUSH     |               |
  |         |     GND     |               |
  |         |    +12V     |               |
  |         |    -COM     <     BLK       |
  |         |     +NC     |               |
  |         |     +NO     <     RED       |
  =======================================
```
