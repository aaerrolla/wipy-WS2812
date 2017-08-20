Wipy-LoPy-MicroPython WS2812 driver
=========================

Wipy-LoPy-MicroPython driver for WS2812, WS2812B, and compatible RGB LEDs. These are
popular RGB LEDs used for example in AdaFruit NeoPixels rings, strips, boards,
etc.

Driver has been tested with up to 144 LEDs (for now) but it
should work with much more LEDs.

Installation
------------

Copy `ws2812.py` file to your WiPy 2.0.

Usage
-----

```
from ws2812 import WS2812
chain = WS2812(ledNumber=144, brightness=100, dataPin='P22' ) # dataPin only for Lora - not tested
data = [
    (255, 0, 0),    # red
    (0, 255, 0),    # green
    (0, 0, 255),    # blue
    (85, 85, 85),   # white
]
chain.show(data)
```

Wiring
------

WS2812 driver is using SPI bus. Connect your LED's input wire to the SPI bus 0, MOSI is
  * WiPy: pin P11 (G22 on Expansion board v2.1A)
  * LoPy: pin P22 by default (G9 on extension board)

Connect LED's power and ground wires to VIN and GND.
The same applies for LED rings, stripes, etc. (they have always one input wire).

USB may be insufficient for powering lots of RGB LEDs. You may need to use
additional power source.

More info & Help
----------------

WiPy 2.0 firmware update: https://docs.pycom.io/pycom_esp32/pycom_esp32/firmware.html#firmware-upgrade

WiPy 2.0 hardware pinout: https://www.pycom.io/wp-content/uploads/2016/11/wipy_pinout.pdf

You can check more about the MicroPython project here: http://micropython.org

Discussion about this driver: http://forum.micropython.org/viewtopic.php?f=5&t=394

Changelog
---------

* 2.0 - Add support for WiPy 2.0
* 1.1 - Add support for LoPy
* 1.0 - First release.

Credit
------
Based on : https://github.com/JanBednarik/micropython-ws2812
