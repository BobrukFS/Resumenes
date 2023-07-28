# Base de datos

Una base de datos es una recopilacion organizada de informacion o datos estructurados, que normalmente se almacena de forma electronica en un sistema informatico. Una base de datos esta controlada por un **sistema de gestion de bases (DBMS)**. En conjunto, los datos y el DMBS, reciben el nombre de sistema de bases de datos.

Los **datos** son todo aquello que se pueden registrar en nuestra base de datos y que no tienen un significado, que siendo procesados nos devuelve informacion que se define como el conjunto de datos que tiene significado para el usuario. 

![[Pasted image 20230512192335.png]]

Hay dos categorias de datos:

* **Datos del usuario**: Son aquellos datos que van a ser utilizado por las aplicaciones.
* **Datos del sistema**: Son aquellos datos que el sistema de gestion de bases utiliza para su propia gestion, como los usuarios registrados para operar la base, los permisos de estos usuarios, etc.


## Software de gestion de bases de datos(DBMS)

El software de gestion de bases de datos nos permiten manipular y gestionar bases de datos. Nos permiten realizar operaciones **CRUD** (create, read, update, delete) en nuestra base de datos:

* crear datos
* leer datos
* modificar datos
* eliminar datos 

Para que nosotros podamos realizar las operaciones CRUD debemos realizar una consulta(**query**) a la base de datos. 

Ademas el DBMS se va a encargar de controlar las inconsistencias (Por ejemplo, si tenemos dos usuarios que quieren modificar el mismo registro).

Los software de gestion de bases de datos (DBMS) realizan la funcion de interfaz entre el usuario final o los programas y la base de datos, organizando los datos y permitiendo el acceso. Uno de los ejemplos de DBMS es [[MySQL]], SQLite.

## Organizacion de una base de datos

Todas las bases de datos deben cumplir con los siguientes objetivos:

* Tiene que ser **versatil**, es decir, que dependiendo de los usuarios o las aplicaciones traten a los datos de formas distintas.
* Tiene que atender con la **rapidez** adecuada.
* Tiene que tener un **indice de redundancia lo mas bajo posible**. Esto significa que no debe hacer repeticion o uso exagerado de una palabra.
* Tiene que disponer de una alta capacidad de acceso para ganar el mayor tiempo posible en la realizacion de consultas.
* Tiene que tener un **alto indice de integridad**, esto significa que al tener muchos usuarios consultando y escribiendo en una misma base de datos no puedo haber fallos en la insercion de datos, errores por redundancia o lenta actualizacion.


[[Modelos de datos]]
[[Indice en base de datos]]
[[Bases de datos relacionales]]
[[Anomalias]]