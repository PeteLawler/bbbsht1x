bbSht1x
========
This module reads Humidity and Temperature from a Sensirion SHT1x sensor. It has been tested
both with an SHT11 and an SHT15.

It is meant to be used in a Beaglebone and depends on https://github.com/adafruit/adafruit-beaglebone-io-python.

The module raspberry-gpio-python requires root privileges, therefore, to run this module you need to run your script as root.

This a Beaglebone port of this library: https://bitbucket.org/lunobili/rpisht1x.git
which in turn is a port of this library: https://github.com/practicalarduino/SHT1x

Example Usage::

    from sht1x.Sht1x import Sht1x as SHT1x
    dataPin = 11
    clkPin = 7
    sht1x = SHT1x(dataPin, clkPin, SHT1x.GPIO_BOARD)
    
    temperature = sht1x.read_temperature_C()
    humidity = sht1x.read_humidity()
    dewPoint = sht1x.calculate_dew_point(temperature, humidity)
    
    print("Temperature: {} Humidity: {} Dew Point: {}".format(temperature, humidity, dewPoint))    

Release Notes
=============

* v0.1 2016/08/21 -- Initial fork
