# Circuitos aritmeticos

Los **circuitos aritmeticos** resuelven tareas especificas relacionadas a las operaciones aritmeticas entre cadenas binarias. Esas cadenas representan en forma binaria dentro del sistema de computos los valores numericos a operar, y por lo tanto estos circuitos operan sobre dos cadenas binarias. 
## Semisumador - Half Adder

El objetivo de este circuito es el de sumar dos cadenas de un bit (BSS(1)), calculando el resultado (en BSS(1)) e indicando ademas en otra salida, si hubo o no acarreo(carry). Por lo tanto recibe 2 entradas (los operandos a sumar) y obtiene 2 salidas (2 bits) que representan 1 bit que indica el resultado de la suma y 1 bit que indica si hubo acarreo.

![[Pasted image 20230826183528.png]]
![[Pasted image 20230827170843.png]]
![[Pasted image 20230827171333.png]]
## Sumador - Full Adder

El objetivo de un sumador es, sumar 2 cadenas en BSS(n). Para hacerlo se separa el problema en varios problemas mas simples: sumar cada columna de la cadena de n bits, dado que en cada columna se hace lo mismo. El hecho de sumar una columna es equivalente al semisumador, pero teniendo en cuenta tambien se necesita como entrada, informacion sobre el carry de la columna anterior (la que esta a la derecha).

Por lo tanto, el sumador recibe 3 entradas, 2 de ellas corresponden a los operandos BSS(1), y la tercera indica si hay acarreo pendiente. Al igual que el semisumador obtiene una salida para el resultado y otra para el acarreo resultante.


![[Pasted image 20230826183544.png]]
![[Pasted image 20230827171318.png]]
![[Pasted image 20230827171904.png]]
![[Pasted image 20230827171346.png]]

### Sumar mas de dos bits

Al contar con el semisumador y el sumador para BSS(1), es posible ahora construir un sumador para cadenas BSS(2), que debe tener la interfaz(conjunto de entradas y salidas) descripta por la figura 23. Esta idea puede extenderse para construir sumados para una mayor cantidad de bits, replicando la idea de conectar en cascada los sumadores y usando un semisumador para la primer columna

![[Pasted image 20230827172004.png]]
![[Pasted image 20230827172011.png]]

Si queremos hacer una suma mas de dos bits lo que podemos hacer es ir concatenando diferentes circuitos de suma para poder permitir esta operacion.

![[Pasted image 20230826183826.png]]
## Semirestador y restador

El restador es como full adder pero en vez de sumar, resta

![[Pasted image 20230826183908.png]]
![[Pasted image 20230827172420.png]]
![[Pasted image 20230827172300.png]]
![[Pasted image 20230827172409.png]]