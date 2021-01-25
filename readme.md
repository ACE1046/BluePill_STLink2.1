# BluePill ST-Link v2.1

![](/Images/Image1.jpg)

ST-Link v2.1 adapter. 2 devices in 1. ST-Link & USB-UART adapter

### Links

Base on https://github.com/nr-electronics/DiY/tree/master/ST-Link%20V2.1%20%2B%20VCP%20%2B%20Mass%20Storage \
https://youtu.be/wWVU0SCtXpQ

### Description

Board to convert cheap BluePill board to STM32 SWD programmer with virtual COM-port.

### Instruction for windows

Before soldering 2 boards together, remove resistor R10 from BluePill. Usualy it is 10K (103 merking).
![](/Images/Image3.jpg)
After soldering the device you need to flash it.\
Set jumpers to boot0=1, boot1=0\
Connect USB-UART adapter to BluePill. Connect GND to GND, TX to PA10, RX to PA9. Connect power (from adapter or through USB).\
Use "flash loader demo" program to flash Unprotected-2-1-Bootloader.bin\
After successful flashing set boot0=0 and reconnect (or connect) usb. USB-UART adapter can be disconnected, it will not be needed.\
Now we have ST-Link V2.J16.S4 STM32+STM8 Debugger and need to update it\
Using "st-link utility 4.3.0" (exactly 4.3.0) selecting menu ST-LINK -> Firmware update\
Upgrade the firmware to "STM32+Audio" (or "STM32+MSD+VCP" for 128K bluepills, if you wish. This will add a Mass Storage mode).\
Reconnect USB.\
Now we have ST-Link V2.J32.A1\
Using STM32CubeProgrammer update it to latest version. Press blue button "Firmware upgrade", "Open in update mode", "Upgrade"\

![](/Images/Image5.jpg)
![](/Images/Image6.jpg)

