# G Commands

## `G00` - Rapid Positioning

The `G00` command creates a linear motion to the position specified in a command like the one given below, moving at the fastest speed possible. This is typically used for starting processes.

```G00 X5 Y12``` is a command to move to the coordinate (5,12) at the fastest speed the system will allow.

## `G01` - Linear Approximation

The `G01` is a command that will create a linear motion to the specified coordinate, but with a specified speed using the `F` value. An example command can be seen below: 

```G01 X5 Y12 F200``` is a command that will move the extruder to (5,12) in a linear motion with a speed of 200 (mm/min in this case).

## `G28` - Homing Sequence

The `G28` command is critical for startup processes, as it will cause the position that is reached there will be used as the zero point for sensors to enable the precision that is needed in a 3D printer.

## `G29` - Bed-Leveling Sequence

The `G29` command should be called after the homing command such that the bed leveling can be standardized to the homed device. This is critial if the machine has an autoleveler because otherwise there may be issues with the final print.

## `G92` - Zeroing the Device

This `G92` command is used to set all axis and other values to 0 after the homing sequence has been completed. 

To zero the position, you will run this command: ```G92 X0 Y0 Z0```

Use this command to zero for the extruder: ```G92 E0```

# M Commands

## `M104` or `M109` - Setting Temperature of Nozzle

Using `M104` will set the temperature expected for the nozzle and continue printing, even if that temperature is not reached.

Using `M109` will set the temperature expected for the nozzle and pause printing until the temperature is reached, then continue with printing.

This is an example of how you would set the temperature using this command: ```M104 S210```

## `M140` or `M190` - Setting Temperature of Print Bed

Using `M140`  will set the temperature expected for the print bed and continue printing when the temperature is not reached, very similarly to `M104`.

Using `M190` will set the temperature expected for the print bed and pause until the print bed temperature is reached, very similarly to `M109`.

## `M106` - Setting Fan Speed

`M106` uses numbers from 0 to 255 to determine the speed of the fan. When not provided with any number, it will cause the fan to go at the maximum speed. For example:

```M106 S255``` sets the fan to full power

```M106``` sets the fan to full power

```M106 S128``` sets the fan to half power

```M106 S0``` turns off the fan

## `M107` - Turning Off The Fan

`M107` behaves very similarly to `M106 S0` in that it simply turns the fan off.

## `M84` - Disable Steppers

`M84` is very important as it will disable the stepper motors, allowing the extruder and carriage to be moved by hand. 

Simply running ```M84``` will disable all stepper motors, while running ```M84 X Y``` will specifically disable the stepper motors for the X and Y axes. This same behavior can be used with all axes.

## More information to come very soon!

# Sources

- https://howtomechatronics.com/tutorials/g-code-explained-list-of-most-important-g-code-commands/
- https://www.youtube.com/watch?v=2TByiMNduss&pp=ygUOZ2NvZGUgY29tbWFuZHM%3D