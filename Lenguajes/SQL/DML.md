# Data Manipulation Language(DML)

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

**Dato**: Si quiero que tome el valor DEFAULT, pongo como valor DEFAULT.
### Seleccionar datos

La consulta **SELECT** sirve para recuperar/seleccionar los datos que se encuentran dentro de una tabla.  Los datos devueltos se almacenan en una tabla de resultados, llamada conjunto de resultados.

```SQL
-- Para seleccionar todos los campos de una tabla

SELECT * FROM nombre_table;

-- Para seleccionar algunas columnas, solamente debemos listarlos separados por coma

SELECT column1, column2 FROM table_name;

-- Podemos poner un alias temporal a la columna que mostramos con select. Un alias solo existe mientras dure esa consulta.

SELECT SUM(precio) AS 'Precio Total' FROM servicios;

-- Otro ejemplo

SELECT e.name, d.department 
FROM employees AS e, departments AS d
WHERE e.dept_id = d.dept_id;
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

UPDATE Clientes SET Nombre = "Juan Carlos", Apellido = "Gomez" WHERE id_Cliente = 10;
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


![[Pasted image 20231001181704.png]]