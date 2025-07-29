# ATmega328PB Arduino Nano Clone config incl. Bootloader
The bootloader is a modified version of Optiboot (https://github.com/Optiboot/optiboot).

## How to install
Add the following URL to the Arduino Board Manager (**File > Preferences > Additional Boards Manager URLs**)
```
https://raw.githubusercontent.com/technick100/ATmega328PB-Arduino-Nano-Clone-with-Bootloader/master/package_m328pb_index.json
```
Then search in the Board Manager for **ATmega328PB** and click install.

If this fails, you might download the zip file and unzip it to:
```
C:\Users\<Your Username>\AppData\Local\Arduino\packages\ATmega328PB-with-Bootloader\hardware
```

## How to burn the Bootloader

1. Wire Arduino Uno to ATmega328PB

| Arduino Uno Pin | ATmega328PB Pin |
|--|--|
| 10 | RESET |
| 11 | MOSI (PB3) |
| 12 | MISO (PB4) |
| 13 | SCK (PB5) |
| 5V | VCC / AVCC |
| GND | GND |

![ICSP header](https://raw.githubusercontent.com/technick100/ATmega328PB-Arduino-Nano-Clone-with-Bootloader/master/1.png)

I recommend following this instruction: https://sysexit.wordpress.com/2013/02/07/burning-a-bootloader-to-an-arduino-nano-using-another-arduino/

Simply select "ATmega328PB" as board, instead of "Arduino Nano w/Atmega 328 again"

2. Check bootloader

```
"C:\Users\<Your Username>\AppData\Local\Arduino15\packages\arduino\tools\avrdude\6.3.0-arduino17/bin/avrdude" "-CC:\Users\<Your Username>\AppData\Local\Arduino15\packages\ATmega328PB-incl-Bootloader\hardware\avr\2.0\tools\avrdude.conf" -v -patmega328pb -cstk500v1 -PCOM6 -b19200 -D
```