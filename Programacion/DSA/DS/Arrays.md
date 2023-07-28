
# Arrays

Un array es una estructura de datos lineal y es una coleccion de elementos (asi se denomina a los valores almacenados en un array) del mismo tipo de dato almacenados en ubicaciones de memoria contigua con un tamaño fijo, lo que da como resultado direcciones fácilmente calculables para los elementos almacenados y esto permite un acceso más rápido a un elemento en un índice específico. Cada elemento se lo identifica con un index. El primer elemento del array esta indexado por un subindice de 0 y al numero de elementos se lo denomina extension o rango del vector.

Un arrays puede almacenarse en variables y tratarse de la misma manera que cualquier otro tipo de dato, la diferencia es que podemos acceder individualmente a cada elemento dentro de el.

![[Pasted image 20230428184848.png]]

La idea del array es representar muchas instancias de una variable.

## Caracteristicas de un array

* Los arrays utilizan una estructura de datos basada en indices que ayuda a identificar facilmente a cada uno de los elementos del array utilizando el indice. Tenemos acceso de tiempo constante a cada elemento.

* Los valores dentro de un array deben ser del mismo tipo de dato.

* Un array tambien puede manejar estructura de datos mas complejas almacenando datos en un array bidimensional (Matrix).

* Un array tambien se usa para implementar otras estructuras de datos como stacks, qeues, tablas hash, etc.

* El proceso de busqueda en un arreglo se puede hacer muy facilmente. 

* Un array tiiene un tamaño fijo para evitar la fuga de memoria (memory leak). Por lo que es una estructura de datos estatica.

## Inicializar un array

Se puede inicializar con valores en el momento de la declaracion o mas tarde mediante una declaracion de asignacion. Nosotros podemos o no declarar el tamaño del array.

La forma de inicializar un array dependera del lenguaje que estemos tratando.

La inicializacion es una asignacion de memoria estatica o en tiempo de compilacion, lo que significa que la memoria del elemento del array se asigna cuando se compila un programa.

Se puede crear un **array dinamico**, que asigna memoria dinamicamente, es decir asignar el espacio de memoria durante el tiempo de ejecucion. En JS los arrays YA son dinamicos.

## Operaciones realizadas en un array

### Acceder a los elementos

Se puede acceder a los elementos de un array por su indice, que comienza desde 0 y aumenta hasta el tamaño del array menos 1. 

![[Pasted image 20230430225527.png]]

**Complejidad de tiempo:** O(1);

### Sorting elements

Los elementos de un array se pueden clasificar en orden ascendente o descendente mediante algoritmos como la bubble sort, insertion sort o quick sort.

### Inserting elements

Los elementos se pueden insertar en un array en una ubicacion especifica, pero esta operacion puede llevar mucho tiempo porque requiere cambiar los elementos existentes en la matriz.

![[Pasted image 20230430225628.png]]
![[Pasted image 20230430225645.png]]

**Complejidad de tiempo:**

O(1) para insertar un solo elemento al final del array.
O(N) complejidad lineal para insertar un elemento en otro lugar que no sea el final ya que debo modificar el indice de todos los elementos.
 
### Deleting elements 

Los elementos se pueden eliminar de un array cambiando los elementos que vienen despues para llenar el espacio.

![[Pasted image 20230430225840.png]]
![[Pasted image 20230430225851.png]]

**Complejidad de tiempo:** 

O(1) si se remueve el elemento final.

O(N) si es en cualquier otro lugar que no sea en el elemento final ya que se tiene que modificar el indice de todos los elementos.

### Updating elements

Los elementos de una matriz se pueden actualizar o modificar asignando un nuevo valor a un indice especifico.

![[Pasted image 20230430225913.png]]
![[Pasted image 20230430225929.png]]

**Complejidad de tiempo:** O(1) es decir complejidad constante.

### Traversing elements

Los elementos de un array se pueden recorrer en orden, visitando cada elementos a la vez. Mediante un bucle.

**Complejidad de tempo**: O(N)

## Tipos de arrays

### Array unidimensional (arrays 1-D)

Se puede imaginar como una fila, donde los elementos se almacenan uno tras otro

![[Pasted image 20230428202242.png]]

### Array multidimensional (Matrix) 

#### Array bidimensional (arrays 2-D)

Se pueden considerar como un array de arrays o como un array que consta de filas y columnas

![[Pasted image 20230428202323.png]]

#### Array tridimensional (arrays 3-D)

Se puede considerar un array de arrays bidimensionales.

![[Pasted image 20230428202511.png]]

### Diferencias

![[Pasted image 20230428202907.png]]

## Ventajas y desventajas de usar arrays

### Ventajas

-   **Acceso eficiente a los elementos en tiempo constante:** los arrays brindan acceso directo y eficiente a cualquier elemento de la colección debido a que el indice de cada elemento se asigna directamente a una direccion de memoria particular . Acceder a un elemento de una matriz es una operación O(1), lo que significa que el tiempo necesario para acceder a un elemento es constante y no depende del tamaño de la matriz.
-   **Recuperación rápida de datos:** las matrices permiten una recuperación rápida de datos porque los datos se almacenan en ubicaciones de memoria contiguas. Esto significa que se puede acceder a los datos de manera rápida y eficiente sin necesidad de estructuras de datos o algoritmos complejos.
-   **Eficiencia de la memoria:** las matrices son una forma eficiente de memoria de almacenar datos. Debido a que los elementos de una matriz se almacenan en ubicaciones de memoria contiguas, el tamaño de la matriz se conoce en el momento de la compilación. Esto significa que se puede asignar memoria para toda la matriz en un bloque, lo que reduce la fragmentación de la memoria. Ademas no se desperdicia espacio con enlaces o punteros.
-   **Versatilidad:** las matrices se pueden usar para almacenar una amplia gama de tipos de datos, incluidos números enteros, números de coma flotante, caracteres e incluso estructuras de datos complejas, como objetos y punteros.
-   **Fácil de implementar:** las matrices son fáciles de implementar y comprender, lo que las convierte en una opción ideal para los principiantes que aprenden programación de computadoras.
-   **Compatibilidad con hardware:** la estructura de datos de matriz es compatible con la mayoría de las arquitecturas de hardware, lo que la convierte en una herramienta versátil para programar en una amplia gama de entornos.
- Muchas tareas de programacion requieren iterar a traves de todos los elementos de una estructura de datos. Las matrices son buenas para esto porque exhiben una excelente localidad de memoria. La continuidad fisica entre los accesos sucesivos a los datos ayuda a explotar la memoria cache de alta velocidad en las arquitecturas informaticas modernas.

### Desventajas

* No se puede ajustar su tamaño en medio de la ejecucion de un programa. El programa fallara si queremos agregar un elemento en `[n + 1]`.  Podemos compensar esto asignando arreglos extradamente grandes pero esto puede desperdiciar espacio, restringiendo nuevamente lo que los programas pueden hacer. Aunque podemos ampliar los arrays de manera eficiente a medida que lo necesitamos, gracias a los arrays dinamicos.  Cada vez que nos quedamos sin espacio duplicamos su tamaño, por ejemplo, comenzamos con un array de tamaño m, y cuando no tengamos espacio duplicamos su tamaño, es decir, 2m. Este proceso de duplicacion asigna una nueva matriz contigua de tamaño 2m, copia el contenido de la matriz anterior en la mitad inferior de la nueva y luego devuelve el espacio utilizado por el array anterior al sistema de asignacion de memoria.Así, cada uno de los n elementos se mueve solo dos veces en promedio, y el trabajo total de gestionar el array dinámico es el mismo O(n) que habría sido si se hubiera asignado de antemano un solo array de tamaño suficiente. Lo principal que se pierde al usar arrays dinámicos es la garantía de que cada inserción tome tiempo constante en el peor caso. Ten en cuenta que todos los accesos y la mayoría de las inserciones serán rápidos, excepto aquellas pocas inserciones que provocan el duplicado del array. Lo que obtenemos en su lugar es una promesa de que la inserción del elemento n se completará lo suficientemente rápido como para que el esfuerzo total realizado hasta ahora siga siendo O(n).


## Aplicaciones de un array

-   **Almacenamiento y acceso a datos** : las matrices se utilizan para almacenar y recuperar datos en un orden específico. Por ejemplo, se puede utilizar una matriz para almacenar las puntuaciones de un grupo de estudiantes o las temperaturas registradas por una estación meteorológica.
-   **Clasificación:** las matrices se pueden utilizar para clasificar los datos en orden ascendente o descendente. Los algoritmos de clasificación, como la clasificación por burbujas, la clasificación por fusión y la clasificación rápida, dependen en gran medida de las matrices.
-   **Búsqueda** : se pueden buscar matrices para elementos específicos utilizando algoritmos como la búsqueda lineal y la búsqueda binaria.
-   **Matrices** : las matrices se utilizan para representar matrices en cálculos matemáticos, como la multiplicación de matrices, el álgebra lineal y el procesamiento de imágenes.
-   **Pilas y colas:** las matrices se utilizan como estructura de datos subyacente para implementar pilas y colas, que se utilizan comúnmente en algoritmos y estructuras de datos.
-   **Gráficos** : las matrices se pueden usar para representar gráficos en informática. Cada elemento de la matriz representa un nodo en el gráfico y las relaciones entre los nodos están representadas por los valores almacenados en la matriz.
-   **Programación dinámica** : los algoritmos de programación dinámica a menudo usan matrices para almacenar resultados intermedios de subproblemas para resolver un problema más grande.

### Aplicaciones de array en Java

-   **Almacenamiento de colecciones de datos:** las matrices se utilizan a menudo para almacenar colecciones de datos del mismo tipo. Por ejemplo, se puede usar una matriz de enteros para almacenar un conjunto de valores numéricos.
-   **Clasificación y búsqueda:** las matrices se utilizan a menudo para clasificar y buscar datos. Por ejemplo, la clase Arrays en Java proporciona métodos como sort() y binarySearch() para ordenar y buscar elementos en una matriz.
-   **Implementación de estructuras de datos:** las matrices se utilizan como estructura de datos subyacente para varias otras estructuras de datos, como pilas, colas. Por ejemplo, se puede usar una implementación basada en matrices de una pila para almacenar elementos en la pila.
-   **Procesamiento de imágenes:** las matrices se utilizan comúnmente para almacenar los valores de píxeles de una imagen. Por ejemplo, se puede usar una matriz bidimensional para almacenar los valores RGB de una imagen.

[[String]]