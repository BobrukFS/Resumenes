# Queue

Una **cola** es una coleccion lineal de elementos caracterizada por ser una secuencia de elementos en la que la operación de insercion se realiza por un extremo y la operación de extraccion por el otro. Tambien se le llama estructura **FIFO** debido a que el primer elemento en ser agregado sera el primero e ser eliminado.

![[Pasted image 20230507163300.png]]

## Operaciones en una cola

### Insertar elemento

Es una operacion que agrega un elemento al final de nuestra cola.

**Complejidad de tiempo:** O(1)

### Eliminar elemento

Es una operacion que elimina el primer elemento de la cola, es decir el agregado menos recientemente.

**Complejidad de tiempo:** O(n) o O(1) dependiendo si utilizamos una array u otra forma.

### isEmpty

Es una operacion que devuelve true si la cola esta vacia, en caso contrario devuelve false.

**Complejidad de tiempo:** O(1)

### Peek

Es una operacion que nos devuelve al primer elemento de la cola.

**Complejidad de tiempo:** O(1)

## Aplicaciones

* Cuando agregamos una cancion a la cola, estamos utilizando esta estructura de datos.
* Para servidores ya que tenemos un monton de operaciones entrando y debemos atender lo que ha estado esperando mas tiempo.