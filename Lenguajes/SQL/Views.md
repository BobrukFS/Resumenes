# Views

Las views en SQL son objetos virtuales que permiten consultar datos de una base de datos como si fueran una tabla. Las views se crean a partir de una o varias tablas y se pueden utilizar para simplificar las consultas, limitar el acceso a los datos o crear nuevos datos virtuales.

Para crear una view, se utiliza la sentencia **CREATE VIEW**. Esta sentencia especifica el nombre de la view y la consulta que se utilizará para generar los datos de la view.

Una vez que se ha creado una view, se puede consultar como si fuera una tabla.

Las views también se pueden utilizar para limitar el acceso a los datos. Por ejemplo, se puede crear una view que solo contenga los datos de los clientes que tienen un determinado nivel de acceso. Esto permite controlar qué datos pueden ver los usuarios, sin necesidad de modificar las tablas subyacentes. Además, las views se pueden utilizar para crear nuevos datos virtuales. Por ejemplo, se puede crear una view que calcule el descuento total de un pedido, en función de los productos que contiene y el nivel de descuento del cliente. Esto permite a los desarrolladores crear aplicaciones más complejas, sin necesidad de escribir consultas SQL complejas.

```sql
/*Crea una vista llamada alumnos_de_quilmes*/
CREATE VIEW alumnos_de_quilmes AS SELECT * FROM alumno WHERE universidad = ‘UNQ’;
/*Una vez creada la views se pueden consultar como si fuera una tabla.*/
SELECT * FROM alumnos_de_quilmes;
```

Tambien podemos crear una nueva vista o reemplazar una vista existente mediante la sintaxis:

```sql
CREATE OR REPLACE VIEW alumnos_de_quilmes AS SELECT * FROM alumno WHERE universidad = ‘UNQ’;
```
Tambien podemos eliminar una vista mediante la sintaxis:

```sql
--Si no existe la vista dara error, por lo que se recomienda utilizar IF EXISTS
DROP VIEW alumnos_de_quilmes;
```

Tambien podemos actualizar una vista y su tabla subyacente si esta es una vista simple y no compleja (es decir, que incluye clausulas, joins, etc).

```sql
UPDATE customer_view
SET country = 'USA'
WHERE customer_name =
```

**Dato**: A la hora de nombrar una view evitar el nombre view en el nombre de la vista. Tampoco incluyamos condiciones OrderBy y Where.