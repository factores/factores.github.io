---
layout: post
title:  "Conexión a la placa Orange Pi por el puerto serie"
date:   2018-07-10 18:39:22
comments: true
categories: electronica
tags: auto
---
Pines de conexión
-----------------



Conectaremos nuestro ordenador a un FT232RL FTDI USB, conectando los pines de TX, RX y GND según se indica en la imagen a los pines de la Orange Pi.
{% highlight bash %}
TX  -> RX
RX  -> TX
GND -> GND
{% endhighlight %}

![Pines de conexión Orange Pi]({{ site.url }}/img/orange_pi_serial.png){:.image}




Comando en terminal Linux para acceder por consola al puerto serie
------------------------------------------------------------------

Conectaremos el USB del FT232RL y lanzaremos un comando para ver qué puerto se le asigna.

{% highlight bash %}

$ dmesg
...
[ XX.XXXXXX] usb 1-10: FTDI USB Serial Device converter now attached to ttyUSB0
....
{% endhighlight %}

En nuestro ejemplo lo asocia al ttyUSB0, nuestro dispositivo sera /dev/ttyUSB0. Como usuario normal no tenemos acceso a este dispositivo y no es recomendable acceder como superusuarios, por lo tanto añadiremos nuestro usuario al grupo dialout.

{% highlight bash %}
$ sudo usermod -a -G dialout nuestro_usuario
{% endhighlight %}

Y ahora ejecutaremos el programa screen.

{% highlight bash %}
$ screen /dev/ttyUSB0 115200
{% endhighlight %}
