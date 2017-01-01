# EthernetIndustruino
If you are using the Industruino Ethernet module, you will need this library which is based on the standard Arduino Ethernet library. The Ethernet module is connected over SPI, so we also need the SPI library.
```
#include <SPI.h>
#include <EthernetIndustruino.h>
```
The Ethernet module also includes FRAM; see the example in the library on how to use this. If you want to use the FRAM together with the Ethernet, there is no need to include the SPI settings as in the FRAM example, because this is taken care of in the Ethernet library. So you can just include the 2 libraries with the above 2 lines; DO NOT include the SPI settings as in the FRAM example:
```
//Setting up the SPI bus -- NO NEED when using the EthernetIndustruino library
SPI.begin();
SPI.setDataMode(SPI_MODE0);
SPI.setBitOrder(MSBFIRST);
SPI.setClockDivider(SPI_CLOCK_DIV2);
```

When using the Ethernet module with the Industruino PROTO, it is important to be aware of the I/O pins it is using, and which should not be used for other I/O functions:

| IDC pin number	| Module function	| Arduino pin	| Default connected	| Required for standard functions |
| --- | --- | --- | --- | --- |
| 1	|MISO	| D14	| yes	| yes |
| 2	| +5V	| +5V	| yes	| yes |
| 3	| SCLK	| D15/SCLK	| yes	| yes |
| 4	| MOSI	| D16/MOSI	| yes	| yes |
| 5	| Ethernet CS	| D10	| yes	| yes |
| 6	| GND	| GND	| yes	| yes |
| 7	| SD CS	| D4	| yes	| yes |
| 8	| Ethernet ext reset	| D5	| no	| no |
| 9	| Ethernet IRQ	| D7	| yes	| no |
| 10	| FRAM CS	| D6	| yes	| yes |
| 11	| /	| D0/RX	| no	| no |
| 12	| /	| D1/TX	| no	| no |
| 13	| /	| D2/SDA	| no	| no |
| 14	| /	| D3/SCL |	no	| no |
