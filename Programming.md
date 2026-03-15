# Programming for the PicoGX

The PicoGX provides some fonctionalities not available to regular cartridges.  

## How communication between the machine and the pico works

A cartridge is a read only device, and no write pin is available on the connector. This means everything is done by addresses.   
An example showing how the selection cartridge works is better than many words:  
```
Contact_Addr1 	EQU #133C
Contact_Addr2 	EQU #25C4

	ld bc,3 ; cd  
	ld a,(Contact_Addr1)  
	ld a,(Contact_Addr2)  
	ld a,(bc) ; command
```  
This code (Z80 assembly) will read something at address 0x133C, then address 0x25C4, the PicoGX will recognize this sequence and will consider the next read address as the command number. Here the PixoGX will execute the `CD` command.  

## Accessing more than 512kb

When the PicoGX detects a cartridge more than 512KB in size, it will lookup for reserved addresses in the Bank 0 of the cartridge.  
![plot](./Pictures/Warning.jpg) This is always bank 0, whatever mapping you apply using RMR2, so cartridge address from 0x000 et 0x3FFF.  
Detection is based on all the 14 bits set ignoring the 2 least weighted bits.
![plot](./Pictures/ExtraSpaceDetection.png)  
Then these 2 least weighted bits are used to select the bloc of 512kb to use:  
+ 00: Use base 512KB (Default launched part).  
+ 01: Use the second 512kb bloc (this is complete flip, the original loaded code is not accessible).  
+ 10: use the third and last 512kb bloc.
+ 11: DO NOT USE! There is not enough flash space in the PicoGX for 2MB cartridges.  

For exemple this code will ask the PicoGX to swap the cartridge content with the 2nd 512kb bloc:
```
	ld hl,#3FFD  
	ld a,(hl)  
```  
This obviously only works if the cartridge is 1mb in size at least. The pico will do nothing if the cartridge is less or equal to 512kb.      