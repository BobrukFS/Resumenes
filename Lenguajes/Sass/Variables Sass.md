# Variables Sass

Las **variables** son una forma de almacenar informacion que desea reutilizar en su hoja de estilo. Puede almacenar cosas como colores, pilas de fuentes o cualquier valor de CSS que crea que querra utilizar. Sass usa el simbolo **$** para convertir algo en una variable.

![[Pasted image 20221214224551.png]]

Si tenemos muchas variables, para evitar confusiones podemos guardar todas las variables en un array de variables. Por ejemplo:

![[Pasted image 20221214224613.png]]

Donde en **map-get($map, key)**.

## Variables default

Las variables definidas con !default se pueden configurar al cargar un modulo con la regla @use. 

Para cargar un modulo con configuracion hay que escribir @use `<url>` with (`<variable>`: `<value>`, `<variable>`: `<value>`). Los valores configurados anularan los valores predeterminados de las variables. Solo se pueden configrar las variables escritas en el nivel superior de la hoja de estilo con una bandera.

![[Pasted image 20230511202744.png]]
![[Pasted image 20230511202802.png]]

**Dato:** Las variables de Sass, como todos los identificadores de Sass, tratan los guiones y guiones bajos como idénticos. Esto significa que `$font-size`y `$font_size`ambos se refieren a la misma variable. Este es un vestigio histórico de los primeros días de Sass, cuando solo permitía guiones bajos en los nombres de los identificadores. Una vez que Sass agregó soporte para guiones para que coincidieran con la sintaxis de CSS , los dos se hicieron equivalentes para facilitar la migración.

**Dato**: Las variables integradas por un modulo integrado no se pueden modificar. 

![[Pasted image 20230511202947.png]]

## Alcance de las variables

Las variables declaradas en el nivel superior de una hoja de estilo son globales, es decir, se puede acceder a ellas en cualquier parte de su modulo despues de haberlos declarados. Las variables que se declaran en bloques suelen ser locales y solo se puede acceder a ellos dentro del bloque en el que se declararon.

![[Pasted image 20230512022948.png]]
Las variables locales pueden incluso declararse con el mismo nombre que una variable global. Si esto sucede, en realidad hay dos variables diferentes con el mismo nombre: una local y otra global.

### Alcance del control de flujo

Las variables declaradas en las reglas de control de flujo tienen reglas de ámbito especiales: no sombrean las variables al mismo nivel que la regla de control de flujo. En cambio, simplemente asignan a esas variables. Esto hace que sea mucho más fácil asignar condicionalmente un valor a una variable o generar un valor como parte de un ciclo.

![[Pasted image 20230512023348.png]]

## Variables css vs sass

La diferencia reside en que las variables sass no las va a compilar con su nombre, si no que las va a mostrar con su valor real, lo que hace que tenga una compatibilidad 100% con todos los navegadores. Pero puedo utilizar ambas ya que eso se supone que no es un problema, porque las variables css tienen aproximadamente un 90% de compatibilidad.