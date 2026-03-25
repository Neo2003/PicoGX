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

## Where to buy it

In UK: [Flame Lily shop](https://shop.flamelily.co.uk/picogx)  
In France: The shop is not ready yet to sell it  

## Limitations as of 2026, March 25th

Be aware that the PicoGX currently does display only 80 items at a time. In any path, it will limit the number of folders+files displayed to 80. I will tune this based on feedbacks.  
File name without extension need to be 40 characters max, if greater than that the PicoGX will fail to load it. I will find a way to fix this, just allow me some time.  

## Construction

The PCB is based on a Raspberry Pi Pico 2 model RP2354B and is using ENIG surface finish and gold plated contacts.  
The box is printed in automotive LEDO 6060 resin.  
The sticker is profesionnally made of vinyl.  

## Some custom cartridges

I made 2 cartridges  
+ Basic 1.1 f3 from CPC 6128 (works on 6128+, will not on 464+ or GX4000 due to missing floppy controler)  
+ Basic 1.1 f4 from "Burnin'Rubber + Basic" cartridge with Burnin and menu removed (works on all but useless on GX4000)  

You will find them for French keyboard in the Cartridges folder, other languages will come soon  

## Greetings

Many thanks to Edouard BERGE for his [RASM compiler](https://github.com/EdouardBERGE/rasm) I used to make the CPC roms and also for his big help with the selection cartridge.  

Many thanks to BDCiron who is working on an alternative selection cartridge using ASIC acceleration, this firmware will be released in the future.  

Many thanks to FreddyV (the creator of the [PicoMEM](https://github.com/FreddyVRetro/ISA-PicoMEM)) for the help with Pico power supply, for components selection and BOM creation for the PicoGX.  

## Programming for the PicoGX

Follow [the link to this page](./Programming.md) to learn how to use 1.5MB cartridge and more to come.  