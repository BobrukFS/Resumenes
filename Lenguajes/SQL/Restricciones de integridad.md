# Restricciones de integridad o Integrity constraints

Las **restricciones** son reglas predefinidas que se aplican a los datos en una sola columna o en varios columnas, para mantener la integridad, precision y confiabilidad de los datos en esa columna. Si los datos insertados cumplen con la regla de restriccion, se insertaran con exito, mientras que si los datos insertados violan la restriccion definida, la operacion de insercion se cancelara.

Las restricciones se pueden considerar a **nivel de columna**, donde se especifica como parte de la definicion de la columna y se aplicaran solo a esa columna, o se declaran de forma independiente a **nivel de tabla**. 

Las restricciones se pueden crear al comenzar una tabla o agregarse a una tabla ya creada, sin embargo se verificada previamente la regla de restriccion en los datos existentes antes de crear esa restriccion.

Si queremos agregar una restriccion a una tabla ya creada, y tenemos un dato que no cumple con la regla de restriccion, lo primero que hay que hacer es actualizar la tabla cambiando los valores que no son validos para que asi podamos agregar la restriccion.

## Tipos de restricciones que se usan habitualmente

* **NOT NULL(NN)**: Se utiliza una restriccion NOT NULL en SQL para evitar insertar valores NULL en la columna especificada, considerandolo entonces NULL como un valor no aceptado para esa columna.

```SQL
--Agregar restriccion al crear la tabla

CREATE TABLE Example (id INT NOT NULL);

--Agregar restriccion a una columna de una tabla ya creada

ALTER TABLE Example MODIFY id INT NOT NULL;
```

* **UNIQUE**: Se utiliza para garantizar que no se inserten valores duplicados en una columna especifica o combinacion de columnas que participen en la restriccion UNIQUE y que no formen parte de la clave primaria. Es decir, el indice que se crea automaticamente cuando define una restriccion UNIQUE garantizara que no haya dos filas en esa tabla que puedan tener el mismo valor para las columnas que participan en ese indice, con la capacidad de insertar solo un valor NULL. Se puede definir varias restricciones UNIQUE por tabla.

```SQL

--Agregar restriccion al crear la tabla

CREATE TABLE Example (
id INT NOT NULL, 
UNIQUE (id)
);

--Si queremos añadirle un nombre a dicha restriccion

CREATE TABLE Example (id INT NOT NULL, 
CONSTRAINT name_restriccion UNIQUE (id)
);

--Si queremos añadir la restriccion a una columna de una tabla ya creada

ALTER TABLE Example
ADD CONSTRAINT name_restriccion UNIQUE (id);

--Si queremos eliminar la restriccion de una columna

ALTER TABLE Example 
DROP INDEX name_restriccion;
```

* **PRIMARY KEY(PK)**: La restriccion PRIMARY KEY consta de una columna o varios columnas con valores que identifican de forma unica cada fila de la tabla. Si la clave primaria se define en varias columnas, entonces se pueden insertar valores duplicados en cada columna individualmente, pero es importante mencionar que los valores de combinacion de todas las columnas de clave primaria deben ser unicos. Solo se puede definir una PRIMARY KEY por cada tabla. Esta restriccion no permite valores nulos. Una restriccion PRIMARY KEY tiene automaticamente una restriccion UNIQUE.

```SQL
--Agregar restriccion al crear la tabla

CREATE TABLE Example (
id INT NOT NULL,
CONSTRAINT name_restriccion PRIMARY KEY (id)
);

--Otra opcion

CREATE TABLE Example (
id INT NOT NULL,
PRIMARY KEY (id)
);

--Agregar una clave compuesta al crear la tabla

CREATE TABLE Example(
	id INT NOT NULL, 
	codigo INT NOT NULL,
	PRIMARY KEY(id, codigo),
);

--Agregar restriccion a uan columna de una tabla ya creada

ALTER TABLE Example
ADD CONSTRAINT name_restriccion PRIMARY KEY (id);

--Eliminar una PRIMARY KEY

ALTER TABLE Example
DROP PRIMARY KEY;
```

**Dato**: Si bien no es necesario ponerle constraint para asignarle un nombre, lo que buscamos es ser comunicativo por lo que es recomendable.

* **FOREIGN KEY (FK)**: La llave foranea o FOREIGN KEY, es una columna o varias columnas, que sirven para hacer referencia o señalar cual es la llave primaria de otra tabla. La columna o columnas señaladas como FOREIGN KEY, solo podran tener valores que ya existan en la PRIMARY KEY de la otra tabla. La tabla con la FOREIGN KEY se denomina tabla secundaria y la tabla con la PRIMARY KEY se denomina tabla principal o de referencia.

```SQL
-- Para crear una clave foranea hay que recordar que necesitamos tener una segunda tabla y tulizamos un campo que nos permita relacionar ambas tablas

CREATE TABLE Example (
OrderID INT NOT NULL,
Orderumber INT NOT NULL,
PersonID INT,
PRIMARY KEY (OrderID),
CONSTRAINT name_restriccion
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);

--Para crear una clave foranea en una tabla ya creada

ALTER TABLE Tabla_origen ADD FOREIGN KEY (campo_tabla_origen)
REFERENCES Tabla_destino (campo_clave_primaria_destino)
```


* **DEFAULT**: Se utiliza para establecer un valor predeterminado para una columna. El valor predeterminado se agregara a todos los registros nuevos, si no se especifica ningun otro valor. Por ejemplo, podemos poner "Usuario897" como valor predeterminado si no se inserta ninguno, o insertar valores del sistema mediante el uso de funciones como GETDATE().

```SQL
--Establecer un valor predeterminado para una columna al crear una tabla

CREATE TABLE Example(
PersonID varchar(60) DEFAULT "Exe"
);

--Establecer un valor predeterminado para una columna en una tabla ya creada

ALTER TABLE Example
ALTER PersonID SET DEFAULT "Exe";

--Eliminar la restriccion DEFAULT para una columna en una tabla ya creada

ALTER TABLE Example
ALTER PersonID DROP DEFAULT;
```

* **CREATE INDEX**: Se utiliza para crear y recuperar datos de la base de datos muy rapidamente. Actualizar una tabla con índices lleva más tiempo que actualizar una tabla sin ellos (porque los índices también necesitan una actualización). Por lo tanto, solo cree índices en las columnas que se buscarán con frecuencia.

```SQL
--Crear un indice en una tabla

CREATE INDEX index_name
ON table_name (column1, column2, ...);

--Crear un indice unico en una tabla

CREATE UNIQUE INDEX index_name
ON table_name (column1, column2, ...);

--Eliminar un indice de una tabla

ALTER TABLE table_name
DROP INDEX index_name;
```

* **CHECK**: Asegura que los valores en una columna satisfagan una condicion especifica. La restricion CHECK se utiliza para limitar el rango de valores que se puede colocar en una columna. Si se define una CHECK restriccion, solo se permitira ciertos valores para esta columna. Si se define una restriccion CHECK en una tabla, puede limitar los valores en ciertas columnas en funcion de los valores en otras columnas de la fila.

```SQL
--Definir una restriccion CHECK en una columna

CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int,
CHECK (Age >= 18)
)

--Nombrar y definir una restriccion CHECK en varias columnas

CREATE TABLE Persons (
ID int NOT NULL, 
LastName varchar(255) NOT NULL,
Age int,
City varchar(255),
CONSTRAINT CHK_Person CHECK (Age >= 18 AND City = 'Sandnes')
);

--Para crear un CHECK cuando la tabla ya esta creada

ALTER TABLE Persons
ADD CHECK (Age >= 18);

-- Para nombrar una CHECK y definirla en varias columnas

ALTER TABLE Persons
ADD CONSTRAINT CHK_PersonAge CHECK (Age >= 18 AND City = 'Sandnes');

--Para eliminar una restriccion CHECK

ALTER TABLE Persons
DROP CHECK CHK_PersonAge;
```