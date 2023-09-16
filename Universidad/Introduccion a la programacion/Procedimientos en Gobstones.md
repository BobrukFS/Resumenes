# Procedimientos en Gobstones

Un **procedimiento** permite definir un comando nuevo. Para definir un procedimiento se utiliza la palabra clave **procedure** seguida del nombre parentesis y llaves donde dentro de estas se pondra el codigo. Un procedimiento, al igual que un programa, tiene un cuerpo conformado por comandos entre llaves. Un procedimiento tiene un nombre que es el que se usara al llamarse, este nombre empieza con mayuscular y siempre la primera palabra es un verbo, por ejemplo DibujarCuadradoRojo, es decir, se utiliza CamelCase. El nombre del procedimiento debe describir el proposito de forma rapida.

Gobstone ya trae definido procedimientos, estos procedimientos se denominan **procedimientos primitivos**.

Un procedimiento puede tener otros procedimientos.

Al presentar nuevos procedimientos, se establecera si los mismos describen operaciones totales o parciales, y en caso de que sean parciales, cuales son sus precondiciones. En el caso de las operaciones parciales, normalmente se indicara solamente la accion descrita por el comando en el caso en que la precondicion sea verdadera.

El proposito en un procedimiento debe decir que esta haciendo este procedimiento sin importar el contexto en el que se usa el mismo. El procedimiento puede no tener una precondicion. La precondicion debe expresar que requerimientos deben suceder en el tablero en el estado actual para poder invocar a dicho procedimiento, si el procedimiento no necesita precondicion hay que aclarar que "No tiene precondicion".

![[Pasted image 20230820114038.png]]
![[Pasted image 20230820114113.png]]

Al crear un programa nosotros tenemos niveles, el programa es el nivel mas alto, en este punto debemos hablar solo en terminos del problema, para ello necesitamos procedimientos que hablen en termino del problema. 

Los procedimientos se pueden considerar como cufriendo diferentes niveles:

a. Nivel de resolucion del problema
b. Nivel de representacion de funcionamiento
c. Nivel de representacion basica

![[Pasted image 20230820163720.png]]

Mezclar niveles no significa mezclar procedimientos con comandos primitivos sino mezclar comandos que hables de niveles de abstraccion distintos

![[Pasted image 20230820163838.png]]


![[Pasted image 20230820115323.png]]

Los procedimientos aportan claridad, facilitan la reutilizacion y la modificacion y permiten expresar la solucion en terminos del problema y no de bolitas.

[[Parametros en gobstones]]