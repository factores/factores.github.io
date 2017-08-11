---
layout: post
title:  "Osciloscopio Hantek en Debian"
comments: true
categories: ingenieria
tags: elec
---

Drivers
-------

Instalación
-----------

Seguir instalación del [enlace](https://github.com/OpenHantek/openhantek).

**Paquetes necesarios para la instalación**

* CMake 3.5+
* Qt 5.3+
* FFTW 3+ 
* libusb 1.x 

CMake 3.5+ no está disponible, lo instalaremos de la web oficial. Primero eliminamos la versión actual.

{% highlight bash %}
sudo apt-get purge cmake
{% endhighlight %}

Descargamos la última versión de *cmake*.

{% highlight bash %}
mkdir ~/temporal
cd ~/temporal
wget https://cmake.org/files/v3.9/cmake-3.9.4.tar.gz
tar -xzvf cmake-3.9.4.tar.gz
cd cmake-3.9.4/
{% endhighlight %}

Instalamos las fuentes ejecutando lo siguiente.

{% highlight bash %}
./bootstrap
make -j4
sudo make install
{% endhighlight %}

Finalmente comprobamos la versión.

{% highlight bash %}
cmake --version
Results of cmake --version:
cmake version 3.9.X
{% endhighlight %}

no está disponible en nuestra distribución por lo tanto deberemos usar los backports. Para añadirlos editamos */etc/apt/source.list* para añadir la línea siguiente, teniendo la precaución de sustituir jessie por nuestra distribución.

{% highlight bash %}
deb http://ftp.debian.org/debian jessie-backports main
{% endhighlight %}

