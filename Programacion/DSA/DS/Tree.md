# Tree

Un **tree** es una estructura de datos no lineal, es decir, los datos no se almacenan de forma secuencial. En cambio, estan organizados en una estructura jerarquica. Un arbol es una coleccion de **nodos** que estan conectados por **edges** y tiene una relacion jerarquica entre los nodos.

El **nodo superior** del arbol se denomina **raiz(root)** y los nodos inferiores se denominan **nodos secundarios**. Cada nodo puede tener varios nodos secundarios, y estos nodos secundarios tambien pueden tener sus propios nodos secundarios, formando una estructura recursiva. Los nodos secundarios a su vez tienen un solo **nodo principal**, que es el nodo predecesor o padre.

Esta estructura de datos es un método especializado para organizar y almacenar datos en la computadora para usarlos de manera más efectiva. Una razón para usar árboles podría ser porque desea almacenar información que naturalmente forma una jerarquía

![[Pasted image 20230509152035.png]]

Los nodos los cuales no tienen ningun nodo hijo se denominan **leaf nodes**.

Algunas de las operaciones mas basicas que se pueden realizar en un arbol son: insercion, busqueda y eliminacion. Ademas hay tres formas de atravesar un arbol, **inorder, preorder y postoder**.

## Propiedades de un arbol

* **Numeros de aristas**: Una arista se puede definir como la conexion entre dos nodos. Si un arbol tiene N nodos, tendra (N-1) aristas. Solo hay un camino desde cada nodo a cualquier otro nodo del arbol

* **Profundidad de un nodo**: La profundidad de un nodo se define como la longitud del camino desde la raiz hasta ese nodo. Cada edge agrega 1 unidad de longitud al camino. Por lo tanto, tambien se puede definir como el numero de aristas en el camino desde la raiz del arbol hasta el nodo.

* **Altura de un nodo**: La altura de un nodo se puede definir como la longitud del camino mas largo desde el nodo hasta un leaf node.

* **Altura del arbol**: La altura de un arbol es la longitud del camino mas largo desde la raiz del arbol hasta un nodo de leaf node.

* **Grado de un nodo**: El recuento total de subarboles adjuntos a ese nodo se denomina grado del nodo. El grado de un leaf node debe ser 0.

![[Pasted image 20230509152857.png]]
![[Pasted image 20230514155542.png]]

## Tipos de trees

### Binary tree

Es el tipo de arbol en el que el numero maximo de nodos secundarios que un nodo puede tener es dos.

![[Pasted image 20230509154109.png]]

### Binary search tree

Es un arbol binario donde los nodos estan en formato ordenado.

* El valor de los nodos de la izquierda deben ser menor al del nodo principal.
* El valor de los nodos de la derecha deben ser mayor al del nodo principal.
* Todos los nodos de la izquierda deben ser menor al nodo raiz.
* Todos los nodos de la derecha deben ser mayor al nodo raiz.
* Ambos subarboles izquierdo y derecho tambien son BST.

![[Pasted image 20230509154629.png]]

#### Tipos de arboles de busqueda binaria

###### Unbalanced Trees

Un arbol binario desequilibrado es aquel que no esta equilibrado.

![[Pasted image 20230514154311.png]]
![[Pasted image 20230515161544.png]]
###### Balanced trees

Un arbol binario balanceado o equilibrado, se define como un arbol binario en el que la altura del subarbol izquierdo y derecho de cualquier nodo difiere en no mas de 1.

![[Pasted image 20230514154320.png]]
![[Pasted image 20230515161608.png]]

### Full Binary Tree

Un **arbol binario lleno** es un tipo especial de arbol binario en el que cada nodo principal interno tiene dos o ningun hijo. Tambien se conoce como arbol binario propio.

![[Pasted image 20230514160505.png]]

#### Propiedades

```markdown
Let, i = the number of internal nodes
       n = be the total number of nodes
       l = number of leaves
      λ = number of levels
```

1.  El número de hojas es `i + 1`.
2.  El número total de nodos es `2i + 1`.
3.  El número de nodos internos es(n-1) / 2.
4.  El número de hojas es `(n + 1) / 2`.
5.  El número total de nodos es `2l – 1`.
6.  El número de nodos internos es `l – 1`.
7.  El número de hojas es como máximo .`2^λ - 1`

### Complete Binary Tree

Un arbol binario completo es un tipo especial de arbol binario en el que todos los niveles del arbol se llenan por completo, excepto los nodos de nivel mas bajo que se llenan desde la izquierda tanto como sea posible. Todos los elementos de hoja deben inclinarse hacia la izquierda. 1.  El último elemento hoja podría no tener un hermano correcto, es decir, un árbol binario completo no tiene que ser un árbol binario full.

![[Pasted image 20230514160912.png]]

## Ventajas

* Los árboles (con cierto orden, por ejemplo, BST) proporcionan acceso/búsqueda moderados (más rápido que la Lista enlazada y más lento que las matrices).   
* Los árboles proporcionan una inserción/eliminación moderada (más rápida que las matrices y más lenta que las listas enlazadas desordenadas).   
* Al igual que las listas enlazadas y, a diferencia de las matrices, los árboles no tienen un límite superior en el número de nodos, ya que los nodos se enlazan mediante punteros.