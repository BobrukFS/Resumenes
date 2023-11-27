# Joins SQL

Las **JOINS** SQL se utilizan para recuperar datos de dos o más tablas de datos, en función de una columna relacionada entre ellas. Los tipos clave de JOIN incluyen:

* **INNER JOIN**: Es un tipo de combinación que devuelve los registros con valores coincidentes en ambas tablas. Esta operación compara cada fila de la primera tabla con cada fila de la segunda tabla para encontrar todos los pares de filas que satisfacen el predicado de unión.  Si no hay ninguna coincidencia, el resultado devuelto es vacío.

```SQL
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers 
ON Orders.CustomerID = Customers.CustomerID;
```

* **LEFT JOIN**: Devuelve todos los registros de la tabla de la izquierda y los registros coincidentes con la tabla de la derecha. 

```SQL
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders 
ON Customers.CustomerID = Orders.CustomerID;
```

* **RIGHT JOIN**: Devuelve todos los registros de la tabla derecha y los registros coincidentes con la tabla izquierda. 

```SQL
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
RIGHT JOIN Customers 
ON Orders.CustomerID = Customers.CustomerID;
```

* **FULL JOIN**: Se encarga de mostrar todas las filas de ambas tablas, sin importar que no existan coincidencias (usará NULL como un valor por defecto para dichos casos)..

```SQL
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
FULL OUTER JOIN Orders 
ON Customers.CustomerID = Orders.CustomerID;
```

* **SELF JOIN**: Es una operación SQL estándar en la que una tabla se une a sí misma. Esto puede parecer contrario a la intuición, pero en realidad es bastante útil en escenarios donde es necesario realizar operaciones de comparación dentro de una tabla. Básicamente, se utiliza para combinar filas con otras filas en la misma tabla cuando hay una coincidencia según la condición proporcionada. Es importante tener en cuenta que, dado que se trata de una operación de unión en la misma tabla, se deben utilizar alias para las tablas para evitar confusiones durante la operación de unión

```SQL
SELECT a.column_name, b.column_name
FROM table_name AS a, table_name AS b
WHERE a.common_field = b.common_field;
```

* **CROSS JOIN**: La unión cruzada en SQL se utiliza para combinar cada fila de la primera tabla con cada fila de la segunda tabla. También se le conoce como producto cartesiano de las dos tablas. El aspecto más importante de realizar una unión cruzada es que no requiere ninguna condición para unirse. El problema con la unión cruzada es que devuelve el producto cartesiano de las dos tablas, lo que puede generar una gran cantidad de filas y un uso intensivo de recursos. Por lo tanto, es fundamental utilizarlos con prudencia y sólo cuando sea necesario.

```SQL
SELECT column_name(s)
FROM table1
CROSS JOIN table2;
```

O tambien alternativamente

```SQL
SELECT column_name(s)
FROM table1, table2;
```