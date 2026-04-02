# PicoGX - A universal cartridge for Amstrad Plus and GX4000

## What is the PicoGX

The PicoGX is a cartridge for Amstrad Plus (464+ and 6128+) and GX4000 console loading cartridges from a MicroSD card.  
Featuring the same package form factor and size as original cartridges, it fits perfectly in the above-mentioned machines.

![plot](./Pictures/TheCartridge.jpg)

## Functionalities

+ Organize the SD as you wish, the PicoGX supports any folder structure of any depth.  
+ If SD card is removed, automatically launches the last loaded cartridge  
+ Present a clear and easy menu on the machine's own screen with detailed fonts  
![plot](./Pictures/PicoGX_menu.jpg)
+ Last loaded cartridge is always on top of the list with inverted colors for fast launch  
+ When connected with the USB-C port to a PC, act as an adapter and mount the SD as disk  
+ Supports future games/demos up to 1.5Mb in size  

## Connectivity

![plot](./Pictures/PicoGX_top.jpg)  
_The picture was taken at prototype time, the cartridge is now white and sticker suites better_

+ MicroSD slot for cartridges storage  
+ USB-C plug to connect to a PC as adapter or to update the firmware  
+ Hole hidding a button for firmware update  

## Construction

The PCB is based on a Raspberry Pi Pico 2 model RP2354B and is using ENIG surface finish and gold plated contacts.  
The box is printed in automotive LEDO 6060 resin.  
The sticker is profesionnally made of vinyl.  

## Where to buy it

In UK: [FlameLily shop](https://shop.flamelily.co.uk/picogx) covers the UK  
In France: The shop is not ready yet to sell it and will cover Europe  

## Updating the firmware

Firmware is evolving based on users feedback. The firmware version is displayed on top right of the CPC screen, you can compare with the latest release, check the "Releases" on the right of this page.  
To update the PicoGX firmware, get the latest .uf2 file, connect the USB-C port of the pico with a cable, push the button hidden 5mm under the hole and keep it pushed while you plug the other end of the cable to a PC.  
Then release the button when the PC makes a mounting sound. A USB disk drive called "RP2350" will mount. Drag & drop the .uf2 file in this folder. 
When flash is complete (it will take ~2 seconds), the folder disappears.  

To help pressing the button, I made a pin. If you have a 3D printer, print it.  
You can find it in 3Dpin folder.  

## Usage

The raspberry PI Pico supports only SDHC and SDXC cards. Old 1 gb SD card won't work.  
Recommendation is to use a 16 gb new one, it's too big but it's cheap.  

The SD can be in any of the following formats:
- Fat16
- Fat32
- ExFat - My preference
- Ext2

There is no need of a 1 gb reserved space in the begining of the SD card, this will even make the SD card not working in some cases.  

Organise cartridges in folders and sub-folders since there is more than 1000 games available in this format and the PicoGX supports only 260 files + sub-folders per folder (firmware 1.0.3 and above).  
The PicoGX will display only folders with one or more CPR or BIN file inside at any depth.  

PicoGX usage is straitforward, use keyboard arrows up and down or joystick up/down to change file selection, use right/left arrows/joystick to change page, enter/button1 to launch a game or enter a folder, ESC/DEL/button2 to return to previous folder. You can also click on the arrow on top of page 1 to return to previous folder.  
All this is written on the bottom of the screen.  

## Changing colors

With firmware 1.0.4 and above, the selection menu colors can be changed.  
To do this, create a file named `PicoGX.cfg` on the root of the SD card.  
Put the following content:  

    # Here you can set the color used in the selection screen
    # It's either #nn using hexadecimal value from the table noted INKR and bold
    # Or use the CPC color code from the BASIC. It goes from 0 to 26 in decimal form and is the BASIC column in the table
    [Color]
    Background=#54
    Text=26

With firmware 1.0.5, now supports Windows file ending and missing last return.  

Lines beginning with `#` are comments and ignored by the PicoGX.  
Check this <a href="https://neo2003.github.io/PicoGX/ColorTable.html" target="_blank">Color Code page</a> to know which values to put for colors.  
The PicoGX will recognize INKR values prefixed with a `#`, this is an hexadecimal number from #40 to #5F, not all values in between are valid. The PicoGX will check validity and not change colors if a value in invalid.  
It will recognize a decimal number if no `#` is present and will accept values from 0 to 26 which are Amstrad BASIC color numbers.   
Note that colors won't be applied if both colors are same, even if one is written with INKR value and the other one with BASIC color number.  

## Some custom cartridges

I made few cartridges  
+ [Basic 1.1 f3 French](./Cartridges/Basic%206128%20Fr.cpr) from CPC 6128  
+ [Basic 1.1 f3 French Pipe](./Cartridges/Basic%206128%20Fr%20Pipe.cpr) from CPC 6128 and modified to have pipe at proper place and inactive ù    
+ [Basic 1.1 v3 English](./Cartridges/Basic%206128%20En.cpr) from CPC 6128  
+ [Basic 1.1 f4 French](./Cartridges/Basic%20Plus%20Fr.cpr) from "Burnin'Rubber + Basic" cartridge  
+ [Basic 1.1 v4 English](./Cartridges/Basic%20Plus%20En.cpr) from "Burnin'Rubber + Basic" cartridge  

Basic from 6128 works only with 6128 Plus, **will not work** with 464 Plus or GX4000 due to the missing floppy controler.  
Basic from Plus works with all, but is useless on GX4000. Burnin' Rubber and menu were removed  

You can also find them by browsing the Cartridges folder, other languages will come soon.  

## Programming for or with the PicoGX

Follow [the link to this page](./Programming.md) to learn how to use 1.5MB cartridges, have save and develop for or with the PicoGX.  

## Games

[1000+ games in cartridge format](https://mega.nz/file/zJJCgahb#oxERnzEHLNnP3jeOzDfmT6eF4zcTy8p313bP3_G-g4w), mainly to be used with joysticks  

## Greetings

Many thanks to Edouard BERGE for his [RASM compiler](https://github.com/EdouardBERGE/rasm) I used to make the CPC roms and also for his big help with the selection cartridge.  

Many thanks to BDCiron who is working on an alternative selection cartridge using ASIC acceleration, this firmware will be released in the future.  

Many thanks to FreddyV (the creator of the [PicoMEM](https://github.com/FreddyVRetro/ISA-PicoMEM)) for the help with Pico power supply, for components selection and BOM creation for the PicoGX.  