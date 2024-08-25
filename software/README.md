# ZXMUX Tester  

To upload the HEX file to your Arduino you will need to use [avrdude](https://github.com/avrdudes/avrdude)


The output is displayed via the serial monitor at 115200 baud so it would also be useful to also install [Arduino IDE](https://www.arduino.cc/en/software)

The below avrdude command line example is for Linux. You may need to change the port for your device. If you are running Windows you may need to install device drivers although these should be installed already if you have installed Arduino IDE


```
avrdude -v -patmega2560 -P /dev/ttyACM1 -cwiring -D -U flash:w:zxmux-tester-1.0.hex:i
```

```
avrdude: Version 7.1
         Copyright the AVRDUDE authors;
         see https://github.com/avrdudes/avrdude/blob/main/AUTHORS

         System wide configuration file is /etc/avrdude.conf
         User configuration file is /home/greg/.avrduderc
         User configuration file does not exist or is not a regular file, skipping

         Using Port                    : /dev/ttyACM1
         Using Programmer              : wiring
         AVR Part                      : ATmega2560
         Chip Erase delay              : 9000 us
         PAGEL                         : PD7
         BS2                           : PA0
         RESET disposition             : possible i/o
         RETRY pulse                   : SCK
         Serial program mode           : yes
         Parallel program mode         : yes
         Timeout                       : 200
         StabDelay                     : 100
         CmdexeDelay                   : 25
         SyncLoops                     : 32
         PollIndex                     : 3
         PollValue                     : 0x53
         Memory Detail                 :

                                           Block Poll               Page                       Polled
           Memory Type Alias    Mode Delay Size  Indx Paged  Size   Size #Pages MinW  MaxW   ReadBack
           ----------- -------- ---- ----- ----- ---- ------ ------ ---- ------ ----- ----- ---------
           eeprom                 65    10     8    0 no       4096    8      0  9000  9000 0x00 0x00
           flash                  65    10   256    0 yes    262144  256   1024  4500  4500 0x00 0x00
           lfuse                   0     0     0    0 no          1    1      0  9000  9000 0x00 0x00
           hfuse                   0     0     0    0 no          1    1      0  9000  9000 0x00 0x00
           efuse                   0     0     0    0 no          1    1      0  9000  9000 0x00 0x00
           lock                    0     0     0    0 no          1    1      0  9000  9000 0x00 0x00
           signature               0     0     0    0 no          3    1      0     0     0 0x00 0x00
           calibration             0     0     0    0 no          1    1      0     0     0 0x00 0x00

         Programmer Type : Wiring
         Description     : Wiring for bootloader using STK500 v2 protocol
         Programmer Model: AVRISP
         Hardware Version: 15
         Firmware Version Controller : 2.10
         Vtarget         : 0.0 V
         SCK period      : 0.1 us

avrdude: AVR device initialized and ready to accept instructions
avrdude: device signature = 0x1e9801 (probably m2560)
avrdude: reading input file zxmux-tester-1.0.hex for flash
         with 8704 bytes in 1 section within [0, 0x21ff]
         using 34 pages and 0 pad bytes
avrdude: writing 8704 bytes flash ...

Writing | ################################################## | 100% 1.39 s 

avrdude: 8704 bytes of flash written
avrdude: verifying flash memory against zxmux-tester-1.0.hex

Reading | ################################################## | 100% 0.99 s 

avrdude: 8704 bytes of flash verified

avrdude done.  Thank you.

```

Once the firmware has been uploaded run Arduino IDE, or any other terminal comms program, and view the serial output at 115200 baud. 

The testing will start and run 20 passes checking the CAS lines and multiplexer logic levels. 

During the test the PASS/FAIL LED's will alternate showing that the test is under way.
At the end of the test the PASS or FAIL LED will display depending on the test outcome. 

![Serial Output](https://github.com/MyRetroStore/ZXMUX-Tester/blob/main/software/serial-output1.png?raw=true)


![Serial Output](https://github.com/MyRetroStore/ZXMUX-Tester/blob/main/software/serial-output2.png?raw=true)










