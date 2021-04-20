---
title: "Transmitter Receiver Tuning"
date: 2021-04-19T23:03:04-07:00
draft: false
toc: false
images:
tags: 
  - arduino
  - NRF24L01
---
The Prayer Rx and El Nieto Tx are due for some TLC. Below is the TO-DO list:

**Receiver Version 5 (RX Mark IV)**

- [ ] Additional bypass capacitors of different values
- [ ] Higher value resistor to dim the LED brightness

**Transmitter Version 8.1 (double check version)**

- [ ] Additional bypass capacitors of different values
- [ ] Remove charging/protection circuitry
- [ ] Remove accompanying charge/protect passives
- [ ] Remove Micro USB
- [ ] Add charging circuit pads for off the shelf charging/protection circuit

**Bypass Capacitor Notes:**

Place the bypass capacitors as close as possible to the chip that needs the clean signal in order to limit the inductance and impedance caused by parasitic properties.