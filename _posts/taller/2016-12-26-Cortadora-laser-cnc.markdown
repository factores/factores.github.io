---
layout: post
title:  "Cortadora/grabadora laser CNC"
date:   2016-12-26 18:39:22
comments: true
categories: taller
tags: elec laser
---
Intérprete de gcode
-------------------

Comprobación

{% highlight bash %}
sudo avrdude -c arduino -b 57600 -p atmega328p -P /dev/ttyUSB0 -vv
{% endhighlight %}

Instalación

{% highlight bash %}
sudo avrdude -F -V -c arduino -b 57600 -p atmega328p -P /dev/ttyUSB0 -U flash:w:grbl.hex 

avrdude: AVR device initialized and ready to accept instructions

Reading | ################################################## | 100% 0.00s

avrdude: Device signature = 0x1e950f
avrdude: NOTE: FLASH memory has been specified, an erase cycle will be performed
         To disable this feature, specify the -D option.
avrdude: erasing chip
avrdude: reading input file "grbl.hex"
avrdude: input file grbl.hex auto detected as Intel Hex
avrdude: writing flash (31034 bytes):

Writing | ################################################## | 100% 9.45s

avrdude: 31034 bytes of flash written

avrdude: safemode: Fuses OK

avrdude done.  Thank you.
{% endhighlight %}

Conversor a gcode
-----------------

Plug-in de raster a gcode en inkscape.

Emisor de gcode
---------------

Estructura
----------

Drivers de los motores paso a paso
----------------------------------