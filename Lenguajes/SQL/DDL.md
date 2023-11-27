# Data Definition Language (DDL)

## Crear una base de datos

Para empezar, debemos crear nuestra base de datos. Esto se realiza con el comando **CREATE DATABASE database_name**. Ademas genera las entradas correspondientes en el **diccionario de datos**, que  es una estructura de la DB que tendra todas las definiciones que tiene mi estructura.

Para eliminar una base de datos utilizamos **DROP DATABASE database_name**.

```SQL

--Crear DATABASE

CREATE DATABASE database_name;

--Eliminar una DATABASE

DROP DATABASE database_name;
```
## Eliminar una base de datos

```SQL
DROP DATABASE name_database;
```
## Crear una tabla

Una vez que tengamos una base de datos podemos empezar a crear nuestras tablas o entidades con la instruccion **CREATE TABLE table_name (column_names tipo_valor restricciones)** donde vamos a definir el nombre de atributos, el tipo de dato y las restricciones de integridad, entre otras cosas. Esto tambien genera informacion en el diccionario de datos.

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
## Modificar una tabla que ya fue creada

**ALTER TABLE** permite modificar la estructura de una tabla existente. Por ejemplo, se pueden añadir o eliminar columnas, crear y eliminar restricciones de integridad, cambiar el tipo de una columna existente o renombrar columnas o la propia tabla. También es posible modificar el comentario y el tipo de la tabla.

Para ello utilizamos la instrucción **ALTER TABLE** seguida del nombre de la tabla a modificar, y lo que sigue dependera lo que querramos modificar de la tabla.
### Añadir una columna

Utilizamos **ALTER TABLE** seguido del nombre de la tabla, seguido de la instrucción **ADD**, seguido del nombre de la columna a agregar, su tipo de dato y restriccion.

```SQL
ALTER TABLE name_table ADD name_column INT NOT NULL;

-- Para añadir varias columnas

ALTER TABLE tableName
ADD (columnName1 datatype,
     columnName2 datatype,
     ...
     );
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
### Añadir o eliminar una restriccion

```SQL
-- Agregar restricciones

ALTER TABLE tableName
ADD CONSTRAINT constraintName
PRIMARY KEY (column1, column2, ... column_n);

-- Eliminar restricciones

ALTER TABLE tableName
DROP CONSTRAINT constraintName;
```
## Renombrar tabla

Para renombrar una tabla ya creada  utilizamos la consulta **RENAME TABLE** seguido del nombre de la tabla, seguido de **TO** y seguido del nombre nuevo de la tabla.

```SQL
RENAME TABLE name_table_old TO name_table_new;
```
## Eliminar una tabla

```sql
DROP TABLE name_table;
```
## Eliminar todos los registros de una tabla

Para eliminar todos los registros de una tabla, incluidos todos los espacios asignados para los registros que se eliminan sin eliminar la tabla se utiliza la consulta **TRUNCATE TABLE** seguida del nombre de la tabla.

```SQL
TRUNCATE TABLE table_name;
```

Recuerde, si bien `TRUNCATE TABLE`es más rápido y utiliza menos recursos del sistema y del registro de transacciones que `DELETE`, no invoca desencadenadores y no se puede revertir, así que utilícelo con precaución.

### Limitaciones de TRUNCATE TABLE

Truncar conserva la estructura de la tabla para uso futuro. Pero no puedes truncar una tabla que:

- Está referenciado por una restricción FOREIGN KEY. (Puede truncar una tabla que tenga una clave externa que haga referencia a sí misma).
- Participa en una vista indexada.
- Se publica mediante replicación transaccional o replicación de combinación.

Si intenta truncar una tabla con una restricción de clave externa, SQL Server le impedirá hacerlo y tendrá que utilizar la `DELETE`declaración en su lugar.

Para tablas particionadas, `TRUNCATE TABLE`elimina todas las filas de todas las particiones. La operación no está permitida si la tabla contiene columnas LOB `varchar(max), nvarchar(max), varbinary(max), text, ntext, image, xml`, o si la tabla contiene columnas de flujo de archivos o columnas de tipo de datos de geografía espacial, geografía, geometría y jerarquía, o cualquier columna de tipos de datos CLR definidos por el usuario.

**Dato**: En las operaciones DDL, las declaraciones COMMIT y ROLLBACK no se pueden realizar porque el motor MySQL confirma automaticamente los cambios.


