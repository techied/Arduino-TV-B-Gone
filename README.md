# README.md update history:  
Readme Last Updated: 17 Oct. 2019

# Current Code Version & History:  

Semver (http://semver.org/) VERSION HISTORY (newest on top):  
(date format: yyyymmdd; ex: 20161022 is 22 Oct. 2016)  
 - 20191017 - v1.4 - Simplification of sketch (no external button or interrupts) and addition of REGION definition
 - 20161022 - v1.3 - Semver versioning implemented; various code updates, clarifications, & comment additions, and changes to fix PROGMEM incompatibilities so it will now compile with latest versions of gcc compiler; also improved blink indicator routines & added the ability to stop the code-sending sequence once it has begun; by Gabriel Staples (http://www.ElectricRCAircraftGuy.com)  
 - 20101023 - v1.2 - Latest version posted by Ken Shirriff on his website here (http://www.righto.com/2010/11/improved-arduino-tv-b-gone.html) (direct download link here: http://arcfn.com/files/arduino-tv-b-gone-1.2.zip)  
 - 20101018 - v1.2 - Universality for EU (European Union) & NA (North America) added by Mitch Altman; sleep mode added by ka1kjz  
 - 2010____ - v1.2 - code ported to Arduino; by Ken Shirriff  
 - 20090816 - v1.2 - for ATtiny85v, by Mitch Altman & Limor Fried (https://www.adafruit.com/), w/some code by Kevin Timmerman & Damien Good  

# Description:  
This code is the TV-B-Gone library ported to run on the Arduino. I have simplified the original sketch. Hardcoded region switch, no button implementation (if you want to try again, hit the reset button) no interrupt. There is also a 3D model for a case you can use which nicely fits an IR LED, 9V battery, Arduino Nano, and SPST on/off switch. Model To Be Uploaded.

# Background:
-see Arduino_TV_B_Gone.ino for latest version history & more details. 

Updated code to fix PROGMEM incompatiblities--now works with latest versions of gcc compiler & Arduino IDE
-with other improvements also
By Gabriel Staples (http://www.ElectricRCAircraftGuy.com)

This port to Arduino is by Ken Shirriff.  
For background details on the Arduino port, how to build it, and how to use it, see:  
 * http://www.arcfn.com/2009/12/tv-b-gone-for-arduino.html and here:
 * http://www.righto.com/2010/11/improved-arduino-tv-b-gone.html (newer)

For information on the original TV-B-Gone see:  
http://www.tvbgone.com/. Mitch Altman is the inventor of the original TV-B-Gone.    

The original code is:  
TV-B-Gone Firmware version 1.2  
 for use with ATtiny85v and v1.2 hardware  
 (c) Mitch Altman + Limor Fried 2009  
 Last edits, August 16 2009  

Added universality for EU or NA, and Sleep mode to Ken's Arduino port.  
 -- Mitch Altman  18-Oct-2010  
Thanks to ka1kjz for the code for adding Sleep  
    <http://www.ka1kjz.com/561/adding-sleep-to-tv-b-gone-code/>  

With some code from:  
Kevin Timmerman & Damien Good 7-Dec-07  

# License:  
Distributed under Creative Commons 2.5 -- Attribution & Share Alike  

# CIRCUIT:  
-NB: SEE "main.h" TO VERIFY DEFINED PINS TO USE  
The hardware for this project uses an Arduino:  
 * Connect an IR LED to pin 3 (IRLED).  
 * Connect a visible LED to the pin 13 (or use the built-in LED in many Arduinos).  

# User Manual:  
## Background Settings:  
 * The TV-B-Gone for Arduino can use either the EU (European Union) or the NA (North America) database of POWER CODES  
 * EU is for Europe, Middle East, Australia, New Zealand, and some countries in Africa and South America  
 * NA is for North America, Asia, and the rest of the world not covered by EU  
 * Adjust "REGION" in "main.h" to specify your region database. 1 for NA, 0 for EU.
 * Serial debugging output can be activated by setting "DEBUG 0" to "DEBUG 1" in "main.h"  
 * For 8 MHz Arduinos, define DELAY_CNT as 11 in "main.h," or use 25 for 16 MHz Arduinos.
  * Fine-tune if necessary  
 * All IR codes are defined in "WORLD_IR_CODES.h"  
  * We'd love to have you add more! Just be careful NOT to duplicate codes please!  
  
## Use:  
 * When the device is first powered on, it will quick-flash (30ms on-time followed by 250ms off-time) 3 times if set to output NA (North America) codes, or 6 times for EU (European Union) codes. See the end of the "setup()" function.  
 * Once on, all power codes will be sent sequentially, one after the other.
 * After each individual IR power code is sent, a quick flash will occur on the visible LED (30ms on-time) to indicate a code was just sent. Therefore, as the codes are sent, you will see the visible LED flash repeatedly.  
 * Once all codes have been sent (which takes around 60 sec or so), the visible LED will remain on to indicate the program has ended.
 * To send the codes again, press the RESET switch on your Arduino or simply power cycle.



