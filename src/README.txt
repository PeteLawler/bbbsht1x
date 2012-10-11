========
rpiSht1x
========
This modules reads Humidity and Temperature from a Sensirion SHT1x sensor. It has been tested
both with an SHT11 and an SHT15.

It is meant to be used in a Raspberry Pi and depends on this module (http://pypi.python.org/pypi/RPi.GPIO/0.4.1a).

The module raspberry-gpio-python requires root privileges, therefore, to run this module you need to run your script as root.

This a Python/Raspberry Pi port of this library: https://github.com/practicalarduino/SHT1x

Example Usage::

    from sht1x.Sht1x import Sht1x
    dataPin = 11
    clkPin = 7
    sht1x = Sht1x(dataPin, clkPin)
    #Or sht1x = Sh1x.WaitingSh1x(dataPin, clkPin)
    temperature = sht1x.read_temperature_C()
    humidity = sht1x.read_humidity()
    dewPoint = sht1x.calculate_dew_point(temperature, humidity)
    print("Temperature: {} Humidity: {} Dew Point: {}".format(temperature, humidity, dewPoint))

Release Notes
=============

* v1.1, 11/10/2012 -- Added WaitingSht1x, dew point calculation and using v4 constants
  WaitingSht1x makes sure that no more than a query per second is performed on the sensor. This is
  in order to prevent the sensor from heating and skewing the temperature readings. 

* v1.0, 7/10/2012 -- Initial release.

