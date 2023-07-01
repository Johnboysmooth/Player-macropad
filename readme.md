# Player! V1.31

Player! is a five button macropad originally designed to accomodate changing music settings in Spotify without tabbing into the Spotify client. By default it is programmed to use dedicated media keys, which can be further optimised with global hotkeys in Windows using [Toastify](https://github.com/aleab/toastify).

Using four cherry compatible switches, Player! provides dedicated keys for pausing/playing music -  returning to a previous song, and skipping to the next song. The fourth switch remains user programmable, binded to 'insert' by default to be used as dedicated Discord mute key. A rotary encoder allows for volume control, with a toggle function bound to its embedded switch to allow rotary control of rewinding and fast-forwarding music. Player! is entirely customisable, using [Vial](https://get.vial.today/) for rebinding keys.

# Images
![](/Images/Player!_3D_KiCAD.png)
![](/Images/Player!_Assembled.jpg)

V1.31 has made the Player! bigger to accommodate 4 mounting holes, which will be used to mount the PCB to a case. The otherwise empty space is covered in a tropical leaf pattern on the top copper layer; a number of changes have been made to improve the appearance, including the addition of the logo top centre of the board. The Player! will now include an ISP header for programming.

# [Bill of Materials](https://octopart.com/bom-tool/iGNVRgwb)

### Entering bootloader mode
Player! will need to be put into bootloader mode to allow QMK to be flashed via the USB connection, see below:

1. Press and hold ```Boot``` switch
2. Tap ```Reset``` switch
3. Release ```Boot``` switch

USBaspLoader will show up in device manager or as a connected device in QMK toolbox when the device has successfully entered bootloader mode, like so:
![](/Images/QMK_Toolbox.png)

## Vial Support 

Vial compatible firmware can be flashed to the Player! using the [player_vial.hex](/Firmware). 
1. In QMK_Toolbox, click "Open", then navigate to player_vial.hex and select it. 
2. Click "Flash". 
3. Following successful flash completion, press the ```Reset``` button on the PCB. 

Player! can now be configured and is now ready to use. The rotary encoder is rebound using the two circular icons on the top row, the switch integrated to the encoder uses the buttons below these icons.
# Bootloader Information
The Player! uses a usb bootloader which allows the ATMega328 to program itself with QMK, namely [USBaspLoader](https://www.fischl.de/usbasp/). 


* The bootloader is available [here](https://github.com/Johnboysmooth/USBaspLoader).
* The instructions for setting up the build environment can be found in the readme.
* Some changes may be required, such as changing the port or programmer definitions for your setup, which can be found on lines 9 and 44 of the makefile.inc respectively. **Never** edit the makefile directly.
* Flashing the ATMega328 once the build environment is setup:

	```make flash``` (flashes the makefile)

	```make fuse``` (sets fuses for ATMega328)


## License
<br />Player! is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License </a>
