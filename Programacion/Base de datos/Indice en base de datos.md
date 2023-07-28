# Indice en base de datos

El **indice** de una tabla desempeña la misma funcion que el indice de un libro, permite localizar datos rapidamente.

Una tabla se indexa por uno o varios campos, y posibilita el acceso directo y rapido haciendo mas eficiente las busquedas. Sin indice, se debe recorrer secuencialmente toda la tabla para encontrar un registro consumiento mas tiempo y recurso. La desventaja de un indice es que consume espacio en el disco ya que requiere realizar una tarea de indexacion. Es una tecnica que optimiza el acceso a los datos, mejora el rendimiento acelerando las consultas y otras operaciones. Es util cuando la tabla contiene miles de registros.

Hay distintos tipos de indices:

* **Index:** Puede haber varios por tabla. Es un indice comun. Los valores no necesariamente son unicos y aceptan valores nulos, Podemos darle un nombre, si no se lo damos, se coloca uno por defecto “key”.

* **Unique :** Es un indice para los cuales los valores deben ser unicos y diferentes, aparece un mensaje de error si intentamos agregar un registro con un valor ya existente. Permite valores nulos y pueden definirse varios por tabla.

* **Clave Primaria (PK) :** Una clave primaria es la columna o colección de columna que nos permite identificar de forma unica a una fila (registro) determinada en una tabla. Existen 3 tipos de claves primarias:

	**1.** **Clave natural** es una clave primaria compuesta de una columna que identifica de forma única a una entidad, por ejemplo el DNI de una persona o la patente de un auto.

	**2. Clave artificial** es una columna creada para una entidad con el propósito de servir únicamente como clave primaria y es visible para los usuarios.

	**3. Clave subrogada** es una clave primaria generada por el sistema, usualmente un tipo de datos generado automáticamente que suele estar escondido del usuario. Normalmente se define con el nombre de “id” y se define como un valor autoincremental. Esto hace que, al insertar un nuevo registro, este valor aumente.

* **Clave Foranea (FK):** Es una columna o un conjunto de columnas en una tabla cuyos valores corresponden a los valores de la clave primaria de otra tabla. Para poder añadir una fila con un valor de clave foranea especifico, debe existir una fila en la tabla relacionada con el mismo valor de clave primaria.

* **Clave candidata :** Las claves candidatas son columnas o conjuntos de columnas en una tabla que podrían ser utilizadas como clave primaria. Se les llama "candidatas" porque tienen el potencial de ser elegidas como clave primaria, pero aún no han sido seleccionadas como tal. En otras palabras, son claves potenciales que aún no se han asignado a la función de clave primaria. Las claves candidatas tienen las mismas propiedades que las claves primarias, como la unicidad y la no nulidad. Sin embargo, a diferencia de las claves primarias, puede haber varias claves candidatas en una tabla. La elección de una clave primaria entre las claves candidatas se basa en factores como la simplicidad, la estabilidad y la accesibilidad de la clave.