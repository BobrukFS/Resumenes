# Anidacion en Sass
Sass le permitirá anidar sus selectores CSS de una manera que siga la misma jerarquía visual de su HTML. Tenga en cuenta que las reglas demasiado anidadas darán como resultado un CSS SOBRECUALIFICADO que podría resultar difícil de mantener y generalmente se considera una mala práctica.

![[Pasted image 20221214224837.png]]

**Dato**: Evitar anidar bastante.

El **ampersand(&)** significa que vamos añadir el selector padre cuando anidamos. Ejemplo:

![[Pasted image 20221214224900.png]]

Podemos utilizar **#{&}** para hacer referencia a que el elemento, pertenece dentro del elemento que fui anidado.

![[Pasted image 20230512110131.png]]
![[Pasted image 20230512110113.png]]