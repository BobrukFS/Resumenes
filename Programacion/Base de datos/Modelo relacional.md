# Modelo relacional

El **modelo relacional** es un modelo de datos que se utiliza para representar la información en una base de datos relacional, mediante una coleccion de **relaciones**. Las relaciones son las **tablas**, estas estan relacionados entre si y para establecer relaciones entre ellas se utilizan claves primarias y claves foraneas para la integridad referencial. 

En este modelo, los datos se almacenan en **tablas** que están relacionadas entre sí. Cada tabla representa una entidad o conjunto de entidades, y cada **columna** de la tabla representa un atributo de esa entidad. Las **filas**(**tupla**) de la tabla representan las instancias o **registros** de la entidad. El nombre de las columnas individuales, se llaman **campos**. 

El **dominio** dentro de la estructura del Modelo Relacional es el **conjunto de valores que puede tomar un atributo**.

![[Pasted image 20230512214231.png]]

El **grado de la relacion** es la cantidad de atributos. El **estado de la relacion** es el conjunto de tuplas, el conjunto de instancias que contiene la relacion(tabla).

Ejemplos:

![[Pasted image 20230903191304.png]]
![[Pasted image 20230903191324.png]]
![[Pasted image 20230903191401.png]]

Ejemplo con notacion alternativa:

![[Pasted image 20230904004636.png]]

En cada instancia de la relacion vamos a tener una referencia

![[Pasted image 20230903191518.png]]

En el contexto de las bases de datos, el término "mapear" se refiere a la acción de establecer una relación o correspondencia entre elementos en una base de datos y elementos en otra.

![[Pasted image 20230904004506.png]]
Ejemplo entidad debil y recursiva:

![[Pasted image 20230903200511.png]]
![[Pasted image 20230903200519.png]]

**Dato**: La clave foranea se representa con un subrayado ondulado.
## Cardinalidades en el MR

### (1,1) a (1,1)

![[Pasted image 20230903192131.png]]
### (0,1) a (0,1)

No se puede hacer el mismo tratamiento que en (1,1) a (1,1) debido a que si un cliente no tiene una mascota, entonces el atributo nombre tendria un valor nulo. Entonces la solucion es hacer una relacion (tabla) nueva.

![[Pasted image 20230903192846.png]]
### (1,n) a (1,n)

![[Pasted image 20230903191638.png]]
![[Pasted image 20230903191709.png]]
Estoy llevando del lado n de la relacion el dni del cliente. Arrastramos la clave del lado 1 de la relacion al lado n, y lo agrego como clave foranea, es decir absorbe la clave primaria del (1 a 1) y la pone como foranea, tambien absorbe los atributos relacionales si es que contiene.

![[Pasted image 20230903192415.png]]
![[Pasted image 20230903191700.png]]
### (1, 1) a (1, n)

![[Pasted image 20230903192156.png]]

### (0,1) a (1,1)

No puedo tratarlo como (1,1) a (1,1) porque hay mascotas que no tienen clientes, entonces la clave foranea DNI seria null en esos casos.  Pero si puedo absorber la clave primaria de mascota, ya que cliente adopta siempre a una mascota.

![[Pasted image 20230903192623.png]]
### (0,1) a (1,n)

![[Pasted image 20230903192715.png]]
### (0,1) a (0,n)

![[Pasted image 20230903192928.png]]

### (0,n) a (1,1)

![[Pasted image 20230903192939.png]]

### (0,n) a (1,n)

![[Pasted image 20230903192949.png]]

### (0,n) a (0,n)

![[Pasted image 20230903193006.png]]
## Ventajas

Una de las ventajas del modelo relacional es que permite la normalización de los datos, es decir, la eliminación de redundancias y la minimización de la duplicidad de datos. Además, el modelo relacional es muy flexible y escalable, lo que lo hace adecuado para una amplia variedad de aplicaciones.

El modelo Relacional utiliza lenguajes de consulta como SQL para interactuar con los datos y realizar operaciones como inserción, actualización, eliminación y consulta de datos. El modelo relacional se utiliza para implementar esta estructura en un sistema de gestión de bases de datos (DBMS) como MySQL, SQL Server o PostgreSQL.

### Diferencias entre MER y MR. 

* Las tablas en el MER eran entidades mientras que en el MR se denominan **relaciones**. 
* Todas las entidades y las relaciones del MER se representan con "relaciones", es decir, tablas en el MR.
* Las relaciones(tablas) estan compuestas por campos(=atributos=columna) y registros. Las relaciones en el MR mapean entidades y relaciones del MER. No hay orden establecido en la forma de presentar los atributos.


