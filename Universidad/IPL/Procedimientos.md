# Procedimientos

Un procedimiento es una nueva instrucción definida por el usuario que representa la solución de una parte del problema. Un procedimiento es un subprograma que realiza una tarea especifica. Consiste en definir una nueva instrucción a partir de las instrucciones primitivas del lenguaje, que luego podemos reutilizar.

Un procedimiento en Qdraw se define mediante la palabra “procedimiento”, seguida de un nombre (no puede contener espacios y comienza con mayúscula), paréntesis vacíos, la sección de documentación (sintaxis de comentarios) y su correspondiente bloque de código entre llaves.

![[Pasted image 20230426172740.png]]
Cada procedimiento debe tener su correspondiente documentación.

![[Pasted image 20230426172800.png]]

## Llamar(invocar) procedimientos

Cada procedimiento tiene dos etapas:

* Definicion: se define con un nombre, la sección de documentación y el bloque de código correspondiente al algoritmo que resuelve el problema. 

* Invocacion/llamado:  Se **invoca** a traves de su nombre seguido de parentesis,  y desde cualquier bloque de codigo del programa o desde otro procedimiento. Un procedimiento se define una sola vez y puede ser reinvocado las veces que sean necesarias.

Al momento de ejecutar el programa, en el lugar desde donde se invoca al procedimiento, se ejecuta el bloque de código correspondiente en su definición.