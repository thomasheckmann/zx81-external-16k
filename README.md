# zx81-external-16k
Simple and compact external 16K RAM interface for the ZX81 with WRX compability. The interface is made using THT components, making it easy for everyone to make. The interface for now is only using 16K from the 62256 memory chip, using the other half 16K might be added on later version. I might also consider making a SMD version, making it even smaller in size :-)

| SCHEMA | PCB |
| ------ | --- |
|<img width="500" src="https://github.com/thomasheckmann/zx81-external-16k/assets/14136378/13aac0e5-a740-411d-8db7-992cb222da2b">|<img width="500" src="https://github.com/thomasheckmann/zx81-external-16k/assets/14136378/c1618e65-fe65-4309-99b0-8c6cdfef9aad">|

## version 1.0
The PCB arrived, so I populated it with some components (all written on the silkscreen).

![image](https://github.com/thomasheckmann/zx81-external-16k/assets/14136378/9aa3a963-2a5f-4a25-a5a8-68c8066c61e9)

BOM for v1.0 (16K only)
- LED 3mm
- Resistor 470 Ohm
- Resistor 4K7 Ohm
- 2 x Ceramic capacitor 100nF, P2,54
- 2 x Diode 1N4148
- 74LS00
- RAM 62256 or similar
- ZX81 Edge Connector or my [ZX81 Bus Extender](https://github.com/thomasheckmann/zx81-bus-extender)
  
NOTE: WRX hi-res, to get full support for hi-res WRX a cercamic capacitor is needed between PIN 20 (CS) and GND. In this build with a KM62256ALP-10 a 1,2nF ceramic capacitor should be fitted. 

The value for the capacitor for different 62256 SRAM chips tested with [STARFIGHT](https://problemkaputt.de/starfigh.htm)

- KM62256ALP-10, 1.2nF

## version 1.1 - full 32K support, with data in the 32-48K area.
Most version for internal 32K RAM puts the extra 16K at the top, 48 to 64K - but this is not what most 32K program expects. The 32K programs I have found expect the 32K from 16K, which requires some extra logic - another issue with this configuration is that normaly the ROM is mirrored between 32 and 48K, which means the ROM has to be disabled when the ZX81 access this part of the memory. I also decided to change the diodes from 1N4148 to BAT85 as suggested in general for this type of usage.

A little prototyping based on the v1.0 board - and yes, 32K from adress 16384 is all good here tested with Beamrider that require 32K and WRX :-)
| <!---> | <!---> |
| ------ | ------ |
|<img width="500" src="https://github.com/thomasheckmann/zx81-external-16k/assets/14136378/63b1f332-3907-4595-98db-b0b84c26ef5d">|<img width="500" src="https://github.com/thomasheckmann/zx81-external-16k/assets/14136378/3de21f3b-935e-4c53-96fe-5fa362c691e3">|

Programs tested with success so far:
- [Beamrider](https://problemkaputt.de/beamride.htm), 32K and WRX graphics 
- [MaxDemo](https://demozoo.org/productions/159644/), 32K and WRX graphics (impressive 320x240 resolution)
- [Cross Snake](https://github.com/Fabrizio-Caruso/CROSS-LIB/releases/tag/XSnake2.0), 32K and WRX
- [Cross Chase](https://github.com/Fabrizio-Caruso/CROSS-LIB/releases/tag/WRX), 32K and WRX
- [Space Invaders](https://splintergu.itch.io/space-invaders-for-zx81-wrx), 32K and WRX

32K Programs NOT working - as they require internal modification in order to run M/C above 32K area.
- [The Crystal Frog](https://www.sinclairzxworld.com/viewtopic.php?t=334)

| <!---> | <!---> |
| ------ | ------ |
|<img width="500" src="https://github.com/thomasheckmann/zx81-external-16k/assets/14136378/cc751cdf-ddca-4291-aa99-5541b012a066">|<img width="500" src="https://github.com/thomasheckmann/zx81-external-16k/assets/14136378/36ffc1d7-7bf1-4760-bd7d-c64a76275ac7">|

BOM for v1.1 (32K, continously from adress 16384)
- LED 3mm
- Resistor 470 Ohm
- Resistor 4K7 Ohm
- Resistor 10K Ohm
- 2 x Ceramic capacitor 100nF, P2,54
- 1 x Ceramic capacitor 1,2nF, P2,54
- 2 x Diode BAT85
- 74LS00
- 74LS32
- RAM 62256 or similar
- ZX81 Edge Connector or my [ZX81 Bus Extender](https://github.com/thomasheckmann/zx81-bus-extender)

The interface has been tested with the following 32K SRAM chips, all running Beamrider perfectly.
- UM62256E-70LL
- HM62256BLP-10
- AS6C62256-55PCN
