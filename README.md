Modified Source from: https://github.com/adafruit/Adafruit_CC3000_Library

Adapted modified HW in order to interoperate with LCD Keypad Shield (see https://code.google.com/p/arduino-display-lcdkeypad/).

__HW modifications to be applied__

* on CC3000 Shield cut the following header connections:
  
        CLK (pin 13)
        MISO (pin 12)
        MOSI (pin 11)
        WCS (pin 10)
        WEN (pin 5)
        CCS (pin 4) 

* on CC3000 Shield make the following connections:

        WCS to Header Pin 13
        WEN to Header Pin 12
        CCS to Header Pin 11
        connect the SPI signals (MOSI, SCK, MISO) to the SPI soldering jumpers in order to connect them to the ICSP header connector 

__SW modifications__

* call the Adafruit_CC3000 constructor with the appropriate Pin Numbers:

        csPin=13
        vbatPin=12
        
* if Card Reader is also used on the CC3000 Shield, call the card reader setup with appropriate pin number for CS=11:

        SD.begin(11) 
