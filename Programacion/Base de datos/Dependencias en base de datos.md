# Dependencias en base de datos

Una dependencia es una propiedad de la semantica de los atributos

* **Dependencia funcionales:** Son **restricciones de integridad** que permiten conocer que relaciones existen entre dos o mas atributos del mundo real. Una dependencia funcional es cuando un atributo define el valor de mas atributos. **Un atributo Y de una relacion depende funcionalmente de otro atributo X de la relacion si a todo valor de X le corresponde siempre el mismo valor de Y**. 
	
	Ejemplo: Tenemos el numero de identificacion (atributo X), este es el **determinante** y las demas columnas **dependientes.** Si cambia el numero de identificacion cambiara el valor de las otras columnas. Las dependientes siempre estan asociada a la misma determinante. El determinante tiene que ser siempre unico e irrepetible. Todos los atributos se determinan a si mismo. Es decir, una clave primaria siempre nos va a dar el mismo conjunto de tuplas

Para decir que un atributo tiene una dependencia funcional utilizamos una flechita hacia la derecha.

Ejemplo: En este caso las dependencias funcionales serian CodProv --> NomProv y CodInsumo -->Precio

![[Pasted image 20231120150851.png]]

* **Dependencias Parciales/transitiva :**  Decimos que tenemos una dependencia parcial, cuando las dependientes no están determinada por la clave primaria completa. Una dependencia transitiva es una dependencia funcional X → Z en la cual Z no es inmediatamente dependiente de X, pero sí de un tercer conjunto de atributos Y, que a su vez depende de X. Es decir, X → Z por virtud de X → Y e Y → Z.

![[Pasted image 20230512200417.png]]
* **Dependencia multivaluada**: Una dependencia multivaluada se refiere a la relación entre conjuntos de atributos en los que un conjunto de atributos determina otro conjunto de atributos y viceversa, pero no hay dependencias funcionales directas entre ellos. Se representa como A ⊳⊳ B, donde A y B son conjuntos de atributos.

	Ejemplo: Sea R un esquema de relacion formado por los atributos A, B, C. La dependencia multivaluada A --> --> B existe si y solo si el conjunto de valores de B que se obtiene para un par de valores (A, C) depende solo del valor de A y es independiente de los valores para C.
