## `G28` - Homing Sequence

The `G28` command is critical for startup processes, as it will cause the position that is reached there will be used as the zero point for sensors to enable the precision that is needed in a 3D printer.

## `G29` - Bed-Leveling Sequence

The `G29` command should be called after the homing command such that the bed leveling can be standardized to the homed device. This is critial if the machine has an autoleveler because otherwise there may be issues with the final print.

## `G92` - Zeroing the Device

This `G92` command is used to set all axis and other values to 0 after the homing sequence has been completed. 

To zero the position, you will run this command: ```G92 X0 Y0 Z0```

Use this command to zero for the extruder: ```G92 E0```

## `M104` or `M109` - Setting Temperature of Nozzle

Using `M104` will set the temperature expected for the nozzle and continue printing, even if that temperature is not reached.

Using `M109` will set the temperature expected for the nozzle and pause printing until the temperature is reached, then continue with printing.

This is an example of how you would set the temperature using this command: ```M104 S210```

## `M140` or `M190` - Setting Temperature of Print Bed

Using `M140`  will set the temperature expected for the print bed and continue printing when the temperature is not reached, very similarly to `M104`.

Using `M190` will set the temperature expected for the print bed and pause until the print bed temperature is reached, very similarly to `M109`.

## More information to come very soon!
