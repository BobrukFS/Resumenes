# Buses

Un **bus**, es un canal de comunicación que las computadoras usan para comunicar sus componentes entre sí para trasmitir datos, direcciones y señales de control. 

El **bus del sistema** esta formado por tres buses para cumplir los diferentes objetivos:

* **bus de direcciones**: Indica el destino o el origen del dato que esta en el bus de datos. En el bus de direcciones, el ancho de bus determina el espacio direccionable. Si tengo m bits, la cantidad maxima de combinaciones, y por lo tanto de celdas a direcciones es 2^m.
* **bus de datos**: Transporta los datos. En el bus de datos el ancho del bus determina cuantos bits pueden trasmitirse simultaneamente.
* **bus de control**: Indica si es lectura o escritura.

Cada bus tiene una determinada cantidad de lineas (**ancho de bus**) y cada linea trasmite un bit a la vez. Entonces el ancho del bus determina cuantos bits se pueden trasmitir en paralelo

![[Pasted image 20230917193721.png]]

Ejemplo:

![[Pasted image 20230917195000.png]]
