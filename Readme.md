# Credits

Digant, Waggster, BIGTREETECH, Marlin Firmware for unlocking the power of this beast. The Firmware Port belongs to Digant. PDF Documentations, aswell as the Waggster Auto Bed Leveling Mod belong to Waggster. I created the custom PrusaSlic3r Profiles for it and spent a ton of time optimizing it.

# Summary

A porting of the BIGTREETECH TFTxx firmware to the MKS TFT28 used on Artillery Sidewinder X1 and Genius printer.
This porting is based on last release xx.26 of BIGTREETECH TFT firmware found on https://github.com/bigtreetech/BIGTREETECH-TouchScreenFirmware/tree/master.

It was arranged according to Artillery Sidewinder X1 / Genius hardware (e.g. onboard modules etc...).
Furthermore, bug fixes, rearrangement of menus, improvements and additions were applied.

## PrusaSlic3r Profiles

To get going, import the PrusaSlicer_config_bundle.ini file

The PrusaSlic3r Profiles also include test Profiles. You will get the best results from the QUALITY Profiles. SPEED Profiles for big mechanical prints. SQUIDGame if you wanna print so fast that you need to roll a dice to get a usable print. Rest are testing profiles. Tons of filament and Print Profiles are added.

Nozzle 0.40 Printer settings also include the custom GCode for BL Touch Auto Bed Leveling. Use this template on the custom GCODE start parameters and copy it over to the other Nozzle Profiles if you wanna use these with BL Touch. You basically need the G29 Code executed before your print begins.

## COMPATIBILITY WITH OCTOPRINT / PRONTERFACE

The serial bus with the main board (MKS GEN L v1.0) is shared between TFT and Octoprint / Pronterface etc... This means that printing from Octoprint / Pronterface etc... causes Marlin to receive gcodes from Octoprint and TFT at the same time (there are collisions). This will let Marlin reply with error messages, that will be displayed on both Octoprint and TFT display, such as:

Line Number is Not Last Line Number +1 Last Line 1686.
In order to avoid the problem, when printing with Octoprint/Pronterface etc... put the TFT in "Listening Mode" pressing on the button:

Menu =>Settings=>Connection=>ON
NOTE:

This limitation is not due to bugs on the TFT firmware but it's an hardware limitation on MKS GEN L v1.0 main board
The mode state is stored on FLASH allowing to restore the mode at startup. This allows to power on/off the printer remotely and to control the printer via USB without the need of any touch (from the user) on the display to engage the mode