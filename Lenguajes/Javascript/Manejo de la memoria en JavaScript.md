# Manejo de la memoria en JavaScript

Un programa divide la memoria asignada en dos grandes partes:

* **Heap**: Memoria destinada para las tareas inmediatas de la carga inicial.
* **Call-Stack**: Memoria destinada a almacenar operaciones a ejecutarse "a destiempo" de la ejecucion del script.

Un programa JavaScript atraviesa dos fases:

1. Primero, se ejecuta el script de inicio a fin, ocupa el heap. En esas acciones iniciales, se puede agregar al Call-Stack funciones para ser ejecutadas en determinadas condiciones.
2. Cuando dichas condiciones se sumplen, pasan a la cola de llamadas (**queue**) para ser ejecutadas una a una.

## Heap

La memoria dinámica que se almacena en el heap es aquella que se utiliza para almacenar datos que se crean en el medio de la ejecución de un programa. En el Heap se encuentran variables y constantes, funciones definidas en el ambito global y objetos creados.
## Call Stack

El Call Stack (pila de llamadas) es una estructura de datos dinámica que almacena información sobre las funciones activas de un programa. En esta estructura, se almacena información sobre las funciones y subrutinas que se están ejecutando, que están pausadas o que deban ser ejecutadas en determinado momento.

Su principal función es la capacidad de ejecutar varias funciones en paralelo e ir haciendo el seguimiento del estado de cada una de ellas.

En el call stack se encuentran event listeners y funciones que siguen el patron Callback.

Todo proceso que se ejecuta desde el call-stack lo llamamos **proceso asincronico**. Un proceso asincronico es un conjunto de tareas asincronicas.