
# Arduino nano EEPROM writer for FV-1 programs

Tool to write FV-1 programs into an 24LC64 EEPROM using an Arduino nano

## Required hardware
* Breadboard
* 24LC64 EEPROM
* Arduino nano
* Wires
### Optional
* 2x 4.7K pullup resitors

## Required softweare
There are some alternative ways that rely on different software. This guide requires the following software:
* Arduino IDE 
* SpinAsm IDE

We will use the SpinAsm IDE to generate the hex contents from the FV-1 programs, and the Arduino IDE to write the hex contents to the EEPROM.

## Steps
1. Wire the Arduino to the EEPROM according to this:
 EEPROM pin  5         ==> Arduino pin A4 (SDA)
 EEPROM pin  6         ==> Arduino pin A5 (SCL)
 EEPROM pins 1,2,3,4,7 ==> Arduino GND
 EEPROM pin  8         ==> Arduino 5V
2. Download the programs you want to write (e.g., https://mstratman.github.io/fv1-programs/)
3. Open the SpinAsmIDE. If you already have a .spj project open it and skip to step 6.
4. Select File -> New
5. Press the "Setup directories for all file types button" and take note (or change) the configured directories. The relevant entry is the "c header out" since it's where our hex files will be placed
6. Click on the "Open project dialog" and choose the files you'll want written to the EEPROM. These should be the same files downloaded in step 2. Double click on each "PROG" entry to op he Arduino IDE and open the MyEEPROMBurner.ino file
7. Follow the instructions written in the comments of the ino file. The Header file mentioned in the comments should be in the "c header out" directory configured in step 5 in the SpinAsm IDE
8. Upload the code to the Arduino, run it, and all the files should have been burned to the EEPROM

## Useful resources
http://www.spinsemi.com/forum/viewtopic.php?f=3&t=785

![arduino](res/arduino.jpg)
