# Memoria principal RAM

La **memoria principal M (Memoria ram, Random Access Memory)** se divide conceptualmente en dos partes: **memoria de instrucciones Mi** dónde **residen las instrucciones que la computadora debe interpretar y ejecutar (el programa almacenado)**, y la **memoria de datos Md** donde se **almacena la información(datos) con la cual la computadora realizara los procesos** (cálculos, decisiones, actualizaciones) que sean necesarios para la resolución del problema. La memoria ram guarda las instrucciones y datos de forma temporal.

La memoria principal es un conjunto de celdas, donde cada celda es un dispositivo que almacena una cadena de bits. El conjunto de celdas es homogeneo, es decir que todas las celdas tienen la misma capacidad, expresada en cantidad de bits. Ademas, cada celda tiene una direccion que la identifica para permitir su lectura o escritura, por eso se dice que es la unidad direccionable mas pequeña. La memoria permite leer o escribir celdas. Es volatil: pierde su contenido al desconectar la energia electrica.

Se denomina de acceso aleatorio porque el acceso a una celda tiene un costo en tiempo igual a cualquier otra.

![[Pasted image 20230917191357.png]]

Por ejemplo si la memoria recibe una orden de lectura sobre la celda 0004 devuelve una cadena binaria de 8 bits 01101110.

La celdas se agrupan en palabras. La palabra es la unidad natural de organizacion de la memoria. El tamaño de la palabra suele coindicir con lo necesario para representar numeros, y puede ser de 1 celda.

**Espacio direccionable:** Conjunto de todas las direcciones de todas las celdas.

Si la memoria tiene 2^m celdas, se necesitan m bits para expresar las direcciones `[0:2^m -1]`

**Unidad de transferencia:** cantidad de bits que se trasmiten al mismo tiempo
## Operaciones sobre la memoria

La memoria admite dos operaciones: **lectura** y **escritura** de celdas. 

### ¿Como funciona la lectura?

La operacion de lectura ocurre cuando la UC pide un dato almacenado en una determinada celda de la memoria principal. Para esto, la UC pone la direccion en el registro MAR y luego activa una señal de lectura en el bus de control. Luego, la Memoria Principal activa un circuito decodificador que permite elegir la celda especifica y copiar su contenido en el bus de datos. Finalmente, el dato se encontrara disponible en el registro MBR de la CPU y mediante el bus de control activara una señal que indica que el dato esta disponible.

![[Pasted image 20230917192057.png]]
### ¿Como funciona la escritura?

La operacion de escritura ocurre cuando la UC necesita almacenar un dato en una determinada celda de memoria. Para hacerlo, la UC pone el dato en el registro MBR y una direccion en el registro MAR. Luego activa una señal de escritura en el bus de control para indicar la operacion de escritura. Tambien en este caso, la memoria activa un circuito decodificador uqe permite elegir la celda especifica, pero ademas toma el dato del bus de datos y lo copia en dicha celda. Finalmente, mediante el bus de control se indica a la UC que la operacion ha finalizado.

![[Pasted image 20230917192144.png]]

Ejemplo de una memoria de 4 celdas

![[Pasted image 20230918163306.png]]