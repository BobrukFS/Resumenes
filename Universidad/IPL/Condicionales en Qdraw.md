# Condicionales en Qdraw

La **alternativa condicional** permite elegir en base a una condición si un bloque de código debe ejecutarse o no. Las condiciones pueden tomar valores o bien verdaderos, o bien falsos. Son los que nos van a permitir discernir entre dos alternativas En las condiciones podemos utilizar operadores lógicos como negación, conjunción y disyunción, etc.

En QDraw, la sintaxis de una alternativa condicional se escribe así:

![[Pasted image 20230426173602.png]]
![[Pasted image 20230426173606.png]]
![[Pasted image 20230426173614.png]]
Por lo tanto, cuando necesitemos accionar mediante sólo una alternativa, el bloque de código que no se utiliza, lo debemos eliminar por completo, simplificando así el código y su lectura.

En este caso, la alternativa eliminada es aquella cuya condición evalúa falso (bloque del "sino"). Quedando como resultado el siguiente código:

![[Pasted image 20230426173632.png]]
Ahora ¿qué pasa si la alternativa en desuso es aquella cuya condición evalúa verdadero (bloque del "si")? Lo que conviene hacer aquí, es cambiar la pregunta negando la condición original, invirtiendo así la situación.

![[Pasted image 20230426173647.png]]
![[Pasted image 20230426173652.png]]
