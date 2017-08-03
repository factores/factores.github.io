---
layout: post
title:  "Programación de Arduino nano [atmega328p] en C"
date:   2017-05-10 18:39:22
comments: true
categories: electronica
tags: auto
---
Código de prueba en C
---------------------
{% highlight c %}
#include <avr/io.h>
#include <util/delay.h>
 
#define BLINK_DELAY_MS 1000
 
int main (void)
{
 /* set pin 5 of PORTB for output*/
 DDRB |= _BV(DDB5);
 
 while(1) {
  /* set pin 5 high to turn led on */
  PORTB |= _BV(PORTB5);
  _delay_ms(BLINK_DELAY_MS);
 
  /* set pin 5 low to turn led off */
  PORTB &= ~_BV(PORTB5);
  _delay_ms(BLINK_DELAY_MS);
 }
}
{% endhighlight %}


Comando en terminal Linux para cargar código al "nano"
------------------------------------------------------

{% highlight bash %}
$ avr-gcc -Os -DF_CPU=16000000UL -mmcu=atmega328p -c -o led.o led.c
$ avr-gcc -mmcu=atmega328p led.o -o led
$ avr-objcopy -O ihex -R .eeprom led led.hex
$ avrdude -F -V -c arduino -p ATMEGA328P -P /dev/ttyACM0 -b 57600 -U
{% endhighlight %}
