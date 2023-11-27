# Circuitos

Los **circuitos digitales** son dispositivos fisicos que implementan una funcion logica. Es decir que para un conjunto de valores logicos de entrada, computa una unica salida logica.

Un circuito es una composicion de compuertas interconectadas entre si que traduce un conjunto de entrada en una salida de acuerdo a una funcion logica. Esta salida se actualiza inmediatamente luego de proveerse las entradas. A este tipo de circuitos digitales se los denomina **Circuito Combinacionales o combinatorios** debido a que recibe varias entradas y su salida esta determinada de forma unica por las entradas vigentes. 

## Circuitos utiles 

### Multiplexor

Un circuito multiplexor tiene por objetivo proyectar una de las entradas en la salida a partir de una linea de control. Es una idea muy utilizada en cuando se tiene un recurso compartido (en este caso, el canal de salida) y se debe asignar a una demanda particular (una de las entradas). El multiplexor recibe 2^N entradas de datos, una salida y N lineas de control que permiten seleccionar solo una de todas las entradas.

* **2^N entradas**
* **1 salida**
* **N lineas de control**

![[Pasted image 20230827013601.png]]
![[Pasted image 20230827013610.png]]
La entrada seleccionada pasa por compuertas hacia la salida. Cada combinacion de las entradas de control corresponde a una entrada de datos, y la salida final del multiplexor correspondera la valor de dicha entrada seleccionada. En B se muestra como la linea de control cuando vale 0 activa el paso de la entrada E1 (con el simbolo !) y cuando vale 1 activa el paso de la entrada E2 (con el simbolo "?").

Para elaborar la tabla de verdad se debe considerar que son 3 entradas.

Formula de verdad:

![[Pasted image 20230827020647.png]]

Para ensamblar el circuito se puede tomar uno de los siguientes criterios. Por un lado, es posible conectar las entradas como indica la formula de verdad anterior, y por otro es posible conseguir otra formula equivalente que simplifique el circuito final, en terminos de cantidad de compuertas asi como de trabajo de diseño. Para ello se aplica una de las leyes de equivalencia de la logica proposicional, y asi se puede construir un circuito mas simple como se muestra en la figura 17

![[Pasted image 20230827020849.png]]

### Decodificador

El objetivo de un decodificador es el traducir un codigo de N bits de entrada en uno de 2^N valores.

Para esto tiene N entradas que representan una cadena de N bits, y selecciona una y solo una de las 2^N lineas de salida. Esto quiere decir que cada linea de salida sera activada para una sola de las combinaciones posibles de entrada. Este circuito es util por ejemplo para direccionar espacios de memoria. Un decodificador de N entradas es capas de direccionar 2^N espacios de memoria.

Algo notable de este circuito es que tiene multiples salidas y por lo tanto cada salida se describe con una formula de verdad independiente, es decir que se debe aplicar por separado el metodo SoP o PoS segun el caso.

* **Posee N entradas**
* **Posee 2^N salidas**
* **No posee lineas de control**

Las salidas se prenden de a una.

![[Pasted image 20230827012829.png]]
 De esta manera, las formulas de verdad para cada una de las salidas son:
![[Pasted image 20230827013158.png]]
![[Pasted image 20230827012853.png]]
![[Pasted image 20230826185420.png]]
![[Pasted image 20230826185307.png]]

### Demultiplexor

Es un circuito complementario al multiplexor, en el cual se permite configurar por cual salida se proyecta la entrada. Esto quiere decir que recibe solo 1 linea de entrada, N lineas de control y 2^N lineas de salida. Este circuito encamina su unica linea de entrada a una de sus 2^N lineas de salida dependiendo de los valores de las lineas de control. Es decir, si el valor binario de las lineas de control es k, se selecciona la salida k.

* **1 entrada**
* **N lineas de control**
* **2^N lineas de salida**

![[Pasted image 20230826185859.png]]
![[Pasted image 20230826190129.png]]

#### Decodificador a demultiplexor

Son parecidos pero el valor de salida cambia. Para ello hacemos una tabla de verdad.

Lo unico que tenemos que combinar son las entradas con las salidas

![[Pasted image 20230826192437.png]]

E de entrada. Sn por salida 0 1 2 y 3. SF que seria la salida final del circuito para poder hacer un demultiplexor de nuestro decodificador.

Luego utilizo SoP o PoS 

![[Pasted image 20230827052920.png]]

![[Pasted image 20230827052952.png]]
Ahora lo que tenemos que hacer es combinar mi entrada con cada una de las salidas del decodificador utilizando esa formula para lograr un demultiplexor. Ponemos de prueba c1 1 y c0 0 y vemos que es igual al demultiplexor.

![[Pasted image 20230827045141.png]]


[[Circuitos aritmeticos]]