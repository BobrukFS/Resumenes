# Sistema binario

El **Sistema binario** es de base 2, utiliza solo dos simbolos (0, 1) para representar un numero.  Cada digito binario se conoce como **bit** y la secuencia de bits se denominan cadenas binarias.. Es un sistema posicional.

Este sistema es sumamente importante ya que las placas y los circuitos electronicos de nuestros telefonos y computadoras funcionan con dos tensiones (voltajes) diferentes, atribuyendo el 0 (cero) a "apagado" y el 1 (uno) al "encendido".

En principio, se utilizaran numeros enteros no negativos, con lo cual nuestro sistema lo conoceremos como **Binario Sin Signo (BSS)**.

![[Pasted image 20230818133711.png]]
![[Pasted image 20230818133700.png]]
![[Pasted image 20230501155008.png]]
## Rango

Un sistema numerico permite construir un conjunto infinito de cadenas, esto no se cumple en el contexto de un sistema de computos ya que se tiene una cantidad limitada de bits, por lo que el conjunto de numeros representables tambien sera limitado. Por este motivo se dice que el sistema es un **sistema restringido**.

En un sistema BSS(n) se pueden representar 2^n valores y el rango es `[0, (2^n) - 1]

Ejemplo en un BSS(3):

![[Pasted image 20230818141457.png]]

## Operaciones aritmeticas

### Suma binaria

Para el sistema binario conviene pensar la suma como un algoritmo por columnas. Es decir, que se suman las columnas empezando por la de menor peso (extremo de la derecha) y acarreando a la siguiente columna, si se alcanza o supera la base.

![[Pasted image 20230818141850.png]]
![[Pasted image 20230818142150.png]]
Para comprobar la correctitud del procedimiento, se deben interpretar las cadenas iniciales, calcular el resultado esperado y compararlo con la interpretacion de la cadena resultado.

### Resta binaria

Al igual que en la suma, al momento de restar, se realizara un algoritmo que procesa columnas de derecha a izquierda, pidiendo a la siguienta columna en caso de ser necesario, es decir cuando el resultado de la columna podria ser menor a cero. Esto se da en dos situaciones: cuando el minuendo es menor al sustraendo, o cuando en la columna inmediata anterior se pidio a la columna actual.

![[Pasted image 20230818142529.png]]
![[Pasted image 20230818143302.png]]
## Desplazamiento de cadenas

![[Pasted image 20230818143515.png]]
