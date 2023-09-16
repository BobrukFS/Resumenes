# Bases de datos relacionales

En este tipo de base de datos, los datos estan relacionados conceptualmente, no por su utilizacion y su implementacion en maquina. El centro de los modelos relacionales son las **entidades** y las **relaciones** entre ellas.

En este tipo de modelo el lugar y la forma en el que se almacenan los datos no tienen relevancia.

La base de datos relacional nos permite agrupar los datos en forma de **tablas**, donde dentro de las mismas, los datos se organizan en **filas** y **columnas**. La interseccion de un **registro** (fila o tupla) y un **campo** (columna) nos da el dato.

Las bases de datos relacionales pueden utilizar el modelo entidad-relacion como el modelo relacional.

SQL por ejemplo, es un lenguaje de programacion para trabajar con base de datos relacionales.

## Ventajas y desventajas de una base de datos relacional

### Ventajas

* Menor redundancia. No hace falta tanta repeticion de datos.
* Menor espacio de almacenamiento. Gracias a una mejor estructuracion de los datos.
* Acceso a los datos mas eficiente. La organizacion de los datos produce un resultado mas optimo en rendimiento.
* Integridad de los datos.
* Mayor seguridad en los datos.
* Independencia de los datos y los programas y procesos. Esto permite modificar los datos sin modificar el codigo de las aplicaciones.

### Desventajas

-   Segmentación de los datos: La normalización puede generar consultas complejas que abarcan varias tablas, lo que puede afectar negativamente el rendimiento.

*   Peor rendimiento frente a las bases de datos NoSQL: Los requisitos de consistencia de datos en el modelo relacional pueden disminuir la velocidad de escritura en las transacciones.

[[Modelos de datos]]
[[SQL]]