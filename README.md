# zx81-external-16k
Simple and compact external 16K RAM interface for the ZX81 with WRX compability. The interface is made using THT components, making it easy for everyone to make. The interface for now is only using 16K from the 62256 memory chip, using the other half 16K might be added on later version. I might also consider making a SMD version, making it even smaller in size :-)

| SCHEMA | PCB |
| ------ | --- |
|<img width="410" height="410" src="https://github.com/thomasheckmann/zx81-external-16k/assets/14136378/13aac0e5-a740-411d-8db7-992cb222da2b">|<img width="410" height="410" src="https://github.com/thomasheckmann/zx81-external-16k/assets/14136378/c1618e65-fe65-4309-99b0-8c6cdfef9aad">|

## version 1.0
The PCB arrived, so I populated it with some components (all written on the silkscreen).
- LED 3mm
- Resistor 470 Ohm
- Resistor 4K7 Ohm
- 2 x Ceramic capacitor 100nF, P2,54
- 2 x Diode 1N4148
- 74LS00
- RAM 62256 or similar
- ZX81 Edge Connector or my [ZX81 Bus Extender](https://github.com/thomasheckmann/zx81-bus-extender)
  
NOTE: WRX hi-res, to get full support for hi-res WRX a cercamic capacitor is needed between PIN 20 (CS) and GND. In this build with a KM62256ALP-10 a 1nF ceramic capacitor should be fitted. 

The value for the capacitor for different 62256 SRAM chips tested with [STARFIGHT](https://problemkaputt.de/starfigh.htm)

- KM62256ALP-10, 1.2nF

## version 1.1 - full 32K support
Most version for internal 32K RAM puts the extra 16K at the top, 48 to 64K - but this is not what most 32K program expects. The 32K programs I have found expect the 32K from 16K, which requires some extra logic - another issue with this configuration is that normaly the ROM is mirrored between 32 and 48K, which means the ROM has to be disabled when the ZX81 access this part of the memory. I also decided to change the diodes from 1N4148 to BAT85 as suggested in general for this type of usage.

A little prototypinh based on the v1.0 board - and yes, 32K from adress 16384 is all good :-)
[PICTURE]

Programs tested with success so far:
- [Beamrider](https://problemkaputt.de/beamride.htm), 32K and WRX graphics 
- [MaxDemo](https://demozoo.org/productions/159644/), 32K and WRX graphics (impressive 320x240 resolution)
- [Cross Snake](https://github.com/Fabrizio-Caruso/CROSS-LIB/releases/tag/XSnake2.0), 32K and WRX
- [Cross Chase](https://github.com/Fabrizio-Caruso/CROSS-LIB/releases/tag/WRX), 32K and WRX
- [Space Invaders](https://splintergu.itch.io/space-invaders-for-zx81-wrx), 32K and WRX

32K Programs NOT working:
- [The Crystal Frog](https://www.sinclairzxworld.com/viewtopic.php?t=334)

[PICTURE OF SCHEMA, PCB and Final build]
