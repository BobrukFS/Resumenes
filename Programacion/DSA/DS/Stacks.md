# Stacks

Una **pila** (stack en inglés) es una estructura de datos lineal que permite almacenar y recuperar datos, siendo el modo de acceso a sus elementos de tipo **LIFO** (del inglés Last In, First Out, «último en entrar, primero en salir»). Su operacion de insercion y extraccion se realiza por el mismo extremo.

![[Pasted image 20230506203248.png]]

## Operaciones en un stack

### Insertar un elemento / Push

Es una operacion que inserta un elemento en lo superior de nuestra pila y  nos devuelve la extension del stack.

**Complejidad de tiempo**: O(1)

### Eliminar un elemento / Pop

Es una operacion que elimina el ultimo elemento agregado a la pila y retorna su valor.

**Complejidad de tiempo**: O(1)

### Mostrar / Peek

Es una operacion que devuelve el valor del ultimo elemento agregado a la pila.

**Complejidad de tiempo**: O(1)

### Comprobar si esta vacio

Es una operacion que devuelve true si la pila esta vacia y false si no lo esta.
 
**Complejidad de tiempo**: O(1)

## Aplicaciones

* Si nosotros deshacemos o reponemos algo como por ejemplo en word estamos utilizando las pilas. Hay que realizar un seguimiento de las operaciones de los usuarios en algun tipo de pila y cuando se ejecuta el comando deshacer o rehacer la aplicacion mira la pila para identificar la operacion que tiene que deshacer o rehacer.

* Otro caso de uso seria cualquier algoritmo en el que es posible que deba realizar un seguimiento de los pasos que realiza. Es decir para aplicar Backtracking.
