---
layout: post
title:  "Cortadora laser CNC"
date:   2016-12-26 18:39:22
comments: true
categories: electronica
tags: elec laser
---
Intérprete código GCODE
-----------------------

{% highlight c %}

#include <stdio.h>
#include <math.h>

double pitagoras(double a, double b){
return sqrt(a*a+b*b);
}

main(){

printf("valor de c %f\n",pitagoras(3,4));
return(0);
}
{% endhighlight %}

Drivers de los motores paso a paso
----------------------------------

Generador de código GCODE
-------------------------

Plug-in de raster a gcode en inkscape.

Estructura
----------
