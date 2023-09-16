# Modelo entidad-relacion (M-E-R)

El modelo entidad-relación se utiliza para diseñar la estructura conceptual de la base de datos. El modelo entidad-relación es una técnica de diseño conceptual que se centra en la identificación de entidades (objetos o conceptos del mundo real), sus atributos y las relaciones entre ellas. Proporciona una representación visual de alto nivel de cómo se relacionan las entidades en un dominio de aplicación.
## Entidades

Este modelo representa la realidad a traves de **entidades** que representan cosas u objetos (que contienen informacion) y se distinguen de otros por sus caracteristicas. Las entidades en un futuro seran las tablas de nuestra base de datos.  La entidad se representa con un rectangulo  y con el nombre en mayuscula.

* **Entidad fuerte**: Las entidades fuertes son independientes de otras entidades. Si estas tienen entidades debiles que dependen de ellas se la denomina **entidad matriz**. Estas tienen un **atributo identificador** o **clave primaria** que distinga a cada suceso (registro) de la entidad. Las claves primarias no pueden ser repetibles. El atributo identificador se puede distinguir en el modelo poniendole color o subrayado.
* **Entidad debil**: Las entidades debiles dependen de otra entidad. No tienen claves primarias y no tienen significado en el diagrama sin su entidad matriz. Pueden tener una clave compuesta, es decir, combinamos la clave primaria de la entidad fuerte (Que ahora es una clave foranea, es decir, hara referencia a la clave primaria de la entidad fuerte) con una clave primaria propia que sera autoincrementar, para asi crear la clave compuesta a la entidad debil. Las entidades debiles siempre tendran una relacion de uno a muchos (1, N).
* **Entidad asociativa**: Las entidades asociativas relacionan las instancias de varios tipos de entidades. Tambien contienen atributos que son especificos a la relacion entre esas instancias de entidades.

**Dato**: Las entidades deben estar acompañadas por algun tipo de identificador, y por el otro lado deben estar relacionandose con una entidad.
## Atributos

Toda entidad debe tener **atributos** que son las caracteristicas que definen o identifican a una identidad, los atributos en un futuro seran las columnas en nuestra base de dato. Los atributos son las caracteristicas de una entidad y tienen un valor. Nos permitira describir como estaran estructurada nuestras entidades. Pueden tambien estar en relaciones si es M:M. 
Cada atributo no puede tener un valor cualquiera, los valores posibles conforman un **tipo de dato**. Al definir un atributo, nosotros podemos declarar que tipo de valor tendra.

* **Atributos simples**: Son atributos que simplemente tienen datos unicos, no estan compuestos por nada mas.
* **Atributos clave(key)**: Estos atributos son unicos e irrepetibles, y sirven para distinguir cada registro de la entidad. Hay claves **primarias, foraneas, etc**. Se subraya en el diagrama para aclarar que es un atributo key. 
* **Atributos multivaluados**: Los atributos de multiples valores son aquellos que pueden tomar mas de un valor. Un atributo multivaluado puede ser compuesto.
* **Atributos compuestos**: Son parecidos a los atributos de multiples valores con la diferencia que estos si pueden tener multidominios. Es decir, estan compuestos por mas atributos. Un atributo compuesto puede ser multivaluado, es decir, podemos tener un atributo contacto que tenga multiples atributos por ejemplo email, telefono, y en email tener multiples valores.
* **Atributos derivados**: Los atributos derivados son atributos cuyos valores se pueden calcular a partir de valores de atributos relacionados que se denominan **atributo almacenado**
* **Atributo complejos**: Son aquellos que son atributos multivaluados y a la vez atributos compuestos.

**Dato**: Si el atributo tiene como tipo de dato un booleano se suele poner un signo de interrogacion.

## Relaciones

Ademas tenemos el **conjunto de relaciones** que consiste en una coleccion de las relaciones entre las entidades. Vamos a tener un conjunto que se forma de la instancia de la relacion. 
El grado de un tipo de relacion es el numero de tipos de entidades participantes. Una relacion de grado binarias son las mas comunes. Las relaciones en el MER van en mayuscula

* **Relacion**: Las relaciones son asociaciones entre dos o mas entidades.
* **Relacion debil o identificativa**: Las relaciones debiles son conexiones entre una entidad debil y su entidad matriz.

![[Pasted image 20230821114952.png]]
Los tipos de relaciones normalmente tienen ciertas restricciones que limitan las posibles combinaciones entre las entidades que pueden participar en el conjunto de relaciones correspondientes. Podemos distinguir dos tipos principales de restricciones de relacion: **razon de cardinalidad** y **participacion**.Nos referiremos a la razón de cardinalidad y a las restricciones de participación, en conjunto, como **restricciones estructurales de un tipo de relación**.

Los tipos de relación también pueden tener atributos, llamados **atributos de relacion** parecidos a los de los tipos de entidad. Por ejemplo, para registrar el número de horas por semana que un empleado trabaja en un proyecto en particular, podemos incluir un atributo Horas para el tipo de relación TRABAJA_EN.
Los atributos de los tipos de relación 1: 1 o l:N se pueden trasladar a uno de los tipos de entidad participantes. Por ejemplo, el atributo Fechalnicio para la relación ADMINISTRA puede ser un atributo de EMPLEADO o DEPARTAMENTO, aunque conceptualmente pertenece a ADMINISTRA. Esto se debe a que ADMINISTRA es una relación 1: 1, por lo que cada entidad departamento o empleado participa a lo sumo en una instancia de relación. Por tanto, el valor del atributo Fechalnicio se puede determinar por separado, bien mediante la entidad departamento participante, bien mediante la entidad empleado (director) participante. 
En el caso de un tipo de relación 1 :N, un atributo de relación sólo se puede migrar al tipo de entidad que se encuentra en el lado N de la relación. 
En los tipos de relación 1: 1 y 1 :N, la decisión sobre dónde debe colocarse un atributo de relación (como un atributo de tipo de relación o como un atributo de un tipo de entidad participante) la determina subjetivamente el diseñador del esquema. 
Para los tipos de relación M:N, algunos atributos pueden determinarse mediante la combinación de entidades participantes en una instancia de relación, no mediante una sola relación. Dichos atributos deben especificarse como atributos de relación
### Cardinalidad

La **cardinalidad** de un atributo indica el numero maximo de instancias de relacion en las que una entidad puede participar. Indica cuántos registros de una tabla están asociados con un solo registro de otra tabla a través de una relación específica. El tipo de cardinalidad se representa mediante una etiqueta en el exterior de la relacion, respectivamente : "1:1", "1:N", "N:M".

* **Uno a uno (1 : 1)**: Se da cuando un elemento de una entidad se puede relacionar solamente con un solo registro de otra entidad y viceversa.
* **Uno a muchos(1:N)**: Se da cuando un registro de una entidad A se puede relacion con cero o muchos registros de otra entidad B y cada registro de la entidad B se relaciona con un solo registro de la entidad A.
* **Muchos a Muchos (N:M)**: Se da cuando un registro de una entidad se relaciona con ceros o varios registros de otra entidad y visceversa.
* **Cero a uno(0:1)**: Se da cuando un registro de una entidad puede o no relacionarse con un registro de otra entidad.
* **Cero a muchos(0:N)**: Se da cuando un registro de una entidad puede o no relacionarse con varios registros de otra entidad.


![[Pasted image 20230512210217.png]]
![[Pasted image 20230512210254.png]]

Ejemplo:

![[Pasted image 20230821115638.png]]

**Dato:** Si la cardinalidad entre tablas es mucho a muchos es una tabla pivote.
**Dato**: La cardinalidad se pone en la entidad receptora

### Participacion

La **restricción de participación** especifica si la existencia de una entidad depende de si está relacionada con otra entidad a través de un tipo de relación. Esta restricción especifica el número mínimo de instancias de relación en las que puede participar cada entidad, y en ocasiones recibe el nombre de restricción de cardinalidad mínima. 

Una entidad participa en una relación si está en al menos una de las instancias (de relación). La participación de un tipo de entidad/rol en un tipo de relación puede ser

- Total si todas las entidades del tipo participan (1)
- Parcial si no es necesario que todas participen (0)

En los diagramas ER, la participación total (o dependencia existente) se muestra como una línea doble que conecta el tipo de entidad participante con la relación, mientras que las participaciones parciales se representan mediante una línea sencilla 

**Dato**: (participacion, cardinalidad)
### Relacion recursiva

En algunos casos el mismo tipo de entidad participa mas de una vez en un tipo de relacion con diferentes roles. Dichos tipos de relaciones se denominan relaciones recursivas.


![[Pasted image 20230821120144.png]]



![[Pasted image 20230512195048.png]]
![[Pasted image 20230512212616.png]]

Una vez que se ha realizado el diseño lógico utilizando el modelo entidad-relación, es necesario implementarlo en una base de datos relacional utilizando un lenguaje de consulta como SQL. En esta etapa, se crean las tablas, se definen las columnas y se establecen las relaciones utilizando claves primarias y foráneas.

## Elementos que hay en un modelo ER



![[Pasted image 20230512195929.png]]

**Dato**: Si el nombre tiene dos palabras la podemos separar con guion bajo.
## Dependencias

Una dependencia es una propiedad de la semantica de los atributos

* **Dependencia funcionales:** Una dependencia funcional es cuando un atributo define el valor de mas atributos. **Un atributo Y de una relacion depende funcionalmente de otro atributo X de la relacion si a todo valor de X le corresponde siempre el mismo valor de Y**. 
	
	Ejemplo: Tenemos el numero de identificacion (atributo X), este es el **determinante** y las demas columnas **dependientes.** Si cambia el numero de identificacion cambiara el valor de las otras columnas. Las dependientes siempre estan asociada a la misma determinante. El determinante tiene que ser siempre unico e irrepetible. Todos los atributos se determinan a si mismo.

* **Dependencias Parciales/transitiva :**  Decimos que tenemos una dependencia parcial, cuando las dependientes no están determinada por la clave primaria completa. Una dependencia transitiva es una dependencia funcional X → Z en la cual Z no es inmediatamente dependiente de X, pero sí de un tercer conjunto de atributos Y, que a su vez depende de X. Es decir, X → Z por virtud de X → Y e Y → Z.

![[Pasted image 20230512200417.png]]


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
