# Algoritmos

El algoritmo se define como un proceso o conjunto de instrucciones (procedimiento) bien definidas que normalmente se utilizan para resolver un grupo particular de problemas en un tiempo finito. Un algoritmo debe resolver un problema general bien especificado. Un problema algoritmico se especifica describiendo el conjunto completo de **instancias** en las que debe trabajar y su salida despues de ejecutarse en una de estas instancias. Una instancia se refiere a un ejemplo o caso especifico de un problema que se debe resolver utilizando el algoritmo, es decir, un input. Entonces un algoritmo es un procedimiento que toma cualquiera de las posibles instancias de entrada (inputs) y lo transforma en la salida deseada (outputs). Un algoritmo es una serie ordenada y finita de instrucciones o pasos que se siguen para resolver un problema específico o realizar una tarea determinada. Los algoritmos son procedimientos precisos y sistemáticos que garantizan una solución correcta si se siguen correctamente. Se caracterizan por ser deterministas, es decir, producen el mismo resultado para un conjunto de datos de entrada dado. Los algoritmos son utilizados ampliamente en programación y computación, y se basan en reglas explícitas y lógica rigurosa.

Ejemplo:

```
Problem : Sorting
Input : A sequence of n keys a1, ... an.
Output : The permutation(reordering) of the input sequence such that a1 <= a2 <= an-1 <= an
```

Una instancia en este ejemplo podria ser un array de nombres, o una lista de numeros.

Hay tres propiedades deseables para un buen algoritmo: 

* Correctos, es decir, toma cualquiera de las posibles instancias de entrada y lo transforma en la salida deseada,
* Eficientes
* Faciles de implementar

Hay veces que todos los objetivos no pueden ser alcanzados simultaneamente. Los algoritmos correctos suelen venir con una prueba de correcion, que es una explicacion del porque sabremos que el algoritmo lleva cada instancia del problema al resultado deseado.

Un diseñador de algoritmos debe ser capaz de demostrar que un algoritmo es incorrecto buscando aquellos inputs que no dan un output deseado. Son contraejemplos.

Existe una diferencia entre los algoritmos y las heuristicas. Las heurísticas, por otro lado, son métodos o enfoques más generales utilizados para abordar problemas complejos en los que no se conocen algoritmos eficientes o que son demasiado costosos computacionalmente. Las heurísticas son reglas prácticas o "reglas generales" que se utilizan como guías aproximadas para tomar decisiones o resolver problemas. A diferencia de los algoritmos, las heurísticas no garantizan una solución óptima o correcta en todos los casos. Sin embargo, son útiles en situaciones en las que se requiere una solución aceptable en un tiempo razonable.Las heurísticas a menudo se basan en el conocimiento y la experiencia previa, y pueden permitir soluciones más rápidas o aproximadas al evitar explorar todas las posibilidades. Aunque pueden ser menos precisas que los algoritmos, las heurísticas son valiosas cuando el tiempo o los recursos son limitados, o cuando se enfrentan problemas complejos que no tienen una solución perfecta o claramente definida. En resumen, mientras que los algoritmos son procedimientos precisos y sistemáticos que garantizan una solución correcta, las heurísticas son enfoques más generales que ofrecen soluciones aproximadas y rápidas, basadas en reglas prácticas y experiencia previa. Ambos enfoques tienen su lugar en la resolución de problemas, y su elección depende de la naturaleza del problema y de los recursos disponibles.

![[Pasted image 20230619225539.png]]
## Diagrama de flujo

Un **diagrama de flujo** es una **representacion grafica** con la ayuda de diferentes simbolos, formas y lineas. El proposito principal del diagrama de flujo es analizar los diferentes procesos de forma visual. 

![[Pasted image 20230501161251.png]]

Ejemplo:

![[Pasted image 20230501161304.png]]

## Indice

[[Problema del vendedor ambulante (TSP)]]

### Arrays


### String

### Linked List

### Stacks

### Queue

### Hash Table

### Tree

[[Implementacion de un Binary Search Tree]]
[[Check if a binary search tree]]
[[Verificar si un arbol binario es un arbol binario full]]
[[Verificar si un arbol binario es un arbol binario completo]]
[[Verificar si un arbol binario esta balanceado]]
[[Recorrer un arbol inorder]]
[[Recorrer un arbol preorder]]
[[Recorrer un arbol postorder]]