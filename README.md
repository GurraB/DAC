# DAC
A USB DAC

This is my take on an USB DAC. 

Theoretical specs:
- 16 bit resolution
- fs = 44.1 kHz
- Signal to noise ratio: 127 dB
- THD+N: 0.0004%

Components:

- TI PCM2707c http://www.ti.com/lit/ds/sbfs036b/sbfs036b.pdf
- TI PCM1794a http://www.ti.com/lit/ds/symlink/pcm1794a.pdf
- TI OPA2134 http://www.ti.com/lit/ds/symlink/opa2134.pdf
- TI LM2662 http://www.ti.com/lit/ds/symlink/lm2663.pdf
- TI TPS60501 http://www.ti.com/lit/ds/symlink/tps60500.pdf

This was designed in EAGLE CAD. It is the first PCB I have ever made. The PCM2707c is used as an USB interface, it is automatically detected as a DAC by windows (Linux might need some drivers). The PCM2707c converts the USB signal to i2s and sends it to the PCM1794a. PCM1794a is a high quality DAC that generates the output signal. The signal is then sent to the operational amplifier.

The bottleneck in the system is the PCM2707c since it can only accept 16 bit audio signal.

Future work:
This is the first design that I have made to see if I can make a simple DAC to begin with. In the future I have plans to add an ESP32 to allow for bluetooth connectivity. I have also thought about adding a Raspberry Pi Zero W that can act as a spotify connect device.

Current status:

The PCB is manufactured and the components are soldered on, I have not tested the board yet.

![Picture of the schematic](https://github.com/GurraB/DAC/blob/master/DAC_sch.PNG)
![Picture of the board layout](https://github.com/GurraB/DAC/blob/master/DAC_brd.PNG)

Design is based upon http://users.abo.fi/jskata/JEDAC/
