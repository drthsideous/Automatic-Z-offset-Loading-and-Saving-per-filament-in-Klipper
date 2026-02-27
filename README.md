# Automatic-Z-offset-Loading-and-Saving-per-filament-in-Klipper
These macros work with Orca. It enables Klipper to see, and load different Z-offsets depending on what filament type the slicer sends. It also saves updated Z-offsets per filament when baby stepping/live tunning.

For those of us who don't have a static Z-Endstop to run AUTO_Z_CALIBRATION and have to adjust
our z-offsets for different filament types.

These macros will enable you to set and save different Z-offsets per filament type.

They will automatically load at the begining of each print.

They will also automatically save any adjustments made during baby stepping/live tuning at
the end of the print. All you have to do is let the print finish and the new offset will save.

THIS IS A WARNING:
I made these macro's with the help of AI. I do not know how to write code well, let alone 
write macros. These work and function for my set-up. That does not mean they will work 
and function for your set up. I'm running Mainsail v1.2.1-1-gff3869a6, 
mainsail v2.17.0 Klipper v0.13.0-541-g187481e2, moonraker v0.10.0-8-g293a4cfc 
on a BTT Pi v1.2 and SKR MINI e3 V3 at this time. I keep my programs up date as they roll out. 
If I encounter any problems upon a new update I will figure it out, and update the macros 
accordingly at that time.

I've included examples of my START_PRINT and END_PRINT macros to give those of you less
inclined to coding, like myself, an idea of how I have things set up, and where I placed
specific lines to make all of this funtion.

DO NOT HIT THE SAVE BUTTON IN THE CONSOLE AFTER BABY STEPPING/LIVE TUNING THIS WILL STILL
SAVE TO YOUR PRINTER.CFG AND CHANGE YOUR BASE SETTING THAT ALL OF YOUR OTHER OFFSETS ARE BASED
ON. Simply let the print finish and your new offset will be saved for that filament.

Probe_Offset_guard will warn you if your printer.cfg was changed in the last print.
If it detects a change it will pause your print at the begining, and give you the option to
proceed and save the new BASE offset, or abort and revert back to the original BASE offset.
This is a guard incase you hit the save button after baby stepping.

Reapply_Filament_Offset reapplies the current offset for the filament type you are currently
printing. In case you baby step too far in either direction, or accidently clear
the offset during a print and want to go back to that filaments offset setting.

There is also a warning, and confirmation at the end of every print if you made any changes 
to that filaments particular Z_offset.

These macros work off of a BASE setting in your printer.cfg. In my case #*# [bltouch]
                                                                        #*# z_offset = 123

My Z offset in the printer config is what I use for ASA, which is why in my saved_variables
ASA is set to 0.00.
																		

