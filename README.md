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
8.  If you decide to print a spacer and to use the original motor, you may have to swap some wires in the motor connector. Instructions can be found [here](https://support.bondtech.se/Guide/01.+Feeder+Upgrade+Kit/59#s606).

# Klipper Config
I use the following with success:
###### Note: You MUST validate these settings for your own machine.
```
[tmc2209 extruder]
uart_pin: PD5
uart_address: 2
diag_pin: ^PA15
driver_SGTHRS: 100
run_current: 0.4
hold_current: 0.4
sense_resistor: 0.22
interpolate: False
stealthchop_threshold: 999999

[extruder]
step_pin: PD9
dir_pin: !PD8
enable_pin: !PD10
microsteps: 16
rotation_distance: 23.421 #26.2564  # (200 * 16 * 48/18) / 325
gear_ratio: 80:20
full_steps_per_rotation: 200	#200 for 1.8 degree, 400 for 0.9 degree
nozzle_diameter: 0.400
filament_diameter: 1.750
heater_pin: PB1
sensor_type: ATC Semitec 104GT-2
sensor_pin: PC0
#control: pid
# Prusa's firmware defaults.
#pid_Kp: 7
#pid_Ki: 0.5
#pid_Kd: 45
min_temp: 10
max_temp: 305
pressure_advance = 0.64 #0.333
pressure_advance_smooth_time: 0.15
```