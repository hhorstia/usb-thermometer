usb-thermometer: TEMPer1
===============

A linux driver for reading the temperature from an inexpensive USB thermometer you can buy for example from eBay
for about ~10 euros.

Code originally written by [Robert Kavaler](http://relavak.wordpress.com/2009/10/17/temper-temperature-sensor-linux-driver/).

Installation instructions (Debian / Ubuntu / Raspbian)
---------
0. If not installed, install these necessary packages `sudo apt-get install libusb-dev libusb-1.0-0-dev`
1. Compile with `make`
2. Run with `sudo ./temper`
3. To fix a systematic error in the measurements, edit the source file line 58 (`const static int offsetDegrees = 0;`)
to a suitable amount in degrees (celcius) you want to change the measurement result with.
Then compile again with `make`.

Changelog
---------

### 0.0.3
* If outputting only deg C or dec F, do not print the date (to make scripting easier) (by Patrick Skillen (pskillen@gmail.com))
* Added constant to correct for systematic error in measurement (by Steffan Slot (see http://dev-random.net/temperature-measuring-using-linux-and-raspberry-pi/))

### 0.0.2
* The original version of pcsensor0.0.1 contains a bug: temperatures below zero overflow and instead of displaying -1.3 C, 254.3 C is displayed. This is a quick and dirty hack to fix it.
http://bailey.st/blog/2012/04/12/dirt-cheap-usb-temperature-sensor-with-python-sms-alerting-system/
