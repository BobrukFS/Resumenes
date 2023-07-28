# Heap

**Heap** es una estructura de datos basada en árboles que sigue las propiedades de un árbol binario completo y es Min Heap o Max Heap.

## Min heap

El valor de cada uno de los nodos principales del arbol es menor o igual que el valor de sus hijos.

![[Pasted image 20230516224406.png]]

## Max heap

El valor de cada nodo principal es mayor o igual que el valor de los nodos hijos.

![[Pasted image 20230516224509.png]]

## Operaciones

### Insert

Se realiza de arriba a abajo y de izquierda a derecha. Pero para respetar las propiedades de que debe ser un min heap o max heap, debemos comparar el valor de los nodos recien insertados con el nodo principal y hacemos intercambio o bubble.

La complejidad de la insercion en un heap es logaritmica, O(log n).

#### Min heap

Insertamos el nodo y seguimos burbujeando si el valor del nodo es mas pequeño que el nodo principal.

#### Max heap

Insertamos un nodo y seguimos comparando y burbujeando si el valor del nodo recien insertado es mayor que el nodo principal.

### Delete

#### Min heap

Primero eliminamos el valor mas pequeño, luego eliminamos el segundo valor mas pequeño, luego el tercer mas pequeño y asi sucesivamente.

Al eliminar el primer valor mas pequeño, lo que hacemos es tomar el ultimo nodo de min heap y ponerlo como nodo raiz. Luego empezamos a comparar el nodo raiz con el nodo hijo y burbujeamos si el nodo raiz o principal es mayor que sus nodos hijos hasta que llegue al lugar donde debe estar.

#### Max heap

Primero eliminamos el valor mas grande, luego eliminamos el segundo valor mas grande y luego el tercer valor mas grande y asi sucesivamente.