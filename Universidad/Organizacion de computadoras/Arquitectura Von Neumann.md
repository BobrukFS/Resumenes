# Arquitectura Von Neumann

Los **sistemas de computo** tienen como objetivo la resolucion de problemas computables. Un **sistema de computo** consta de un procesador, memoria, entrada/salida y las interconexiones entre estos componentes principales.

Los **problemas computables** son aquellos para las cuales se puede diseñar un algoritmo que lo resuelve. Un **algoritmo** es exactamente una secuencia de instrucciones que pertenecen a un conjunto de posibles instrucciones que conforman un lenguaje. Si ese lenguaje esta pensado para un sistema de computo que lo comprende, entonces los algoritmos son ejecutables automaticamente, es decir que se los define como **programas**. Entonces, el sistema de computos (o computadora) resuelve los problemas a traves de la ejecucion de programas.

La computadora es una máquina que **cambia información de una forma a otra**: **recibe información (entrada), la transforma y proporciona información (salida).** Esta información puede presentarse de muchas formas, lo que convierte a la computadora es una maquina sumamente versátil. Esta versatilidad está dada en que la maquina sea controlada por un programa, que establece las instrucciones que le indican a las partes físicas que deben hacer para transformar los datos de entrada en la salida requerida.

Von Neumann propuso una computadora de **proposito general**. Una **computadora** es una **maquina digital** y **sincrónica**, con capacidad de cálculo numérico y lógico, **controlada por un programa almacenado** y con posibilidad de **comunicación con el mundo exterior.**

*  Es **digital** porque dentro de la computadora las señales eléctricas que se manejan y **la información** que se procesa **se representa** en forma discreta, por medio de dos valores (0 y 1).

*  Es **sincrónica** ya que realiza las operaciones coordinadas por un reloj central que envía señales de sincronismo a todos los elementos que componen la computadora.

*  Internamente posee una **capacidad de cálculo numérico y lógico**, en un subsistema denominado **Unidad aritmético-logica (UAL).**

* Al ser controlada por un programa significa que internamente se tiene ordenes o instrucciones almacenadas que la computadora podrá obtener, interpretar y ejecutar.

* Esta **comunicada con el mundo exterior.** Esto significa que podrá realizar operaciones de ingreso o egreso de valores desde y hacia el mundo real, utilizando **dispositivos periféricos**.

La mayoría de las computadoras actuales presentan una estructura interna basada en la arquitectura definida por John Von Neumann:

![[Pasted image 20230911154155.png]]

Las computadoras solo realizan cuatro cosas:

· **Recibir entradas** (aceptan información desde el mundo exterior) mediante dispositivos de entrada como el teclado y el mouse.

· **Producir salidas** (dan información al mundo exterior) mediante dispositivos de salida como el monitor o la impresora.

· **Procesar información** (llevan a cabo operaciones aritméticas o lógicas con la información).

· **Almacenar información** (mueven y almacenan información en la memoria). Los dispositivos de almacenamiento y la memoria sirven para almacenar información. Los medios de almacenamiento más conocidos son las unidades de disco, diskettes y cintas.

El núcleo de una computadora digital es una colección de conmutadores de encendido-apagado diseñada para convertir información de una forma a otra mediante circuitos logicos. El usuario proporciona a la computadora patrones de bits (entrada) y esta sigue las instrucciones para transformar esa entrada en otro patrón de bits(salida) y devolverlo al usuario.

La arquitectura von Neumann, y se basa en tres conceptos claves:

* Los datos e instrucciones están almacenados en una única memoria de lectura-escritura constituida por celdas de igual tamaño.

* Los contenidos de las celdas de la memoria son identificables por posición, sin importar el tipo de los datos guardados en ese lugar.

* La ejecución ocurre de manera secuencial (a menos que se modifique explícitamente) de una instrucción a la siguiente.

[[Unidad central de procesamiento CPU]]
[[Ejecucion de un programa]]
[[Arquitectura Q]]
[[Memoria principal]]



