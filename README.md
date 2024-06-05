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

The value for the capacitor for different 62256 SRAM chips tested:

- KM62256ALP-10, 1.2nF
