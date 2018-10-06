# Things to consider

[TOC]

# 1. When drawing electronic circuit 

## For readability

When drawing circuit diagram, it is good to draw for understanding easily.

1. --------------> (dataflow : start from left to right)

   Because I think it is more comfortable for people to see something  from left to right direction.

2. Element Library

   Draw like symbol that datasheet offers rather than pin order(1,2,3...)

   Because similar function pins are nearby each other. 

   It is easy to draw on a function base. (datasheet application)

   And element having a lot of pins is divided into several blocks.

3. It is good to draw block diagram at a front page of circuit

4. Be careful of TX/RX signals names from connector

   1. Mistake sometimes happens that TX/RX are connected wrong.
   2. ex) need own naming rule : TX from CPU, RX from Micom 

5. When draw data line, use Bus line and page connector

## Practical Experience

1. Connector Pin Map
   1. Locate Pin map not to happen Power/GND short though user connects cable in an opposite direction
2. Numbers of connector pin
   1. Power pin : set pin numbers considering the amount of current flowing
      1. ex) If we have to supply 5V/1A with 400mA/Pin Connector, use over 3 pins (1A < 400x3mA)
   2. And GND pin : the same pin numbers as POWER pins
      1. reason : need Return Path. we have to make Power flow load 

# 2. when drawing artwork

1. consider POWER path

2. imagine connection diagram with connector, power and signals

3. consider element location at the same time

   1. we can print 1:1 circuit diagram and match to mechanic diagram on a paper

4. consider the amount of current 

   1. path thickness, length, via numbers

5. check if items are located as my intention.

   1. see if related items get together

      (bypass cap is located nearby element)

6.  Don't make GND island
   1. make one GND
7. Secure GND via
8. make signal lines and GND not sharp (the cause of EMI radiation)
9. Important Signal lines are covered by GND
   1. ex. video output signals and clock

# 3. when debugging

# 4. For product reliability

## 1) temperature

## 2) EMI

## 3) LSS, ESD, Impulse

### LSS

Use TVS Diode so that LSS goes to GND through it not to have influence on other ICs.

1. divide GND 
2. Ethernet Protection Circuit (TVS diode) : locate it to between ethernet transformer and phyceiver rather than between transformer and outside line 
3. increase serial resistance value for audio input signal

### ESD

make PCB hole through hole (metal) and make it touch to mechanical chassis to get large GND

how to touch mechanical chassis

- wire
- EMI gasket

consider GND combination or separation

how to trace the cause

- Suspicious IC : what has an influence on it ?
  - lower supply power
  - short crystal
  - short input signal
  - reset
  - GND combination or separation 

### EMI

1. metal frame convers circuit (Good EMI : shielding effect )
2. EMI radiate through cable
   1. check if PCB pattern (to cable) passes by the elements giving noise --> not to pass by
   2. fix it for preventing cable from moving
   3. use EMI core (proper frequency)
   4. FFC cable : GND shield (with cable GND), flat EMI core
   5. signal clock line : serial resistance

## 4) Safety

# 5. Produce Jig, Productivity

