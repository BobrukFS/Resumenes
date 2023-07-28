# Hash table / map / dictionary / array asociativo

Es una estructura de datos que permite almacenar llaves (keys) y valores (values). El proposito de una Hash Table es mantener la capacidad de acceder facilmente a cualquier valor a  partir de su clave, pero al mismo tiempo utilizar una cantidad razonable de memoria.

Por ejemplo si nosotros usamos un array para buscar el precio en una lista de precios, la complejidad sera linear, es decir O(n) ya que debemos recorrer todo el array para encontrar el valor que coincida con la key. En cambio, si usamos una hash table la complejidad sera constante, es decir O(1) o en el peor de los casos O(N) ya que la key nos proporciona la ubicacion del bucket que contiene su valor.

Estas estructuras no son ideales para conjuntos de datos pequeños, ya que hay una gran cantidad de sobrecarga. Son eficientes en un conjunto de datos grande.

![[Pasted image 20230508185723.png]]

Una Hash Table se compone de: 

* **Funcion Hash**: Es una funcion que toma una key y clacula un numero entero (La formula es personalizable y sera basada en la key y su tipo de dato). Esto da como resultado un codigo hash.

* **Buckets**: Es una ubicacion de almacenamiento de valores indexada, que permite una o mas entradas. Se puede guardar multiples entradas en caso de una colision, tratando cada bucket como una linkedlist.

## ¿Como funciona?

La funcion hashing va a tomar la key y calcular un numero entero que llamamos codigo hash. Este codigo hash lo operamos con un modulo de la capacidad de nuestra tabla (nro de buckets), lo que va a dar como resultado la ubicacion donde se va almacenar el valor de la key.

Hashing toma una key y calcula un numero entero /formula basado sera basada en la key y su tipo de dato). En una tabla hash, nosotros usamos HASH % capacidad de nuestra tabla para calcular el numero indice.

Nosotros en una hash table podemos insertar (**set**) , eliminar (**delete**) y buscar(**get**). Ademas podemos limpiar la hash table (**clear**) y mostrar el tamaño de la hash table (**size**). Todas estas operaciones son constantes.

## Colision

Las **colisiones** se producen cuando la funcion hash genera el mismo index para mas de una key. Es decir hay diferentes keys que tienen el mismo **codigo hash**. Cuanta menos colisiones tengamos mas eficiencia tendremos.

![[Pasted image 20230509130117.png]]

### Manejar las colisiones

#### Open addresing o Rehashing

Cuando se detecta la colision, lo que hay que hacer es buscar la siguiente casilla disponible para asignar al valor. Sin embargo esto no es optimo porque debemos recorrer hasta encontrar un espacio disponible por lo que la complejidad es linear.

Hay diferentes formas de implementar Open Addresing. Una de las mas comunes es la busqueda lineal "Linear Probing" aunque hay otras tecnicas como Quadratic Probing y Double Hashing.


#### Separate chaining

Cuando se detecta la colision en determinado bucket, hay que transformarlo en una lista enlazada. Esta listas enlazadas almacenara elementos que comparten el mismo indice en la tabla hash. Por lo que cada vez que se cree una colision se creara una lista enlazada. Sin embargo esto hace que la complejidad sea O(N).

![[Pasted image 20230509151022.png]]

#### Modificar la funcion hash

Una buena funcion hash es la que tiene la menor cantidad de colisiones por lo que debemos buscar el mejor algoritmo para que nunca se repita un codigo hash.


Ejemplo:

![[Pasted image 20230508185508.png]]









