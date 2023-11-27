# Compuertas logicas

Las compuertas logicas son dispositivos electronicos que componen un circuito que desarrollan las funciones logicas elementales de conjuncion, disyuncion y negacion.
El ultimo paso del metodo del diseño de circuitos consiste en conectar adecuadamente las compuertas logicas que sean necesarias, respetando la formula de verdad correspondiente.
## Tipos de compuertas
### Compuerta OR

Es aquella que implementa una disyuncion, posee dos entradas. La salida de esta compuerta representa la operacion logica de una suma entre ambas entradas, es decir, basta que una de ellas sea 1 para que su salida sea tambien 1.

![[Pasted image 20230826174114.png]]
![[Pasted image 20230826222508.png]]
### Compuerta AND

Es aquella que implementa la funcion logica de la conjuncion. Tiene dos entradas y el resultado es un 1 solo si ambas entradas son 1.

![[Pasted image 20230826174219.png]]

### Compuerta NOT
Es aquella que implementa un inversor, es decir, invierte el dato de entrada. Esta compuerta dispone de una sola entrada.

![[Pasted image 20230826174235.png]]
![[Pasted image 20230826222627.png]]
### Compuerta XOR
Es aquella que implementa una disyuncion exclusiva, es decir que su salida sera 1 si una y solo una de sus entradas es 1.

![[Pasted image 20230826222728.png]]
![[Pasted image 20230826174302.png]]
### Otras compuertas

#### Compuerta NAND

Es aquella que implementa la siguiente expresion logica:

![[Pasted image 20230826222854.png]]

#### Compuerta NOR

Es aquella que implementa la siguiente expresion logica:

![[Pasted image 20230826222944.png]]

![[Pasted image 20230826174357.png]]
## Conexion de compuertas

La **conexion de las compuertas dan lugar a un circuito**. Para que el circuito sea legible, hay una tecnica para ir conectando las compuertas siguiendo un orden espacial dentro del circuito de manera que quede organizado visualmente.

Como primer paso se debe replicar cada entrada del circuito de manera de disponer un cable de conexion para cada entrada y su negacion, como puede observarse en la figura 5.11 (A). Cada uno de esos cables representan los **literales de las formulas de verdad** y estan disponibles para conectarse una o mas veces a las compuertas de cada termino.

El segundo paso es ir conectando a cada compuerta siguiendo el orden de los terminos de la formula de verdad, en direccion a la salida del circuito, como se observa en B. Como ejemplo, en C se puede ver como conectar la linea e1 y la linea ~e2 a una compuerta AND, siguiendo un termino (e1 . ~e2). A continuacion se conecta otra compuerta AND segun un posible segundo termino (e1 . e2) como en D. Finalmente, las salidas de cada compuerta AND se conectan entre si mediante compuertas OR

![[Pasted image 20230826223202.png]]
![[Pasted image 20230826223637.png]]

Ejemplo:

![[Pasted image 20230826223745.png]]