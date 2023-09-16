
# Ciclo de vida de los programas

Se utilizan representaciones simbolicas para las instrucciones maquina, donde los codops se representan mediante abreviaturas, denominadas **nemotecnicos**, que indican la operacion en cuestion. Ejemplos:

![[Pasted image 20230911160816.png]]

Los operandos tambien suelen representarse simbolicamente. Por ejemplo, la instruccion ADD R, Y puede significar sumar el valor contenido en la posicion de datos **Y** al contenido del registro **R**. En este ejemplo, Y hace referencia a la direccion de una posicion de memoria, y R a un registro particular. La operacion se realiza con el contenido de la posicion y no con su direccion.

Este lenguaje simbolico se denomina **codigo fuente**, y el dispositivo que traduce este codigo simbolico al lenguaje de la computadora (**codigo maquina**, es decir, codigo binario) es el **ensamblador**, quien ademas, carga/guarda el programa en memoria principal. Al proceso de traducir del codigo fuente a codigo maquina se lo denomina **ensamblar** y si pasamos de codigo maquina a codigo fuente se llama **desensamblar**.

![[Pasted image 20230911161231.png]]

# Ejecucion de un programa

La ejecucion de un programa es la ejecucion ordenada de las instrucciones que lo componen, y la ejecucion de cada una respeta un **ciclo de ejecucion de instrucciones** que cuenta con 3 etapas:

* **Busqueda de instrucciones**: La UC se encarga de recuperar el codigo maquina completo de la instruccion que esta en memoria principal y ponerlo disponible en un registro de uso especifico de la CPU. Se nombra **Instruction Register** o IR. 
* **Decodificacion**: La UC Identifica la tarea que resuelve la instruccion y si requiere operandos, operadores. Por ejemplo, identifica los primeros 4 bits de la instruccion que esta en memoria que fue ensamblada para saber que operacion es.
* **Ejecucion**: Se traduce en que la UC delegue a otro circuito la realizacion de la tarea especifica para cada instruccion, por ejemplo en el caso de las instrucciones aritmeticas que son delegadas a la ALU ya que posee circuitos logicos. La ALU traduce el codigo maquina en acciones, y finaliza la tarea y le va a dar a la UC el resultado.

![[Pasted image 20230911161742.png]]

Ejemplo: Para escribir el programa que resuelva A=A-B se necesita poder escribir la instruccion: restar  LO-QUE-HAY-EN-B a LO-QUE-HAY-EN-A. Entonces surge la necesidad de tener una representacion binaria, que pueda ser entendida por la unidad de control, quien le dira a la ALU que debe activar una resta, y por lo tanto debe usar el circuito restador. Esa representacion se denomina **codigo maquina** y debe incluir en cada instruccion la siguiente informacion

* **Que operacion es**
* **Cuales son los operandos**
* **Donde se guarda el resultado**

En una computadora los valores de las variables deben ser mantenidos en registros de uso general. En este caso necesitaremos un registro para A y otro para B. El resultado se almacena en el registro A.


Resumen

El codigo maquina describe el programa en terminos comprensibles para el ser humano. El ensamblador traduce de codigo fuente a codigo maquina para que el programa pueda ser interpretado por la unidad de control, que convierte los codigos de operacion en acciones. Por ejemplo, la instruccion ADD R0, R1 debe escribirse como cadena binaria para que los circuitos de la Unidad aritmetico logica produzcan el resultado de una suma que sera almacenada en R0.

![[Pasted image 20230912163444.png]]