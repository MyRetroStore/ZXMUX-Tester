# ZXMUX Tester

An Arduino Mega 2560 shield to test the ZXMUX chips used in the ZX Spectrum retro computers.

## Introduction

The ZXMUX chip (ZX8401 / PCF1306P / 40058) is a custom multiplexer chip designed for and used in the ZX Spectrum 128, +2, 48 Issue 5 and 6A.

As this is a custom chip, modern chip testers like the TL866 is unable to test them.  If you are troubleshooting a Spectrum and you don't have a known good working device to test the multiplexer in, this makes it difficult to troubleshoot.


I built an shield for the Arduino Mega 2560 which tests the multiplexer as it's a fairly simple design that uses logic NAND/OR gates and digital multiplexers. I used this to also test the ZXMUX replacement chips that I sell on my store.

The gerber and HEX files are provided if you want to do a DIY.

![Shield](https://github.com/MyRetroStore/ZXMUX-Tester/blob/main/ZXMux%20Tester.jpg?raw=true)


![Output](https://github.com/MyRetroStore/ZXMUX-Tester/blob/main/software/serial-output1.png?raw=true)

The code tests the CAS logic and all logic levels of the multiplexers and runs the tests through 20 passes. 


## Usage

The HEX file is provided which needs to be uploaded your Arduino Mega 2560 using [avrdude](https://github.com/avrdudes/avrdude)

The output is displayed via the serial monitor at 115200 baud so it would also be useful to install [Arduino IDE](https://www.arduino.cc/en/software)

See the software folder for instructions for uploading using avrdude

Once the code is uploaded remove power from the Arduino and insert the chip to be tested. 
Note the chip orientation and connnfirm it's correct before applying power. 

Open the serial monitor and view outpout. The PASS/FAIL LED's will also alternate while under test, and at the end of the test the PASS / FAIL LED will show the result. 


##  Shield

The gerber files for the shield can be found under hardware/gerbers

![ZXMux Tester Shield](https://github.com/MyRetroStore/ZXMUX-Tester/blob/main/hardware/ZXMux%20Tester%20Shield.jpg?raw=true)

## BOM
| Reference | Value |
| ------ | ------ |
| Pass | Green LED 0805 |
| Fail | Red LED 0805 |
| R1/R2 | 2k2 0805 Resistors |
| U1 | 40 Pin ZIF Socket |
| SW1 | Push Button Switch 6x6x6 |
| | 2.54mm SIL Male Headers

## Purchasing

If you don't want build the shield yourself, assembled shields can be purchased from:
- [MyRetroStore](https://myretrostore.co.uk/)
- [eBay](https://www.ebay.co.uk/str/myretrostoreuk)

## License
CC BY-NC-SA 4.0


[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/H2H8RDX9W)

