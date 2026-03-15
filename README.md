# PicoGX - A universal cartridge for Asmstrad Plus and GX4000

## What is the PicoGX

The PicoGX is a cartridge for Amstrad Plus (464+ and 6128+) and GX4000 console loading cartridges from a MicroSD card.  
Featuring the same package form and size as original cartridges, it fits perfectly in the above mentioned machines.

![plot](./Pictures/TheCartridge.jpg)

## Functionalities

+ Organize the SD as you wish, the PicoGX supports any folder structure of any depth.  
+ If SD card is removed, automaticaly launches the last loaded cartridge  
+ Present a clear and easy menu on the machine own screen with detailed fonts  
![plot](./Pictures/PicoGX_menu.jpg)
+ Last loaded cartridge is always on top of the list with inverted colors for fast launch  
+ When connected with the USB-C port to a PC, act as an adapter and mount the SD as disk  
+ Supports future games/demos up to 1.5Mb in size  

## Connectivity

![plot](./Pictures/PicoGX_top.jpg)

+ MicroSD slot for cartridges storage  
+ USB-C plug to connect to a PC as adapter or to update the firmware  
+ Hole hidding a button for firware update  

## Construction

The PicoGX PCB is a Raspberry Pi Pico 2 model RP2354B using ENIG surface finish and gold plated contacts.  
The box is printed in automotive LEDO 6060 resin.  
The sticker is profesionnaly made of vinyl.  

## Greatings

Many thanks to Edouard BERGE for his [RASM complier](https://github.com/EdouardBERGE/rasm) I used to make the CPC roms and also for his big help with the selection cartridge.  

Many thanks to BDCiron who is working on an alternative selection cartridge using ASIC acceleration, this firmware will be released in the future.  

Many thank to FreddyV (the creator of the [PicoMEM](https://github.com/FreddyVRetro/ISA-PicoMEM)) for the help with Pico power supply, for components selection and BOM creation for the PicoGX.  

## Programming for the PicoGX

Follow [the link to this page](./Programming.md) to learn how to use 1.5MB cartridge and more to come.  