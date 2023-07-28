# Clausulas

Las clausulas son condiciones de modificacion utilizadas para definir los datos que desea seleccionar o manipular

* **FROM**: Se usa para releccionar registros de una tabla.

```SQL
SELECT * FROM name_table;
```

**Dato**: El asterisco selecciona a todos.

* **DISTINCT**: Se utiliza para eliminar registros duplicados de una tabla y solo recuperar los unicos. Solo la consulta SELECT usa la clausula DISTINCT.

```SQL
SELECT DISTINCT name_column1, name_column2 FROM name_table;
```

* **WHERE**: Funciona de manera a una condicion if, esta se puede combinar con operadores. Se puede utilizar para las consultas SELECT, DELETE o UPDATE.

```SQL
SELECT name_column
FROM name_table
WHERE condition;
```

* **LIMIT**: La clausula LIMIT se utiliza para especificar el numero de registros a devolver.

```SQL
SELECT name_column
FROM name_table
WHERE condition
LIMIT numero;
```

* **GROUP BY**: La clausula GROUP BY se usa para recopilar datos de varios registros y agruparlos por una o mas columnas. Por lo general se encuentra en declaraciones SELECT pero tambien se utiliza a menudo con funciones agregadas.

```SQL
SELECT name_column
FROM name_table
WHERE condition
GROUP BY name_column
```

* **HAVING**: La clausula HAVING especifica que registros agrupados se muestran en una instruccion SELECT con una clausula GROUP BY. Despues de que GROUP BY combine los registros, HAVING muestra cualquier registro agrupado por la clausula GROUP BY que satisfaga las condiciones de la clausula HAVING.

```SQL
SELECT name_column
FROM name_table
GROUP BY name_column
HAVING condition;
```

* **ORDER BY**: Se utiliza para clasificar el conjunto de resultados en orden ascendente (ASC) o descendente (DESC).

```SQL
SELECT name_column
FROM name_table
GROUP BY name_column
HAVING condition
ORDER BY name_column DESC;
```