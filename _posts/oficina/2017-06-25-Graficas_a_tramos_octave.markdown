---
layout: post
title:  "Gráfica definida a trozos en octave"
date:   2017-06-24 18:39:22
comments: true
categories: proyecto
tags: octave
---

Definimos el valor de la abscisa ‘x’ de 0 a 200 en pasos de 0.01

{% highlight octave %}
x = 0:0.1:200
{% endhighlight %}

Para definir la función a trozos multiplicamos el valor de la función en el tramo por una operación lógica que crea un vector de unos en el tramo que se cumple.

{% highlight octave %}
y = ...
  (0.0796                                ) .* (x < 100           ) + ...
  (127.32./(24-2.*(4-(x-102).^2).^0.5).^2) .* (x < 102 & x >=100 ) + ...
  (0.3183                                ) .* (x < 200 & x >=102 ) 
  {% endhighlight %}

Para mostrar la gráfica finalmente usaremos.

{% highlight octave %}
plot(x,y)
{% endhighlight %}
