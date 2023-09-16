# Base de datos

Una base de datos es una recopilacion organizada de informacion o datos estructurados de acuerdo a un modelo y relacionados entre si, que normalmente se almacena de forma electronica en un sistema informatico. Una base de datos esta administrada por un **sistema de gestion de bases (DBMS)**. En conjunto, los datos y el DMBS, reciben el nombre de **sistema de bases de datos**.

![[Pasted image 20230831112154.png]]

Una base de datos representa algun aspecto del mundo real, tiene algun grado de interaccion con eventls del mundo real y un publico que esta activamente interesado en su contenido. Los usuarios finales de una base de datos pueden interactuar con esta por ejemplo con trasacciones, y la base de datos debe reflejar los cambios tan pronto como sea posible.

Los **datos** son todo aquello que se pueden registrar en nuestra base de datos y que no tienen un significado, que siendo procesados nos devuelve informacion que se define como el conjunto de datos que tiene significado para el usuario. 

![[Pasted image 20230512192335.png]]

Hay dos categorias de datos:

* **Datos del usuario**: Son aquellos datos que van a ser utilizado por las aplicaciones.
* **Datos del sistema**: Son aquellos datos que el sistema de gestion de bases utiliza para su propia gestion, como los usuarios registrados para operar la base, los permisos de estos usuarios, etc.


## Software de gestion de bases de datos(DBMS)

El **software de gestion de bases de datos** (DBMS o SGBD) nos permiten manipular y gestionar bases de datos. Facilita los procesos de definicion, construccion, manipulacion y comparticion de bases de datos entre varios usuarios y aplicaciones. **Definir** una base de datos implica especificar los tipos de datos, estructuras y restricciones de los datos que se almacenaran en la base de datos. La definicion tambien se almacena en esta ultima en forma de **catalogo o diccionario** de la base de datos, es lo que se conoce como metadatos. La **construccion** de la base de datos es el proceso consistente en almacenar los datos en algun medio de almacenamiento controlado por el DBMS. La **manipulacion** de una base de datos incluye funciones como la consulta de la base de datos para recuperar datos especificos, actualizar la base de datos, etc. Compartir una base de datos permite que varios usuarios y programas accedan a la base de datos de forma simultanea. 

Nos permiten realizar operaciones **CRUD** (create, read, update, delete) en nuestra base de datos:

* crear datos
* leer datos
* modificar datos
* eliminar datos 

Para que nosotros podamos realizar las operaciones CRUD desde una aplicacion debemos realizar una **consulta**(**query**) a la base de datos y nos va a devolver informacion. 

El DBMS tiene mecanismos para controlar las inconsistencias (Por ejemplo, si tenemos dos usuarios que quieren modificar el mismo registro). Ademas, tiene mecanismos especiales para el backup y el manejo de grandes volumenes de datos.

La informacion queda almacenada en almacenamiento persistente, es decir, en disco duro, etc.

Los software de gestion de bases de datos (DBMS) realizan la funcion de interfaz entre el usuario final o los programas y la base de datos, organizando los datos y permitiendo el acceso. Uno de los ejemplos de DBMS es [[MySQL]], SQLite, SQL server.
## Caracteristicas deseadas de una BD - DBMS

Todas las bases de datos deben cumplir con los siguientes objetivos:

* Tiene que ser **versatil**, es decir, que dependiendo de los usuarios o las aplicaciones traten a los datos de formas distintas.
* Tiene que ser independiente/transparente, es decir el acceso a la informacion es independiente de la forma en la que estan guardando los datos.
* **Seguridad** .
* **Recuperacion ante fallos**.
* **Catalogo** para poder consultar la informacion sobre la estructura de la base.
* Tiene que atender con la **rapidez** adecuada.
* Tiene que tener un **indice de redundancia lo mas bajo posible**. Esto significa que no debe hacer repeticion o uso exagerado de una palabra.
* Tiene que disponer de una alta capacidad de acceso para ganar el mayor tiempo posible en la realizacion de consultas.
* Tiene que tener un alto **indice de integridad**, esto significa garantia de la calidad de la informacion que hay en una DB, y no se deberia ser posible incluir datos con valores invalidos, incoherencias. Las restricciones de integridad proporcionan un medio de asegurar que los cambios que se hacen en la BD por usuarios autorizados no resultan en una perdida de la consistencia de los datos.
* Tiene que tener un **alto control de acceso y modificacion concurrente**, esto significa que al tener muchos usuarios consultando y escribiendo en una misma base de datos no puede haber fallos en la insercion de datos, errores por redundancia o lenta actualizacion. Es decir, distintos usuarios deben poder acceder a la misma informacion al mismo tiempo, y manejar el conflicto que dos usuarios modifiquen y/o eliminen la misma informacion al mismo tiempo.
* **Manejo transaccional** se debe agrupar muchas modificaciones en una unidad de trabajo, de forma tal que se hagan o todas o ninguna. Si una aplicacion falla en el medio de la transaccion, no queda registrada.

[[Bases de datos relacionales]]
[[Indice en base de datos]]
[[Anomalias]]