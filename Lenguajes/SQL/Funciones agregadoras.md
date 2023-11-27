# Funciones agregadoras

Las funciones de agregacion son funciones incorporadas que computan un valor de resultado unico correspondiente a un conjunto de valores de entrada, es decir, es un calculo sobre un conjunto de valores, devolviendo un solo valor, excepto por la funcion COUNT. Estas funciones ignoran los valores NULL.

Las funciones de agregación básicas que soportan todos los gestores de datos son las siguientes:

* **COUNT()**: Devuelve el numero total de filas seleccionadas por la consulta. Si pongo * cuenta todas las filas de la tabla.

```sql
SELECT COUNT(name_column) FROM name_table;
```

Se puede utilizar con la clausula group by.

* **MIN()**: Devuelve el valor minimo del campo que especifiquemos. Acepta columnas con datos numericos y textos.

```SQL
SELECT MIN(name_column) FROM name_table;
```

* **MAX()**: Devuelve el valor maximo del campo que especifiquemos. Acepta columnas con datos numericos y textos.

```SQL
SELECT MAX(name_column) FROM name_table;
```

La función `MAX()` solo devolverá una única fila como resultado. Si varias filas contienen el valor más alto y desea obtener todas estas filas, no debe usar `MAX()`. Una mejor opción sería ordenar la columna y luego  `LIMIT` el resultado hasta la primera fila.

* **SUM()**: Suma los valores del campo que especifiquemos. Solo se puede utilizar en columnas numericas. Omite los valores NULL.

```SQL
SELECT SUM(name_column) FROM name_table;
```

* **AVG()**: Devuelve el valor promedio del campo que especifiquemos. Solo se puede utilizar en columnas numericas. Devolvera un error si se usa con tipos de datos no numericos.

```SQL
SELECT AVG(name_column) FROM name_table;
```

* **IFNULL()**: Permite devolver un valor alternativo si una expresion es NULL.

```SQL
SELECT ProductName, UnitPrice * (UnitsInStock + IFNULL(UnitsOnOrder, 0)
FROM Products
);
```

* **EXTRACT(dato a extraer from columna de donde se extrae )** : Se utiliza para extraer una parte de una fecha o hora.
```SQL
	ALTER TABLE tabla_nombre ADD CONSTRAINT fecha_no_octubre_ni_noviembre CHECK (EXTRACT(Month from fecha) NOT IN ( 10 , 11));
```

Estas funciones son basicas en SQL, pero cada sistema gestor de base de datos relacionales ofrece su propio conjunto de funciones agregadas.

Todas estas funciones se aplican a una sola columna, que especificaremos entre parentesis, excepto la funcion COUNT, que se puede aplicar a una columna o indicar un `“*”`. La diferencia entre poner el nombre de una columna o un `“*”`, es que en el primer caso no cuenta los valores nulos para dicha columna, y en el segundo si.