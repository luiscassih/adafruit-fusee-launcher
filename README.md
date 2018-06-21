# adafruit-fusee-launcher
Fusee Launcher for the Adafruit Feather M0 with deep sleep, SSD1306 and battery indicator support

Based on https://github.com/Wovelon/sam-fusee-launcher and https://github.com/atlas44/sam-fusee-launcher
This works with a SSD1306 display connected to the Adafruit Feather M0 Adalogger.
This doesn't differ to much from the Wovelon's version, I customized the way it goes to deep sleep and added a battery indicator without the need of the screen.

--------------------
Whe the board start, it checks the battery level.
* If it's between 4.26V and 4.1V it will blink the led #8 for 2 seconds.
* 1 seconds if it's between 4.1V and 3.8V.
* 200ms if it's between 3.8V and 3.4V.

After that it will start fusee and will send the payload. Then it will go to deel sleep mode until the boton reset is pushed again.

If the board is powered on but with no intention of inyect a payload it will go to sleep automatically after 20 seconds.


For now it has the Hekate 2.3 payload in payload.h with LayeredFS support, based on https://github.com/TheDgtl/hekate/releases/tag/v2.3-fusee

https://github.com/tumGER/SDFilesSwitch/releases