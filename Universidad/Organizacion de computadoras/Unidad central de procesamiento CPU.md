# Unidad central de procesamiento CPU

El **procesador o unidad central de procesamiento (UCP),** interpreta y lleva a cabo las instrucciones de los programas, efectúa manipulaciones aritméticas y lógicas con los datos y se comunica con las demás partes del sistema de cómputo.

Una CPU moderna es un conjunto extraordinariamente complejo de circuitos electrónicos. Cuando se incorporan todos estos circuitos en un chip de silicio, a ese chip se lo denomina **microprocesador**. La CPU se ubica en la motherboard (placa madre). Aunque hay variantes en cuanto al diseño de estos chips, existen dos factores relevantes para el usuario: la **compatibilidad y la velocidad**

·  No todo el software es compatible con todas las UCP.

· Hay una enorme diferencia en la rapidez con la cual los procesadores pueden manejar información. La **velocidad de una computadora esta determinada** en gran parte por **la velocidad de su reloj interno**, el dispositivo cronométrico que produce pulsos eléctricos para sincronizar las operaciones. Por lo general, las computadoras se describen en términos de su velocidad de reloj, medida en unidades **Hertz** (un herz representa un pulso por segundo).

El funcionamiento del procesador esta determinado por las instrucciones que ejecuta. Estas instrucciones se denominan **instrucciones maquina**. Al conjunto de instrucciones distintas que puede ejecutar el procesador se denomina **repertorio de instrucciones**.

Un punto de encuentro en que la persona que diseña el computador y la persona que lo programa pueden ver la misma maquina es el **repertorio de instrucciones**. Desde el punto de vista de las personas que diseña, el conjunto de instrucciones maquina constituye la especificacion o requisitos funcionales del procesador: implementar el procesador es una tarea que, en buena parte, implica construir circuitos que cumplan con esos requisitos. Desde el punto de vista de la persona que programa, las instrucciones de ese lenguaje ensamblador son las herramientas disponibles para expresar los programas.

Cada instruccion debe contener la informacion que necesita el procesador para su ejecucion:

* **codigo de operacion**: Especifica la operacion a realizar (suma, resta, etc). La operacion se indica mediante un codigo binario denominado **codigo de operacion** o **codop**.
* **Referencia a los operandos origen**: La operacion puede implicar uno o mas operandos origen, es decir operandos que son entradas para la operacion.
* **Referencia al resultado**: La operacion puede producir un resultado por lo que puede ser necesario indicar donde se almacenara.
* **Referencia a la siguiente instruccion**: Indica al procesador de donde captar la siguiente instruccion tras completarse la ejecucion de la instruccion actual. La siguiente instruccion a captar esta en memoria principal o, en el caso de un sistema de memoria virtual en memoria principal o en memoria secundaria (disco). En la mayoria de los casos, la siguiente instruccion a captar sigue inmediatamente a la instruccion en ejecucion y en tales casos no hay referencia explicita a la siguiente instruccion. Cuando sea necesaria la referencia explicita debe suministrarse la direccion de memoria principal o de memoria virtual.

Por otro lado, los operandos y el resultado pueden estar en algunas de las tres areas:

* **Memoria principal o virtual**
* **Registro del procesador**: Un CPU contiene uno o mas registros que pueden ser referenciados por instrucciones maquina. Si solo existe un registro, la referencia a el puede ser implicita. Si existe mas de uno, cada registro tendra asignado un numero unico y la instruccion debe contener el numero del registro deseado. Estos registros se denominan **registros de uso general** y normalmente son circuitos secuenciales con capacidad de almacenar una cadena de unos cuantos bits.
* **Dispositiva de entrada/salida**: La instruccion debe especificar el modulo y dispositivo de Entrada/Salida para la operacion. En el caso de E/S asignadas en memoria, se dara otras direccion de memoria principal o virtual.
## Componentes del CPU

![[Pasted image 20230911195045.png]]
### Unidad de control UC

La funcion de la **unidad de control** es buscar las instrucciones en la memoria principal, decodificarlas (interpretación) y controla la ejecucion, empleando para ello la unidad de proceso. Establece la comunicacion entre la ALU suministrandole los operandos e indicandole que operacion llevar a cabo, la memoria principal y el resto de los componentes. 
### Unidad aritmetica y logica ALU

La ALU es un circuito logico digital encargada de las operaciones aritmeticas (suma, resta, etc) y logicas (not, and, or, etc) sobre datos. Los datos con los que se trabaja siempre estan en registros. Los datos e instrucciones viajan desde la memoria principal hasta estas memorias internas llamadas registros.

**Todos los otros elementos del sistema de cómputo** (UC, registros, memoria, entrada/salida) están principalmente para **traer datos a la UAL** para que ésta los procese y luego tomar los resultados y comunicarlos. **Una UAL y todos los componentes en la computadora** están basados en el **uso de simples dispositivos electrónicos digitales que pueden almacenar dígitos binarios y realizar operaciones lógicas** simples (operaciones booleanas).

La UAL también actualiza unas señales denominadas **banderas o flags** como resultado de una operación. Estas banderas o flags, que no son más que bits individuales o pertenecientes a un registro especial, cambiarán acorde al resultado. 
### Otros elementos

* **Registros:** Son un espacio de almacenamiento interno que almacenan temporalmente los datos (bits) de E/S de los circuitos operacionales. (Por ejemplo, el **registro acumulador** que almacena temporalmente los resultados de las operaciones o el registro de estados que indica el estado de la última operación). Hay dos tipos de clasificaciones de registros:

* **Registro contador de programa (PC):** Contiene la dirección de memoria (seria como el índice) de la siguiente instrucción a ejecutar y se incrementa en uno cada vez que se hace una lectura de instrucciones.

* **Registro de instrucción (IR):** La instrucción leída desde la memoria principal, se almacena aquí para que la unidad de control decida qué hacer.

* **Registro de direccionamiento:** Se coloca el numero de dirección a la que ir a buscar un dato. Esta dirección es indicada por la propia instrucción o por algún otro modo de direccionamiento.

* **Registro de direccion de memoria(MAR)**: Es un registro que me guardara momentaneamente la direccion con la cual se esta operando en memoria.

* **Registro amortiguador de memoria(MBR)**: Es un registro que guarda el dato a escribir en una posicion de memoria o el dato contenido en una posicion de memoria leido mas recientemente.

* **Decodificador:** Son circuitos especiales encargados de determinar que se debe hacer.

Los registros de la UCP sirven para dos funciones:

*  **Registros visibles al usuario:** Permiten al programador en lenguaje de maquina minimizar las referencias a memoria principal optimizando el uso de los registros, que son de acceso más rápido que aquella.

* **Registros de control y estado:** Son utilizados por la UC para controlar la operación de la UCP, y por programas del sistema operativo para controlar la ejecución de los programas.

* **Bus interno de UCP**: Es necesario para transferir datos entre los distintos registros y la UAL, dado que la UAL de hecho opera solo sobre datos en la memoria interna de la UCP.

![[Pasted image 20230918162413.png]]