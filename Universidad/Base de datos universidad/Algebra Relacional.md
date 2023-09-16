# Algebra Relacional

El **álgebra relacional** es un conjunto de operaciones matemáticas utilizadas en bases de datos relacionales para realizar consultas y manipulación de datos. Estas operaciones incluyen selección, proyección, unión, intersección, diferencia, producto cartesiano entre otras. Estas operaciones ayudan a buscar, filtrar y combinar datos en tablas de una base de datos dando una nueva relacion.

El algebra relacional es un conjunto de operaciones que realizo sobre distintas relaciones produciendo una nueva relacion. 
## Operadores

Hay dos grandes grupos, por un lado tenemos los **operadores basicos** y por el otro los **operadores derivados**.

Por otra parte tambien lo podemos clasificar de la siguiente manera:

* **Operador unario**: Trabajan con una sola relacion. Genera una nueva relacion.

R(N) --> R(M)

Se aplica una relacion R con N atributos y devuelve otra relacion R con M atributos.

* **Operador binario**: Trabaja con mas de una relacion. Genera una nueva relacion.

R(N) x R(S) --> R(M)

Se aplica una relacion R con N atributos y devuelve otra relacion R con M atributos.
### Seleccion

Este operador es un operador unario que va a trabajar sobre una determinada relacion(tabla). Se emplea para **seleccionar un subconjunto de las tuplas de una relacion que satisfacen una condicion de seleccion**. Puede visualizarse como una particion horizontal de la relacion en dos conjuntos de tuplas: las que satisfacen la condicion son seleccionadas y las que no, descartadas. El grado de la relacion resultante de una operacion SELECCION es el mismo que el de R. El numero de tuplas en la relacion resultante es siempre menor que o igual que el numero de tuplas en R.

En general, SELECCION esta designada como:

![[Pasted image 20230907144937.png]]

donde el simbolo sigma se utiliza para especificar el operador de SELECCION, mientras que la condicion de seleccion es una expresion logica especificada sobre los atributos de la relacion R. El resultado de SELECCION tiene los mismos atributos que R.

La expresión lógica especificada en <condición de selección> está constituida por un número de cláusulas de la forma:

![[Pasted image 20230907145100.png]]

Los operadores de comparacion se pueden aplicar a los atributos cuyos dominios son vlaores ordenados, como los de tipo numerico o de fecha. Los de cadena de caracteres tambien se consideran del mismo tipo debido a la secuencia en los codigos. Si el dominio de un atributo es un conjunto de valores desordenados, solo pueden usarse los operadores = o diferente a.

Las clausulas pueden estar conectadas por operadores logicos and, or y not.

La operacion SELECCION es **conmutativa**, es decir:

![[Pasted image 20230907145500.png]]

Por lo tanto, una secuencia de SELECTs anidados puede ser evaluada en cualquier orden.

Adicionalmente, podemos remplazar una secuencia de SELECTs anidados por un único SELECT cuya condición es la conjunción de las condiciones de cada SELECT individual

![[Pasted image 20230907145800.png]]

Ejemplo:  El operador seleccion donde voy a indicar el atributo que es marca = quilmes sobre la relacion cerveza entonces le voy a estar indicando que me traiga las mismas tuplas que tengan marca igual a quilmes.

![[Pasted image 20230907145833.png]]
### Proyeccion

La PROYECCION selecciona ciertas columnas de la tabla y descarta otras. Si sólo estamos interesados en algunos atributos de una relación, usamos la operación PROYECCIÓN para planear la relación sólo sobre esos atributos. Por consiguiente, el resultado de esta operación puede visualizarse como una partición vertical de la relación en otras dos: una contiene las columnas (atributos) necesarias y otra las descartadas.

![[Pasted image 20230907215819.png]]

donde pi es el símbolo usado para representar la operación PROYECCIÓN, mientras que lista de atributos contiene la lista de campos de la relación R que queremos, los atributos van separados con coma. El resultado de la operacion PROYECCION solo tiene los atributos especificados en la lista de atributos en el mismo orden a como aparecen en la lista. Por tanto, su grado es igual al numero de atributos contenidos en lista de atributos.

Si la lista de atributos solo incluye atributos no clave de R, es posible que se dupliquen tuplas. La operacion PROYECCION **elimina cualquier tupla duplicada**, por lo que el resultado de la misma es un conjunto de tuplas y, por consiguiente, una relacion valida. Esto se conoce como eliminacion de duplicados.

El numero de tuplas de una relacion resultante es siempre menor o igual que el de las contenidas en R.

Ejemplo:

![[Pasted image 20230907220236.png]]

Otro ejemplo:

![[Pasted image 20230907233353.png]]
![[Pasted image 20230907233443.png]]
**Dato**: Siempre se analiza primero lo que esta entre parentesis.
### Union,  Interseccion y Diferencia

Para combinar los elementos de dos conjuntos se utilizan varias operaciones de la teoría de conjuntos, como la UNIÓN, la INTERSECCIÓN y la DIFERENCIA DE CONJUNTOS (llamada también a veces MENOS, o MINUS). Todas ellas son operaciones binarias, es decir, se aplican a dos conjuntos (de tuplas).

Cuando se refieren a las bases de datos relacionales, las relaciones sobre las que se aplican estas tres operaciones deben tener el mismo tipo de tuplas; esta condición recibe el nombre de compatibilidad de unión o **type compatible**. Dos relaciones R(A1, A2, . . . , An) y S(B1, B2, . . ., Bn) se dice que son de **type compatible** si tienen el mismo grado n y si  dom(Ri) = dom(Si).

Esto significa que para que sea compatible ambas relaciones tienen el mismo número de atributos y que cada par de atributos correspondiente cuenta con el mismo dominio.

#### Union

El resultado de esta operación, especificada como R U S, es una relación que incluye todas las tuplas que están tanto en R como en S o en ambas, R y S. Las tuplas duplicadas se eliminan.

![[Pasted image 20230907231943.png]]

El resultado es una relación T que incluye todas las tuplas de R o todas las de S o las de ambas, excluyendo repeticiones.

![[Pasted image 20230907232000.png]]

La union es una operacion conmutativa

![[Pasted image 20230907232046.png]]

La union tambien es una operacion asociativa

![[Pasted image 20230907232103.png]]

Ejemplo:

![[Pasted image 20230907232124.png]]
#### Interseccion

El resultado de esta operacion, es una relacion que incluye todas las tuplas que pertenecen a la vez en R y en S.

![[Pasted image 20230907232620.png]]
![[Pasted image 20230907232642.png]]

Observe que la INTERSECCIÓNpuede expresarse en términos de unión y diferencia de conjuntos del siguiente modo:

![[Pasted image 20230907232711.png]]

La interseccion es una operacion conmutativa

![[Pasted image 20230907232742.png]]

La interseccion es una operacion asociativa

![[Pasted image 20230907232749.png]]

EJemplo:

![[Pasted image 20230907232804.png]]
**Dato**: Si no hay valores en comun el resultado es vacio por lo que cualquier operacion que se aplique a un resultado vacio es invalida.
#### Diferencia de conjunto

El resultado de esta operacion, especificada como R - S, es una relacion que incluye todas las tuplas que estan en R pero no en S. Esta operacion es una operacion binaria y no es conmutativa.

Ejemplo:

![[Pasted image 20230907232441.png]]

### Producto cartesiano

El operador PRODUCTO CARTESIANO me permite hacer las combinacion de tuplas entre ambas relaciones. 

Es un operador binario que relaciona dos relaciones produciendo una relacion resultante nueva y distinta que va a incluir todas las combinaciones posibles.

![[Pasted image 20230908114717.png]]
El resultado es una relación T que incluye todas las combinaciones posibles de cada tupla de R con cada tupla de S, y sus atributos corresponden a los de  R seguidos por los de S

![[Pasted image 20230908114728.png]]

No es una operacion conmutativa.

Es una operacion asociativa.

![[Pasted image 20230908114810.png]]

Por ejemplo, me va a combinar la primer tupla de plato con la primera de vino, con la segunda y asi sucesivamente.

![[Pasted image 20230908114650.png]]

### Rename

Este operador es un operador unario. Al renombrar una relacion lo que estamos haciendo es generar una nueva relacion.

![[Pasted image 20230907235129.png]]

Renombra la relacion y sus atributos

![[Pasted image 20230907235143.png]]

![[Pasted image 20230907235151.png]]

Para renombrar una relacion:

![[Pasted image 20230908125537.png]]

Renombrar todos los atributos y generando una relacion nueva sin nombre (anonima):

![[Pasted image 20230908125617.png]]

Renombrar atributos en individual:

![[Pasted image 20230908125657.png]]
![[Pasted image 20230908125715.png]]

Renombrar Relacion y atributos a la vez con un nuevo nombre en la relacion

![[Pasted image 20230908125746.png]]

o

![[Pasted image 20230908125803.png]]

Ejemplo: 
![[Pasted image 20230908115124.png]]
![[Pasted image 20230908115143.png]]

### Join Natural

El operador JOIN Natural es un operador binario.

![[Pasted image 20230908115349.png]]

donde q es el numero de atributos en comun entre R(N) y R(M)

El resultado es una relación T que incluye todas las combinaciones posibles de cada tupla de R con cada tupla de S, siempre que la combinación satisfaga que el atributo de R con el mismo nombre que el atributo de S tengan el mismo valor.

![[Pasted image 20230908115333.png]]

**Dato**: Debe haber al menos un atributo con el mismo nombre entre ambas relaciones.

No es una operacion conmutativa.

Es una operacion asociativa

![[Pasted image 20230908115436.png]]

Ejemplos:

![[Pasted image 20230908115516.png]]
![[Pasted image 20230908115527.png]]
### Join condicional

El operador JOIN Condicional trabajo con una relacion u otra que tengan atributos que se llamen distinto pero que tengan el mismo dominio o el mismo valor.

El resultado es una relación T que incluye todas las combinaciones posibles de cada tupla de R con cada tupla de S, siempre que la combinación satisfaga la condición del join; sus atributos corresponden a los de  R seguidos por los de S.

![[Pasted image 20230908115916.png]]
![[Pasted image 20230908120006.png]]

Una forma equivalente es:

![[Pasted image 20230908120027.png]]

No es una operacion conmutativa.

Es una operacion asociativa

![[Pasted image 20230908120045.png]]

**Dato**: Como una de las condiciones del producto condicional es que no haya atributos repetidos para luego poder acceder a todos, el grado de la relación resultante de la operación concatena las columnas de ambas. Si tenías 10 en una y 7 en la otra, tu resultado tiene 17 columnas

Ejemplo:

![[Pasted image 20230908115746.png]]
### Division
El operador de división (/) define una relación sobre el conjunto de atributos C, incluido en la relación A, y que contiene el conjunto de valores de C, que en las tuplas de A están combinadas con cada una de las tuplas de B

Ejemplo:

![[Pasted image 20230908124745.png]]

## Resumen

![[Pasted image 20230908125924.png]]
![[Pasted image 20230908125933.png]]
![[Pasted image 20230908125950.png]]