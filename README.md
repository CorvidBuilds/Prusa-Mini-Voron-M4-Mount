# Prusa Mini Voron M4 Mount
Adapter and mounting plate to put the Voron M4 extruder on a Prusa Mini.
###### Advantages:
- Shorter bowden tube than mounting the M4 to a static position on the Z extrusion.
###### Disadvantages:
- More moving weight on Z axis.
- Must use pancake motor.

# Disclaimer
I whipped this up in an afternoon. The goal was to make _something that works_, not necessarily something pretty or maximally functional. The mounting plate may conflict with other mods but worked with my OPM's electronics box. Due to clearances, the original extruder motor must be swapped out for a pancake motor. ***These parts are not scaled for ABS.***

# Instructions

1.  Print the Adapter Plate letters face up.
2.  Print the Mounting Plate letters face down.
3.  Add Heated Inserts as indicated by the parts. There should be 4 total.
4.  Mount Adapter Plate in place of the original extruder using 2 M3x16 bolts as indicated. The unmarked hole is here if you want to index the plate with an additional M3 bolt and nut to imitate the original design.
5.  Mount Mounting Plate onto the Adapter Plate using 2 M3x12 bolts as indicated.
![Assembly](https://github.com/CorvidBuilds/Prusa-Mini-Voron-M4-Mount/blob/main/images/Aseembly.png)
6.  Mount M4 to Mounting Plate using 2 M3x12 bolts. I've had these bolts back out so I recommend a temporary threadlock of your choice.
7.  If you're using the Prusa firmware add the following to your slicer's startup gcode:
> M92 E550
