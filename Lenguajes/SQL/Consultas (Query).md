# Consultas

Estas sentencias en SQL nos permitiran realizar consultas a nuestra base de datos.

## Crear una base de datos

Para empezar, debemos crear nuestra base de datos. Esto se realiza con el comando **CREATE DATABASE database_name**.

Para eliminar una base de datos utilizamos **DROP DATABASE database_name**.

```SQL

--Crear DATABASE

CREATE DATABASE database_name;

--Eliminar una DATABASE

DROP DATABASE database_name;
```

## Crear una tabla

Una vez que tengamos una base de datos podemos empezar a crear nuestras tablas o entidades con la instruccion **CREATE TABLE table_name (column_names tipo_valor restricciones)**.

```SQL
CREATE TABLE Clientes (
Id_Cliente int NOT NULL,
Nombre varchar(50) NOT NULL,
Apellido varchar(50) NOT NULL, 
Id_Localidad int NOT NULL
);
```

### Crear una tabla a partir de otra tabla

La nueva tabla obtiene las mismas definiciones de columna. Se pueden seleccionar todas las columnas o columnas especificas. Si crea una nueva tabla utilizando una tabla existente, la nueva tabla se completara con los valores existentes de la tabla anterior.

```SQL
CREATE TABLE new_table_name AS
	SELECT column1, column2,..
	FROM existing_table_name
	WHERE ....;
```

**Dato**: Para que el ID sea auto incremental debemos utilizar la funcion **AUTO_INCREMENT** que lo que va hacer es generar automaticamente valores numericos secuenciales cada vez que se inserta un registro en una tabla para un campo definido como incremento automatico.

## Operaciones CRUD

Antes que nada para realizar estas operaciones debemos indicar en que base de dato vamos a operar, para ello utilizamos la instruccion **USE database_name**.

### Insertar datos

El comando para insertar registros en una tabla es **INSERT INTO (columna1, column2, ....)** seguido de la palabra **VALUES (valor1, valor2, valor 3)**. Ademas es posible ignorar los campos que permiten valores nulos.

```SQL
INSERT INTO Clientes (Nombre, Apellido, Id_Localidad)
VALUES ('Juan', 'Gomez', 15);

--Podemos insertar varios registros a la vez utilizando comas.
INSERT INTO Clientes (Nombre, Apellido, Id_Localidad)
VALUES ('Juan', 'Gomez', 15),
('Pepe', 'Gomez', 19),
('Hugo', 'Gomez', 12);
```

Si estamos agregando valores para todas las columnas de la tabla, no es necesario especificar los nombres de las columnas en la consulta SQL. Sin embargo, hay que asegurarse que el orden de los valores sea el mismo que el de las columnas de la tabla.

![[Pasted image 20230516163850.png]]

### Seleccionar datos

La consulta **SELECT** sirve para obtener/seleccionar los datos que se encuentran dentro de una tabla. 

```SQL
-- Para seleccionar todos los campos de una tabla

SELECT * FROM nombre_table;

-- Para seleccionar algunas columnas, solamente debemos listarlos separados por coma

SELECT column1, column2 FROM table_name;

-- Podemos poner un alias temporal a la columna que mostramos con select. Un alias solo existe mientras dure esa consulta.

SELECT SUM(precio) AS 'Precio Total' FROM servicios;
```

Tambien podemos **concatenar** para poderlos unir con la funcion **CONCAT**.

```SQL
SELECT CONCAT(nombre, " ", apellido)
AS "Nombre Completo"
FROM reservaciones;
```

#### Copiar los datos de una tabla en una nueva tabla

```sql
SELECT *
INTO new_table
FROM old_Table
WHERE condition;
```

La nueva tabla se creara con los nombres y tipos de columnas definidos en la tabla anterior. Puede crear nuevos nombres de columna utilizando la clausula **AS**.

Si queremos copiar los datos a una nueva tabla en otra base de datos podemos utilizar la clausula **IN**.

```SQL
SELECT * INTO CustomersBackup2017 IN 'Backup.mdb'
FROM Customers;
```

#### Insertar datos copiados de una tabla a otra tabla ya creada

Para ello utilizamos las palabras reservadas **INSERT INTO** seguida de la tabla donde se insertaran los datos, seguida de la palabra reservada SELECT, seguida de las columnas que se copiaran, seguida de la palabra reservada FROM y la tabla de donde se copiaran los datos.

```SQL
INSERT INTO table2
SELECT * FROM table 1
WHERE condition;
```

### Update date

La instruccion **UPDATE** sirve para actualizar los registros existentes. Es necesario definir una condicion que permita identificar los registros que se quieran actualizar ya que si no especificamos se actualizaran todos los registros existentes en una tabla

```SQL
UPDATE name_table
SET columna1 = valor1, column2 = valor2, ...
WHERE condition;

-- Ejemplo: En este ejemplo actualizamos en la tabla clientes, el nombre y apellido donde el id del cliente sea 10

UPDATE Clientes SET Nombre = "Juan Carlos", Apellido = "Gomez" WHERE Id_Cliente = 10;
```

Podemos actualizar multiples registros al mismo tiempo tambien.

### Delete date

Para borrar registros existentes en una tabla necesitamos la instruccion **DELETE**. Nuevamente es necesario y muy importante tener una condicion que nos permita identificar los registros a eliminar, ya que si no especificamos se borra todo.

```SQL
DELETE FROM name_table WHERE condition;
```

**Dato:** MySQL viene con un modo activado por defecto que nos protege de realizar este tipo de consultas, cada vez que querramos realizar consultas de DELETE o UPDATE, nosotros tenemos que indicar un id en la condicion, y no un campo al menos que desactivemos el modo seguro.

**Dato:** SQL cuando borramos un registro, sigue quedando ocupado, entonces al insertar un nuevo registro, siempre se va agregar a lo ultimo.

#### Eliminar todos los datos dentro de una tabla

Para ello utilizamos **TRUNCATE TABLE** que eliminara todos los datos dentro de una tabla.

## Modificar una tabla que ya fue creada

**ALTER TABLE** permite modificar la estructura de una tabla existente. Por ejemplo, se pueden añadir o eliminar columnas, crear y destruir índices, cambiar el tipo de una columna existente o renombrar columnas o la propia tabla. También es posible modificar el comentario y el tipo de la tabla.

Para ello utilizamos la instrucción **ALTER TABLE** seguida del nombre de la tabla a modificar, y lo que sigue dependera lo que querramos modificar de la tabla.

### Añadir una columna

Utilizamos **ALTER TABLE** seguido del nombre de la tabla, seguido de la instrucción **ADD**, seguido del nombre de la columna a agregar, su tipo de dato y restriccion.

```SQL
ALTER TABLE name_table ADD name_column INT NOT NULL;
```

### Modificar una columna sin cambiar el nombre de una columna

Utilizamos **ALTER TABLE** seguido del nombre de la tabla, seguido de la instrucción **MODIFY COLUMN**, seguido de la columna a modificar y que es lo que queremos modificar.

```sql
ALTER TABLE name_table MODIFY COLUMN name_column INT NOT NULL;
```

Si queremos cambiarle el nombre

```SQL
ALTER TABLE name_table CHANGE name_column_old name_column_new INT NOT NULL;
```

### Eliminar una columna

Utilizamos **ALTER TABLE** seguido del nombre de la tabla, seguido de la instrucción **DROP COLUMN** seguido del nombre de la columna a eliminar.

```sql
ALTER TABLE name_table DROP COLUMN name_column;
```

### Renombrar tabla

Para renombrar una tabla ya creada  utilizamos la consulta **RENAME TABLE** seguido del nombre de la tabla, seguido de **TO** y seguido del nombre nuevo de la tabla.

```SQL
RENAME TABLE name_table_old TO name_table_new;
```

## Eliminar una tabla

```sql
DROP TABLE name_table;
```

## Eliminar una base de datos

```SQL
DROP DATABASE name_database;
```

## Show

Para obtener el codigo que se utiliza para crear la misma tabla creada anteriormente

```SQL
SHOW CREATE TABLE name_table;
```

Al ejecutar esta consulta nos devolvera una tabla donde deberemos hacerle click derecho al codigo de debajo de create table y copiar, luego lo pegamos en nuestra consulta y lo ejecutamos y crearemos la misma tabla.

**Dato**: Hay que eliminar las backticks del codigo copiado o tocar copy field(unquoted).

```sql
--SHOW TABLES sirve para ver las tablas de nuestra base de datos que estamos usando.

SHOW TABLES;

--SHOW DATABASES sirve para ver un registro de todas las bases que existen.

SHOW DATABASES;

--SHOW COLUMNS FROM sirve para ver informacion sobre las columnas de una tabla.

SHOW COLUMNS FROM name_table

--DESCRIBE hace lo mismo que SHOW COLUMNS FROM

DESCRIBE name_table

```