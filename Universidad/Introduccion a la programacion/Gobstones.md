# Gobstones

En gobstone nosotros manipulamos **bolitas** sobre un **tablero** mediante el **cabezal**, que seria la **celda** actual. Este cabezal realiza acciones al recibir instrucciones y brinda informacion al responder preguntas. Solo se puede acceder a una celda por vez.

![[Pasted image 20230819152604.png]]
Para manejar el cabezal se utilizan  los comandos que son descripciones de acciones (Poner, Mover) y las expresiones que son descripciones de informacion (Rojo, Este).

En Gobstones, **se transforma un tablero inicial en un tablero final**. Para informar el estado inicial del tablero debemos indicar el tamaño del tablero, cantidad y posicion de las bolitas y la posicion del cabezal.

El programa comienza con la palabra clave **program** y sus comandos van entre llaves `{...}` que determina el bloque de codigo. Los comandos comienzan con mayuscula, por ejemplo, Poner, Mover, etc. Los comandos primitivos llevan un **argumento** que serian las expresiones que describen informacion. Ejemplo: Poner(Rojo) donde los valores literales tambien empiezan con mayuscula Verde, Este, etc. Si no se respetan las reglas, se produce un error.

La secuenciacion de comandos se obtiene colocando los mismos uno a continuacion del otro, normalmente en lineas separadas, y opcionalmente terminados con el caracter de punto y como (;)

Los **programas equivalentes** son aquellos que pueden resolver el mismo problema.

Una **operacion total** es la descripcion de una accion que, al no tener requisitos para que el cabezal pueda llevarla a cabo, siempre puede ser realizada.

Una **operacion parcial** es la descripcion de una accion que precisa que en ciertos requisitos se cumplan para que el cabezal pueda llevarla a cabo, y en que en caso de que los mismos no se cumplan, provoca la autodestruccion del cabezal y todos los elementos. La precondicion de una operacion parcial expresa los requisitos que deben cumplirse para que la ejecucion de la accion indicada por la operacion pueda ser llevada a cabo sin provocar la autodestruccion del cabezal.

**Dato**: Hay que **indentar** siempre para que se sea legible al leer el codigo.

**Dato**: Los comandos pueden contener, como parte de su nombre, letras, números y el guión bajo.

**Dato**: Hay diferente tipos de tableros iniciales y si se pide, debe funcionar en todos ellos.

![[Pasted image 20230824205142.png]]

Un valor es una entidad o dato con sus caracteristicas propias.

Una expresion es un simbolo o cadena de simbolos que se utiliza para describir, denotar o nombrar un valor especifico.

Mientras las expresiones referencias cosas, los comandos referencian acciones. Pero tanto expresiones como comandos estan formados por cadenas de simbolos.
## Vestimentas

Las **vestimentas** permiten asociar estados de una celda con imagenes especificas, asi podemos visualizar las ideas representadas.
## Comentarios en el codigo

Los programas pueden contener texto que sea ignorado por la computadora. Los comentarios sirven para documentar, dejar comentarios y anular un comando. Hay dos tipos de comentarios: En linea y en parrafo. Para poner comentarios en gobstone utilizamos // en linea y `/**/` en parrafo.

[[Procedimientos en Gobstones]]




