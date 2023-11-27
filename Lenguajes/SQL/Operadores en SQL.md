# Operadores en SQL

La clausula **WHERE, HAVING y CHECK** nos sirve para definir condiciones, podemos utilizar para ello operadores aritmeticos, operadores de comparacion y operadores logicos (AND, OR y NOT).

## Otros operadores

* **IS NULL** : Se utiliza para probar valores vacios.

* **IS NOT NULL**: Se utiliza para probar valores no vacios.

* **IN**: Se utiliza para seleccionar aquellos campos que coincidan con alguna condicion de una lista proporcionada. Ademas evita el uso excesivo de OR. Ejemplo ("Exe", "Sofia"). La lista proporcionada puede ser una condicion o muchas.

* **LIKE**: Se utiliza para buscar o seleccionar con algun patron en la columna. Esto se puede utilizar acompañado de comodines. Los **comodines** se utilizan para sustituir caracteres "%" **representa cero, uno o varios caracteres** y `_` representa un solo caracter.

* **BETWEEN**: Se utiliza para seleccionar valores dentro de un rango dado. Los valores pueden ser numeros, texto o fechas. Tiene 2 argumentos, el valor inicial y el valor final, que tienen que ir separados por un AND. Para mostrar los productos fuera del rango utilizamos **NOT BETWEEN**.

* **UNION**: Se utiliza para combinar el conjunto de resultados de dos o mas SELECT. Cada declaracion SELECT dentro debe tener el mismo numero de columnas. Las columnas tambien deben tener tipos de datos similares. Las columnas en cada declaracion SELECT tambien deben estar en el mismo orden.
* **EXIST**: Se utiliza para probar la existencia de cualquier registro en una subconsulta. El operador devuelve verdadero si la subconsulta devuelve uno o mas registros.
* **ANY**: Supongamos que la subconsulta devuelve una lista de valores v1, v2, …, vx. El operador ANY devuelve TRUE si cualquier comparación (scalar_expression, vi) devuelve TRUE. De lo contrario, devuelve FALSE. Por cada fila de la subconsulta se evalúa la comparación con cada uno de los valores devueltos y si la comparación es True para alguno de los valores ANY es verdadero, si la comparación no se cumple con ninguno de los valores de la consulta, ANY da False a no ser que todos los valores devueltos por la subconsulta sean nulos en tal caso ANY dará NULL. Si la subconsulta no devuelve filas ANY da False incluso si expresion es nula. Hay que tener en cuenta que el operador SOME es equivalente al operador ANY.
* **ALL**: El operador ALL selecciona los valores si todos los registros de subconsulta cumplen la condicion.
