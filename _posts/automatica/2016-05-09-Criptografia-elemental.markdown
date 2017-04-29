---
layout: post
title:  "Criptografía elemental"
date:   2016-07-08 18:39:22
comments: true
categories: electronica
tags: auto
---
Definición de código criptográfico
----------------------------------

Un código definido en K, M y C con un par de de algoritmos eficientes* (E,D) donde:

$$E=K\times M\rightarrow  C$$

$$D=K\times C\rightarrow M$$

Además, debe cumplirse que:
{% raw %}
\\[\forall \,m \in M, k\in K: D(k,E(k,m))=m \\]
{% endraw %}
*Eficiente aquí se refiere a que la ejecución de estos algoritmos debe producirse en tiempo polinomial.

El algoritmo E puede tener una componente aleatoria en su salida pero el algoritmo D siempre es determinista.

Ejemplo característico: Libreta de un sólo uso (*One time pad*)
---------------------------------------------------------------
El "tamaño" del mensaje m, la clave k y el cifrado c son iguales a n.

{% raw %}
$$M={\left\{0,1\right\}}^n, K={\left\{0,1\right\}}^n,C={\left\{0,1\right\}}^n$$
{% endraw %}
El algoritmo de cifrado y de descifrado es la operación o-exclusiva (XOR).

Cifrado: 

$$c=k\oplus m$$

Descifrado: 

$$m=k\oplus c$$

Teoría de la seguridad en la información (Shanon 1949)
------------------------------------------------------

La idea intuitiva es que c no debe revelar información sobre m. Sin embargo la definición formal es más compleja como se verá a continuación.

Un código de cifrado tiene **secreto perfecto** si:
{% raw %}
$$\forall \,m_0,m_1\, con\, y\,\forall c\in C$$

$$Longitud(m_0)=Longitud(m_1)$$

$$P\left[ E\left(k,m_0\right)=c\right]=P\left[ E\left(k,m_1\right)=c\right]$$

{% endraw %}

k es uniforme en el espacio K, esto es $$k \xleftarrow{R} K$$

Teorema: Para que un código posea "secreto perfecto"
----------------------------------------------------

$$\mid K\mid\geq \mid M\mid$$

Es decir, la longitud de k debe ser mayor o igual a la longitud de m, el código *one time pad* ---en adelante OTP--- cumple la condición el el límite.

Cifrador de flujo (*Stream cipher)*
-----------------------------------

Aquí la idea es remplazar la k aletoria de OTP un una pseudo-aleatoria. Un generador de claves pseudo-aleatorias o PRG (*Pseudo Random Generator*) es una funcion G que:

$$G: \left \{ 0,1 \right \}^{s} \rightarrow \left \{ 0,1 \right \}^{n} ; s\ll n  $$

El algoritmo que genera esta función debe ser eficiente y su salida debe parecer aleatoria ---más sobre esto después---. Esta nueva clave sustituirá a la k usanda en el OTP:

Cifrado: 

$$c=G\left(k\right)\oplus m$$

Descifrado: 

$$m=G\left(k\right)\oplus c$$

Tal y como indicó Shannon este tipo de cifrado no tiene secreto perfecto y por lo tanto habrá que definir lo que se considera un generador G seguro, mientras tanto veamos la definición de un generador G impredecible.

Para que un generador G sea impredecible no tiene que existir un algoritmo eficiente A que conocidos los i primeros bits generados permita calcular los n-i bits restantes. 

$$\exists i : G\left(k \right )\mid _{1,...i}\,\xrightarrow{algoritmo}G\left(k \right )\mid _{i+1,...n} $$

Matemáticamente un generador es predecible si existe un algoritmo A tal que...

$$\exists A\, y\, \exists  \left [  1\leqslant i\leqslant (n-1)\right ]:  P\left [  A\left\{G\left(k \right )\mid _{1,...i} \right \}=G\left(k \right )\mid _{i+1} \right ]\geqslant \left ( 1/2 +\varepsilon \right ) $$

Con:

$$k \xleftarrow{R} K$$ y un $$\varepsilon$$ no despreciable.

Por lo tanto, un algoritmo será impredecible si no es predecible ---¡vaya vuelta para contar esto!---.

**Notas finales sobre qué es despreciable:**

*En la práctica:*

$$ \varepsilon $$ se considera no despreciable si $$ \varepsilon \geqslant \frac{1}{2^{30}} $$ (1GB de datos) y se considera despreciable si  $$ \varepsilon \geqslant \frac{1}{2^{80}} $$

*En teoría:*

$$\varepsilon$$ es una función tal que $$\varepsilon:Z^{\geq 0}\rightarrow R^{\geq 0}$$

$$ \varepsilon $$ se considera no despreciable si $$ \exists d:\varepsilon\left(\lambda \right )\geqslant 1/\lambda^{d}$$ y se considera despreciable si  $$\forall d, \lambda\geqslant \lambda_d: \varepsilon \left(\lambda \right )\leqslant 1/\lambda^{d}$$

---Ejemplo despreciable: $$\varepsilon \left(\lambda \right )=1/2^{_{\lambda}}$$

Para un d dado existe una $$\lambda$$ tal que satisface la ecuación.

---Ejemplo no despreciable: $$\varepsilon \left(\lambda \right )=1/\lambda^{_{1000}}$$

En el ejemplo se comprueba que si se toma una $$\lambda$$ mayor a 1000 la condición no se cumple.

