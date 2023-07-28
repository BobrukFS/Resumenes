# Linked lists

Las linked lists generalmente no se almacenan en ubicaciones contiguas, por lo que deben almacenarse con etiquetas adicionales (**punteros**) que proporcionen una referencia al siguiente elemento.

Las listas enlazadas permite almacenar un conjunto de elementos(tambien pueden ser llamados objetos o nodos) presentados como una secuencia (en forma lineal) sin necesidad de estar en ubicaciones contiguas. 

![[Pasted image 20230503221922.png]]

Una lista enlazada consta de un numero de **nodos(elementos)** con dos componentes(campos), un punto que referencia al siguiente nodo de la lista y un valor, que puede ser **cualquier tipo**. El ultimo nodo va a referenciar a una lista vacia, a null.

![[Pasted image 20230503222043.png]]
![[Pasted image 20230503222154.png]]

Las listas enlazadas son **estructuras de datos dinamicas**, es decir, porque exactamente el numero de nodos que va a tener se va a definir durante el tiempo de ejecucion.

## Operaciones en listas enlazadas

### Insertar elementos en una lista enlazada. 

#### Start

Para insertar un elemento al principio de mi lista enlazada lo que debo hacer es instanciar un nuevo nodo con su valor y su puntero que apunta al siguiente elemento (aquel que antes era el primero) y hacer que el puntero head apunte hacia el nuevo nodo. 

![[Pasted image 20230503222242.png]]
![[Pasted image 20230503222317.png]]

**Complejidad de tiempo**: O(1)

#### End

Para insertar un elemento al final primero debemos saber si tenemos un puntero cola o no. En caso de que tengamos tail, lo que debemos hacer es simplemete instanciar el nodo, actualizar el puntero de tail para que referencie al nuevo nodo, y actualizar el puntero del nodo anterior para que apunte a este ultimo que fue agregado. Ademas el nuevo nodo agregado tiene que tener un puntero que referencie a null.

**Complejidad de tiempo**: O(1)

Por otro lado, si no tenemos tail, debemos recorrer cada elemento de la lista hasta llegar al nodo que su puntero referencie a null. Luego realizamos los mismos pasos.

**Complejidad de tiempo**: O(N)

![[Pasted image 20230503222327.png]]
![[Pasted image 20230503222348.png]]

#### Middle

Para insertar un nodo despues de otro nodo lo que debemos hacer es primero instanciar el nodo, luego recorremos la lista hasta llegar al nodo donde vamos a insertar despues de el nuestro nuevo nodo. Actualizamos el puntero del nodo actual para que apunte al nodo que agregamos, y actualizamos el puntero del nodo que agregamos para referenciar al nodo siguiente.

**Complejidad de tiempo**: O(N)

En cambio para insertar un nodo antes de otro nodo la complejidad es :

**Complejidad de tiempo:** O(N)

![[Pasted image 20230503222511.png]]
![[Pasted image 20230503222524.png]]

### Mostrar los elementos de una lista enlazada

### Eliminar un elemento en una lista enlazada. 

Cuando vayamos a eliminar un elemento de una lista, primero tenemos que acordarnos de liberar la memoria ocupada por dicho nodo (en algunos lenguajes de programacion). Para ello debemos declarar una variable temporal que almacene el valor de dicho nodo, para luego poder eliminarlo.

#### Start

Para eliminar el primer elemento de una lista enlazada lo que debemos hacer es actualizar el puntero head para que apunte al siguiente nodo de la lista. A continuacion, eliminamos el nodo.

![[Pasted image 20230503222716.png]]
![[Pasted image 20230503222729.png]]

**Complejidad de tiempo:  O(1)**

#### End

Si queremos eliminar el ultimo elemento de una lista enlazada debemos recorrer toda nuestra lista hasta llegar al final. Luego debemos actualizar el puntero de la cola actual para apuntar a la nueva cola que seria el nodo anterior al eliminado y actualizar su puntero a null. Posteriormente eliminamos el nodo.

![[Pasted image 20230503222752.png]]

**Complejidad de tiempo O(n)**

#### Middle

![[Pasted image 20230503222802.png]]
![[Pasted image 20230503222811.png]]
**Complejidad algoritmica**:  O(N).

### Traversing elements

Acceder a cada uno de los elementos de una lista, comenzamos por el primero y terminamos por el ultimo. Para ello podemos recorrer los elementos en un bucle del primero al ultimo, es decir hasta que el puntero de un nodo apunte a NULL.

**Complejidad de tiempo**:  O(N)

### Accesing an element

A diferencia de los arrays en las listas enlazadas no tenemos indices para acceder, por lo que debemos recorrer los elementos hasta llegar al nodo al que queremos acceder. 

**Complejidad de tiempo para el nodo head y tail** : O(1)
**Complejidad de tiempo para cualquier otro nodo**:  O(N)

## Clasificacion de listas enlazadas

### Listas simplemente Enlazadas

Cada nodo(elemento) contiene un unico enlace que conecta ese nodo al nodo siguiente y asi consecutivamente. La lista es eficiente en recorridos directos (hacia adelante).

![[Pasted image 20230503223148.png]]


### Listas doblemente enlazadas

Cada nodo contiene dos punteros, uno a su nodo predecesor(anterior) y el otro a su nodo sucesor(siguiente). La lista es eficiente tanto en recorrido directo como en recorrido inverso.

![[Pasted image 20230503223254.png]]

Este tipo de lista nos permite recorrerla tanto hacia delante como hacia atras.

### Lista circular simplemente enlazada

Es una lista enlazada simplemente en la que el ultimo elemento (tail) se enlaza al primer elemento (head) de tal modo que la lista puede ser recorrida de modo circular.

![[Pasted image 20230503223314.png]]


### Lista circular doblemente enlazada

Una lista enlazada doblemente enlazada en la que el ultimo elemento se enlaza al primer elemento y viceversa. Esta lista se puede recorrer de modo circular tanto en direccion directa como inversa.

![[Pasted image 20230503223341.png]]

## Ventajas y desventajas de una lista enlazada frente a un array

### Ventajas

* Los nodos no tienen porque guardarse todos juntos en memoria, como ocurre con los arrays.

* Pueden tener longitud variable, es decir, son estructura de datos dinamicas a diferencia de los arrays que tienen tamaño fijo.

* Podemos agregar y quitar elementos en tiempo de ejecucion.

* Permite insertar o eliminar del inicio en tiempo constante (O(1)).

### Desventajas

* Las listas no tienen indice, por lo que no podemos hacer accesos aleatorios. Por lo que dicha operacion sera mas costosa.

* Necesita mas espacio en memoria ya que ademas de los datos hay que almacenar los punteros.

* Los arrays tienen una mejor localidad de caché en comparación con las listas vinculadas.

## Aplicacion

* Las linked list se pueden utilizar para implementar en otras estructuras de datos como puede ser stacks, queues, hash tables.