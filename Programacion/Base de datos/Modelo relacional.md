# Modelo relacional

El modelo relacional es un modelo de datos que se utiliza para representar la información en una base de datos relacional. el modelo relacional es una forma de representar y organizar los datos en una base de datos relacional utilizando tablas, columnas y filas. Se basa en el álgebra relacional y utiliza claves primarias y claves foráneas para establecer las relaciones entre las tablas.

En este modelo, los datos se almacenan en **tablas** que están relacionadas entre sí. Cada tabla representa una entidad o conjunto de entidades, y cada **columna** de la tabla representa un atributo de esa entidad. Las **filas** de la tabla representan las instancias o **registros** de la entidad.

El nombre de las columnas, se llaman **campos**. El valor del campo es la interseccion entre el registro y la columna.

La clave primaria es un atributo o conjunto de atributos que identifica de manera única cada registro de la tabla. Las claves foráneas son atributos que hacen referencia a una clave primaria de otra tabla y se utilizan para establecer relaciones entre las tablas.

Una de las ventajas del modelo relacional es que permite la normalización de los datos, es decir, la eliminación de redundancias y la minimización de la duplicidad de datos. Además, el modelo relacional es muy flexible y escalable, lo que lo hace adecuado para una amplia variedad de aplicaciones.

El modelo Relacional se enfoca en la representación de los datos en tablas, donde cada tabla tiene filas (registros) y columnas (atributos). En este modelo, las relaciones entre las tablas se establecen mediante claves primarias y claves foráneas. El modelo Relacional utiliza lenguajes de consulta como SQL para interactuar con los datos y realizar operaciones como inserción, actualización, eliminación y consulta de datos.

El modelo relacional se utiliza para implementar esta estructura en un sistema de gestión de bases de datos (DBMS) como MySQL, SQL Server o PostgreSQL.

El dominio dentro de la estructura del Modelo Relacional es el **conjunto de valores que puede tomar un atributo**.

![[Pasted image 20230512214231.png]]

## Restricciones de integridad

La integridad se refiere a la correcion de la informacion contenida en la base de datos. Las restricciones de integridad proporcionan un medio de asegurar que los cambios que se hacen en la BD por usuarios autorizados no resultan en una perdida de la consistencia de los datos.

## Normalizacion

La **normalizacion** es la tecnica de estandarizacion y validacion de datos que se utiliza para diseñar las tablas y establecer las relaciones entre ellas. Esto nos permite una mayor organización para eliminar la redundancia de datos y proteger la integridad de los mismos. Sin la normalizacion, tendriamos datos redundantes los cuales traen aparejados problemas de mantenimiento ademas de ocupar espacio en el disco duro. El proposito es producir un conjunto estable de las relaciones que sea un modelo fiel de las operaciones de la empresa. Lograr un diseño flexible que permita extender el modelo cuando se necesite representar nuevos atributos, conjunto de entidades y relaciones, es decir, escalabilidad. Diseñar la base de datos fortaleciendo cierto tipos de restricciones de integridad.

Con la normalizacion evitamos:

* **Redundancia de los datos**
* **Anomalias de actualizacion**
* **Anomalias de borrado**
* **Anomalias de insercion**

Las formas normales se pueden clasificar en:

**1.**       **Primera Forma Normal (1FN)**
**2.**       **Segunda Forma Normal (2FN)**
**3.**       **Tercera Forma Normal (3FN)**
**4.**       **Cuarta Forma Normal (4FN)**
**5.**       **Quinta Forma Normal (5FN)**

Se realizara el proceso de normalizacion sobre la siguiente tabla de ejemplo:

![[Pasted image 20230512214850.png]]
Podemos encontrar los siguientes problemas en esta tabla:

1. Datos duplicados como nombres de provincia, estados de cuenta, etc .
2. Campos con varios datos.
3. Datos relacionados.
4. Podríamos tener errores en la relación de Provincias y Localidades. Por algún error una localidad pudo haber quedado junto a una provincia que no le correspondía.
5. Por algún error humano, alguien pudo haber escrito mal el nombre de una provincia o localidad. Encontrar y solucionar en la base de datos ese incidente puede ser muy incómodo.
6. No tenemos control si hay emails o CVUs duplicados.
7. Los procesos de búsqueda y actualización son ineficientes. Por ejemplo, si quisiéramos buscar y reemplazar el email de un usuario como Pascual Vargas.

### Primera forma normal (1FN)

Una tabla esta en **primera forma normal** cuando todos los datos son atomicos, es decir, cada atributo tiene su propia columna y todas las columna contienen el mismo tipo de datos y solo deben tener un valor, ademas no debe haber grupos repetidos. 

Como vemos en el ejemplo, la primera forma normal no se cumple por el campo email. En la primera y en la quinta tupla tenemos dos emails:

![[Pasted image 20230512215901.png]]

Para solucionarlo debemos eliminar el atributo que no cumple dicha condicion y tendremos que crear una tabla con dicho atributo, en el ejemplo emails que contenga las columnas email, que funcionara como clave primaria (PK), y una columna Id_Cliente, que funcionara como Clave foranea que apunta hacia el id del cliente, esta debe ser del mismo tipo de dato y la misma extension que la clave primaria hacia la que hace referencia.

![[Pasted image 20230512220029.png]]

El resultado final es que tenemos una tabla con todos los datos de los usuarios, y una segunda tabla que nos permite relacionar los emails con los datos de usuario. Asi si un usuario tiene N emails, en esta nueva tabla tendremos N mails relacionados con el mismo id de usuario. Esto nos permite que los procesos de busqueda y actualizacion sean eficiente y evita campos con varios datos.

### Segunda forma normal (2FN)

Una tabla esta en **Segunda Forma Normal (2FN)**, cuando se agregan atributos que no forman parte de ninguna clave a las condiciones de la primera forma normal, dependiendo de forma completa de la clave principal. Su funcionamiento depende de la clave primaria. Esta sirve para eliminar los datos redundantes, es decir, la redundancia es la repeticion de una palabra o dato.

La importancia de una buena normalización es que además de prevenir errores y ser eficiente en el uso del sistema, nos ayuda a realizar tareas de mantenimiento mucho más simples.

El problema que vamos a resolver es la falta de normalización de las columnas Provincia y Localidad.

Para empezar, sera necesario:

1. Crear las tablas Provincias y Localidades

2. Eliminar el la columna Provincia de la tabla Clientes ¿Por qué eliminamos la columna provincia? Porque el dato de la provincia lo podemos obtener sabiendo la localidad. Todas las localidades pertenecen a una única provincia, así es que, si se sabe la localidad, se sabe la provincia.

Entonces, ahora obtendremos la segunda forma normal, ya que obtendremos la provincia desde la tabla localidades y la localidad desde la tabla clientes. Además, creamos la tabla EstadosCuentas con Id_Estado (PK) y Nombre.

Al aplicar la segunda forma normal nos quedarían las tablas Clientes, Provincias y Localidades:

![[Pasted image 20230512220300.png]]
Ahora volvamos a los problemas que mencionamos anteriormente :

1.       Podríamos tener errores en la relación de Provincias y Localidades. Por algún error una localidad pudo haber quedado junto a una provincia que no le correspondía. Este problema ya no existe, todas las relaciones de provincia y localidades existen en una única tabla, y de ser necesario cambiar una relación la tarea se simplifica a editar el registro de una única tabla.

2.        Por algún error humano, alguien pudo haber escrito mal el nombre de provincia o localidad. Encontrar y solucionar en la base de datos ese incidente puede ser muy incómodo. Nuevamente este problema se soluciona editando un único registro, en una única tabla.

### Tercera forma normal (3FN)

Para que una tabla este en la **Tercera Forma Normal**, a las dos condiciones anteriores hay que agregarle que los atributos que no son clave no pueden depender de manera transitiva de una clave cantidada. Aquí se deben eliminar las columnas que no dependen de la clave principal. Esta forma normal es considerada como el estandar a cumplir por los esquemas relacionales.

Siguiendo el ejemplo, tenemos que agregar la tabla Cuentas la cual tiene los atributos CVU (PK), Id_Estado e Id_Cliente y en la tabla Clientes eliminaremos a columna CVU y Id_EstadoCuenta quedando las tablas de la siguiente forma:

![[Pasted image 20230512220511.png]]

Con el resultado obtenido, en la tabla Cuentas ahora tenemos la posibilidad de mantener la información del CVU y el estado de la cuenta de una forma más eficiente y desacoplada de la tabla Clientes. La cual se ha reducido significativamente a los datos que son relevantes para los detalles de un cliente como nombre, apellido y localidad.

### Cuarta Forma Normal (4FN)

El objetivo de la cuarta forma normal es evitar que nuestras tablas posean dependencias multivaluadas. Las dependencias multivaluadas son aquellas donde la existencia de dos o más relaciones N:M (Muchos a muchos) causando redundancia.

Como nuestro ejemplo de momento no cuenta con ninguna instancia de relación de muchos a muchos (N:M) tenemos que asumir q ue necesitamos habilitar los movimientos que tiene cada cliente con uno o más tipos de moneda.

Para esto crearemos la tabla Monedas, la cual tendría los atributos Id_Moneda y Nombre, y una tabla ClientesMonedas que tendrá las columnas Id_Cliente e Id_Mone da, en donde asignaremos con qué tipos de monedas puede operar cada cliente:

![[Pasted image 20230512220655.png]]
En la tabla ClientesMoneda vemos que un cliente puede tener muchas monedas, y que una moneda puede ser usada por muchos clientes (N:M).

### Quinta forma Normal (5FN)

Una relación se encuentra en 5FN si ya pasó por la normalización 4FN y además, las dependencias existentes son las dependencias de Join o de unión con sus proyecciones. Esto ocurre cuando podemos obtener la tabla original por medio de la unión de sus proyecciones, relacionándose entre sí a través de la clave primaria o alguna de sus claves alternativas.

Esto quiere decir que si mediante la unión de los campos de las tablas, podemos recuperar la tabla inicial. Si hacemos el ejercicio de ir conectando todos los id de las tablas, veremos que es posible reconstruir la tabla inicial.