# Funciones definidas en SQL
En SQL, las funciones son bloques de código que se pueden utilizar para realizar tareas específicas. Las funciones pueden devolver un valor, una fila o una tabla.

La sintaxis general para crear una función definida por el usuario es la siguiente:

```sql
CREATE FUNCTION nombre_función ([parámetro1 [, parámetro2 ...]])
RETURNS tipo_de_valor
AS
BEGIN
  // Cuerpo de la función
END;

```

Para invocar una funcion, se utiliza la siguiente sintaxis:

```sql
nombre_función (valor1, valor2)
```

Ejemplo

```sql
CREATE FUNCTION add(a in, b int) 
RETURNS int   
	LANGUAGE SQL    
	IMMUTABLE    
	RETURNS NULL ON NULL INPUT    
	RETURN a + b

SELECT edad(2, 3);
```