# Tipos personalizados en gobstones

## Registros

Los **registros** son un tipo de datos con estructura que cuentan con dos o mas partes.  Este tipo de datos los definimos indicando los valores de sus **campos(fields)**.

Se utiliza la palabra clave **type** para un **tipo nuevo** (cuyo nombre comienza con mayusculas). **is record** para aclarar que es un registro.  Para declarar los campos utilizamos la palabra clave **field** para cada campo (cuyo nombre va con minusculas).

![[Pasted image 20231019204409.png]]

Al definir un tipo registro, se debe dejar claro cual es el tipo de datos que modela, para esto debemos escribir el proposito del tipo que forma parte del contrato de la definicion.

![[Pasted image 20231019204510.png]]
Un field de un registro puede tomar valores de cualquier tipo de datos.

![[Pasted image 20231019204618.png]]
Para construir valores del tipo **se usa el nombre del tipo como constructor** seguido de parentesis, y se da valor a cada field escribiendo el nombre, seguido del simbolo **<-** y el valor.

![[Pasted image 20231019204708.png]]
Los valores de los fields deben cumplir ciertas condiciones. Las condiciones necesarias se dan en la definicion, a estas condiciones las llamamos **invariante de representacion** y seria como la precondicion de los datos. Si se arma un dato que no cumple el invariante de representacion, se considera **invalido**. Sin embargo, el lenguaje lo aceptara, pero es invalido.

![[Pasted image 20231019204847.png]]

Los registros se pueden pasar como argumento de operaciones, recordar en variables y devolver como resultado de funciones debido a que son datos.

Cada campo tiene asociada una funcion de acceso llamada **observador de campo o funcion observadora**. El **nombre de la funcion es el mismo nombre del field, su argumento es un valor del tipo registro correspondiente** y lo que hace es **describir el valor del campo dado**.

Ejemplo: Escribir una función lasCartas_y_SonDelMismoPalo, que dadas 2 cartas, indique si ambas son del mismo palo

![[Pasted image 20231019205258.png]]
## Variantes 

En un **tipo de datos con estructuras que esta dada por casos**. Cada case tiene un nombre y define un valor diferente del mismo tipo. 

Para definir este tipo de dato utilizamos la palabra clave **type** seguida del nombre del tipo de dato, seguido de la palabra clave **is variant** para indicar que es una variante. Un tipo de dato variante tiene casos que se declaran con la palabra clave **case**.

![[Pasted image 20231019213508.png]]

Cada valor de un tipo variante se define con uno de los constructores de casos. Cada caso define un constructor. Los constructores enumeran los valores posibles. Por eso se conocen tambien como **tipo enumerativos**.

Los valores de un tipo enumerativo se pueden usar como cualquier otro valor

![[Pasted image 20231019205655.png]]
Para decidir que devolver segun su que valor es se puede utilizar choose con igualdades.

![[Pasted image 20231019205732.png]]
Ejemplo:  Definir una función siguientePalo_ que tome un palo y describa al palo siguiente al dado en el orden alfabético (circularmente, como en los colores)

![[Pasted image 20231019210019.png]]Se puede construir un registro basandose en otro registro dado, se puede hacer campo a campo, o se puede usar una notacion especial utilizando **|**.

![[Pasted image 20231019210439.png]]
![[Pasted image 20231019210516.png]]
![[Pasted image 20231019210538.png]]

Ejemplo: Escribir una función la_SinLasRojas que dada una Celda (como registro de tipo Celda), describa la Celda resultante al sacar todas las bolitas rojas de la dada

![[Pasted image 20231019215457.png]]

Otro ejemplo: Escribir una función la_Con10AzulesMás que dada una Celda (como registro de tipo Celda), describa la Celda resultante de agregar 10 bolitas azules a la dada

![[Pasted image 20231019215521.png]]

Se puede usar un registro como valor del campo de otro.

![[Pasted image 20231019215603.png]]
![[Pasted image 20231019215610.png]]
![[Pasted image 20231019215653.png]]
![[Pasted image 20231019215706.png]]

**Dato**: El **String** nos permite representar cualquier cadena de caracteres.