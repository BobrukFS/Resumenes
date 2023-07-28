# Graph

Los gráficos son estructuras de datos no lineales formadas por un número finito de nodos o vértices y los edges que los conectan. Los gráficos son estructuras de datos que se utilizan para abordar problemas del mundo real en los que representa el área del problema como una red, como redes telefónicas, redes de circuitos y redes sociales.

![[Pasted image 20230516212739.png]]

## Graph directed y Graph undirected

### Graph undirected

En el grafico no dirigido no tenemos una direccion ligada a los edges. Podemos viajar desde cualquier nodo adyacente y viceversa.

![[Pasted image 20230516212935.png]]

### Graph directed

En el grafico directed tenemos la direccion ligada a cada uno de los edges.

![[Pasted image 20230516213116.png]]
![[Pasted image 20230516213135.png]]

## Terminologia en graph

* **Path**: Es un camino a un nodo o vertice. Es un conjunto de edges desde el vertice inicial hasta el vertice final. Ejemplo: Path from e to C = [e, a, b, c]. Podemos tener un **Closed path** que tiene una ruta donde los nodos inicial y final son los mismos. Tambien podemos tener un **path simple** es cualquier path donde los nodos no se repiten.

![[Pasted image 20230516213513.png]]

* **Bucle**:  Es un edge que conecta a un nodo a si mismo.

![[Pasted image 20230516221959.png]]

* **Degree of node**: Es el numero de aristas que conectan un nodo.

![[Pasted image 20230516222121.png]]

En los graficos directed tenemos dos tipos de grados para cada nodo:  El **grado de entrada** y el **grado de salida**. El grado de entrada es el numero de aristas que entran al nodo, mientras que el grado de salida es el numero de aristas que salen del nodo.

![[Pasted image 20230516222312.png]]

* **Cycle graph** : Es un grafico simple donde tenemos todos los nodos conectados entre si y el numero de aristas es igual al numero de nodos del grafico.

![[Pasted image 20230516222431.png]]

* **Connected graph**: Es un graph donde podemos visitar cualquier nodo desde cualquier otro nodo. Si no es un connected graph es un disconnected graph.

![[Pasted image 20230516222556.png]]
* **Complete graph**: Es un graph donde cada nodo del grafo esta conectado a otro nodo del grafo.

![[Pasted image 20230516222730.png]]

* **Weighted graph:** Es un grafico en el que tenemos un valor o peso asignado a un edge que conecta dos nodos diferentes.

![[Pasted image 20230516222842.png]]
* **Simple graph:** Un grafico simple es un grafico que no tiene bucles ni edges paralelos.


## Formas de representar un graph

### Adjacency matrix

Representamos el grafico usando un array bidimensional (Array 2D) o un table hash. 

Ponemos 1 para representar la presencia de un edge, y 0 si no lo hay. En caso de un weighted graph, ponemos infinito si no hay presencia de un edge, o el peso si hay presencia del edge.

En el ejemplo `matrix[1][2]`es 1.

![[Pasted image 20230516223207.png]]

### Adjacency list

Usamos un array de linked list para representar el grafico.

![[Pasted image 20230516223520.png]]

