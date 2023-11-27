# Arquitectura Q


![[Pasted image 20230911162202.png]]

## Prueba de programas: Prueba de escritorio

La **prueba de escritorio** es un metodo para analizar si un programa cumple con loq ue se espera de el. Para realizar esta prueba se debe definir un escensario inicial concreto y un escenario final o esperado, para luego **simular la ejecucion del programa a alto nivel**, indicando los cambios en cada instruccion. Finalmente se debe comparar el resultado obtenido con el resultado que se esperaba, para concluir si la prueba fallo o fue exitosa.

Ejemplo: Se cuenta con un programa en Q1 que calcula el area de un trapecio

![[Pasted image 20230912162147.png]]

donde la base mayor B esta almacenada en R0, la base menor b en R1, y la altura h en R2. El programa que calcula el area, dejando el resultado en el registro R0, es como sigue:

![[Pasted image 20230912162235.png]]

Suponiendo que ocmo escensario inicial se tiene que el registro R0 contiene la cadena 0003, el registro R1 contiene la cadena 0002, y el registro R2 contiene la cadena 0002, entonces se espera que el resultado sea R0=0005.

![[Pasted image 20230912162335.png]]
![[Pasted image 20230912162352.png]]


[[Arquitectura Q1]]
[[Arquitectura Q2]]



