# Qdraw

El lenguaje consta de un tablero (una hoja cuadriculada) y un autómata, representado por un cabezal. El objetivo consiste enque el autómata se desplace por el tablero y ejecute acciones sobre sus casilleros. Las acciones que puede realizar son pintar y despintar. De esta manera se podrán realizar diferentes dibujos.

El tablero consiste en una superficie de tamaño variable (ancho y alto) con celdas. Cada celda puede estar en blanco o pintada de algún color. Sólo maneja los colores Negro, Rojo y Verde.

## Sintaxis

La mayoria de los lenguajes utilizan una sintaxis estricta que debe utilizarse para que el automata entienda las instrucciones que queremos darle.

Todo programa Qdraw inicia con la palabra reservada **programa**, seguida de un bloque de codigo con las instrucciones a ejecutar. **Palabra reservada** significa que debemos escribir esa palabra exactamente como lo indica su sintaxis y no se puede usar para otra cosa que no sea su definicion. Un **bloque de codigo**  es un conjunto de instrucciones que se agrupan de forma secuencial, colocandolas entre llaves.

![[Pasted image 20230426171305.png]]



## Primitivas

![[Pasted image 20230426171435.png]]

## Errores

### Errores sintacticos.

La sintaxis del lenguaje es estricta, si no respetamos la sintaxis existe un error sintáctico y el código es inválido. Es lo mismo que decir, que el código ni siquiera comienza a ejecutarse, pues está mal.

### Errores logicos.

En QDraw, si se realiza alguna acción inválida, el programa falla. Son aquellos que se dan como resultado de ejecutar un programa sobre un tablero inválido, como cuando el cabezal intenta moverse a una celda inexistente, o intenta despintar una celda que no está pintada.

## Documentacion

### Comentarios

Un [[Comentario]] en Qdraw estan delimitados por los siguientes caracteres:

**/\*…\*/**

Los comentarios pueden ocupar multiples lineas, y puede haber mas de uno en un mismo programa.



### Proposito

El proposito describe el objetivo del programa, lo que realiza, independientemente de como lo realiza. Es decir, comunica el que y no el como.  Por otra parte, ademas comunica el estado inicial, y el estado final al finalizar la ejecucion del programa. En Qdraw se debe decir donde inicia el cabezal y donde quedara el cabezal sobre el tablero al finalizar la ejecucion del programa. El proposito se coloca tanto en el programa como en cada procedimiento.

No interesa qué pasos realiza el cabezal para lograr el estado final. Sólo su objetivo. No describir el algoritmo.

![[Pasted image 20230426171949.png]]
![[Pasted image 20230426172206.png]]
**Dato:** Por convencion se asume que el cabezal inicia en la esquina inferior izquierda del tablero si no se especifica. Si no se especifica donde finaliza el cabezal luego de la ejecucion del programa, se entiende que el cabezal termina en el mismo lugar donde inicio (acciones que deben reflejarse en el codigo).

### Precondicion

La **precondición** es parte de la documentación del programa, y es aquello que el programa necesita / requiere sí o sí para cumplir con su propósito. Es decir, las condiciones con las que debemos contar, los requisitos necesarios, para pasar del estado inicial al estado final, luego de ejecutar el programa. Esto implica que si no tenemos en cuenta estas condiciones, el programa puede fallar o realizar otra cosa. No siempre hay precondiciones. Es documentación opcional. La precondicion se coloca tanto en el programa como en cada procedimiento.

![[Pasted image 20230426172338.png]]
![[Pasted image 20230426172345.png]]
Sin estos requisitos, al ejecutar el programa hace "BOOM".

Si mi programa solo tene instrucciones totales, no hace falta una precondicion, instrucciones totales puede ser pintar celda. Instrucciones no totales son el desplazamiento por ejemplo.

