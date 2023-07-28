# Modelo entidad-relacion (E-R)

El modelo entidad-relación se utiliza para diseñar la estructura lógica de la base de datos. El modelo entidad-relación es una técnica de diseño conceptual que se centra en la identificación de entidades (objetos o conceptos del mundo real), sus atributos y las relaciones entre ellas. Proporciona una representación visual de alto nivel de cómo se relacionan las entidades en un dominio de aplicación.


Este modelo representa la realidad a traves de **entidades** que representan cosas u objetos (que contienen informacion) y se distinguen de otros por sus caracteristicas. Las entidades en un futuro seran las tablas de nuestra base de datos.

Toda entidad debe tener **atributos** que son las caracteristicas que definen o identifican a una identidad, los atributos en un futuro seran las columnas en nuestra base de dato. Los atributos son las caracteristicas de una entidad. Nos permitira describir como estaran estructurada nuestras entidades. Pueden tambien estar en relaciones si es M:M.

Ademas tenemos el **conjunto de relaciones** que consiste en una coleccion de las relaciones entre las entidades.

![[Pasted image 20230512195048.png]]
![[Pasted image 20230512212616.png]]

Una vez que se ha realizado el diseño lógico utilizando el modelo entidad-relación, es necesario implementarlo en una base de datos relacional utilizando un lenguaje de consulta como SQL. En esta etapa, se crean las tablas, se definen las columnas y se establecen las relaciones utilizando claves primarias y foráneas.

## Elementos que hay en un modelo ER

* **Entidad fuerte**: Las entidades fuertes son independientes de otras entidades. Si estas tienen entidades debiles que dependen de ellas se la denomina **entidad matriz**. Estas tienen un **atributo identificador** o **clave primaria** que distinga a cada suceso (registro) de la entidad. Las claves primarias no pueden ser repetibles. El atributo identificador se puede distinguir en el modelo poniendole color o subrayado.
* **Entidad debil**: Las entidades debiles dependen de otra entidad. No tienen claves primarias y no tienen significado en el diagrama sin su entidad matriz. Pueden tener una clave compuesta, es decir, combinamos la clave primaria de la entidad fuerte (Que ahora es una clave foranea, es decir, hara referencia a la clave primaria de la entidad fuerte) con una clave primaria propia que sera autoincrementar, para asi crear la clave compuesta a la entidad debil. Las entidades debiles siempre tendran una relacion de uno a muchos (1, M).
* **Entidad asociativa**: Las entidades asociativas relacionan las instancias de varios tipos de entidades. Tambien contienen atributos que son especificos a la relacion entre esas instancias de entidades.
* **Atributos simples**: Son atributos que simplemente tienen datos unicos, no estan compuestos por nada mas.
* **Atributos clave(key)**: Estos atributos son unicos e irrepetibles, y sirven para distinguir cada registro de la entidad. Hay claves **primarias, foraneas, etc**. Se subraya en el diagrama para aclarar que es un atributo key.
* **Atributos multivaluados**: Los atributos de multiples valores son aquellos que pueden tomar mas de un valor.
* **Atributos compuestos**: Son parecidos a los atributos de multiples valores con la diferencia que estos si pueden tener multidominios. Estan compuestos por mas atributos.
* **Atributos derivados**: Los atributos derivados son atributos cuyos valores se pueden calcular a partir de valores de atributos relacionados.
* **Relacion**: Las relaciones son asociaciones entre dos o mas entidades.
* **Relacion debil**: Las relaciones debiles son conexiones entre una entidad debil y su entidad matriz.

![[Pasted image 20230512195929.png]]

## Dependencias

Una dependencia es una propiedad de la semantica de los atributos

* **Dependencia funcionales:** Una dependencia funcional es cuando un atributo define el valor de mas atributos. **Un atributo Y de una relacion depende funcionalmente de otro atributo X de la relacion si a todo valor de X le corresponde siempre el mismo valor de Y**. 
	
	Ejemplo: Tenemos el numero de identificacion (atributo X), este es el **determinante** y las demas columnas **dependientes.** Si cambia el numero de identificacion cambiara el valor de las otras columnas. Las dependientes siempre estan asociada a la misma determinante. El determinante tiene que ser siempre unico e irrepetible. Todos los atributos se determinan a si mismo.

* **Dependencias Parciales/transitiva :**  Decimos que tenemos una dependencia parcial, cuando las dependientes no están determinada por la clave primaria completa. Una dependencia transitiva es una dependencia funcional X → Z en la cual Z no es inmediatamente dependiente de X, pero sí de un tercer conjunto de atributos Y, que a su vez depende de X. Es decir, X → Z por virtud de X → Y e Y → Z.

![[Pasted image 20230512200417.png]]

## Cardinalidad

La **cardinalidad** de un atributo indica el numero maximo de veces que una instancia se relaciona con otra. El tipo de cardinalidad se representa mediante una etiqueta en el exterior de la relacion, respectivamente : "1:1", "1:N", "N:M".

* **Uno a uno (1 : 1)**: Se da cuando un elemento de una entidad se puede relacionar solamente con un solo registro de otra entidad y viceversa.
* **Uno a muchos(1:N)**: Se da cuando un registro de una entidad A se puede relacion con cero o muchos registros de otra entidad B y cada registro de la entidad B se relaciona con un solo registro de la entidad A.
* **Muchos a Muchos (N:M)**: Se da cuando un registro de una entidad se relaciona con ceros o varios registros de otra entidad.

![[Pasted image 20230512210217.png]]
![[Pasted image 20230512210254.png]]

Ejemplo:

![[Pasted image 20230512210316.png]]
**Dato:** Si la cardinalidad entre tablas es mucho a muchos es una tabla pivote.

## Como hacer un diagrama entidad-relacion

Es increíblemente importante organizar el diagrama ER de una forma lógica para aumentar la comprensión. 

Los diagramas de entidad relacion son faciles de comprender y no requieren recibir capacitacion para poder trabajar con ellos de manera eficiente y precisa.
Los DER ademas son facilmente traducibles en tablas relacionales que pueden utilizarse para construir rapidamente bases de datos. Ademas, los DER pueden ser utilizados como el plano para implementar los datos en aplicaciones de software especificas.

### Identificar los componentes

**1.** **Determina las entidades**: Las entidades generalmente son sustantivos.

![[Pasted image 20230512211722.png]]

**2.** **Identifica las relaciones**: Las relaciones resaltan como las entidades interactuan entre si. Son generalmente verbos. 

![[Pasted image 20230512211836.png]]

**3. Agrega atributos:** Los atributos muestra caracteristicas especificas de la entidad, detallando que informacion es importante para el modelo.

![[Pasted image 20230512212046.png]]

**4. Cardinalidad de las relaciones**:

![[Pasted image 20230512212125.png]]

### DER a las especificaciones

![[Pasted image 20230512212208.png]]
- Las entidades son Cliente y Cuenta.
- Las relacion es que los clientes tienen cuenta.
- Los atributos de cliente son : id, nombre, calle, ciudad.
- Los atributos de cuenta son: Numero de cuenta y saldo.

![[Pasted image 20230512212249.png]]

Otro ejemplo:

![[Pasted image 20230512212331.png]]
