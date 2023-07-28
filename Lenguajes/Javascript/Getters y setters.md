# Getters y setters

Hay dos tipos de propiedades de objeto:

* Una de ellas es con las que venimos estado usando hasta ahora, que eran **propiedades de datos**. Estas contienen un valor y se acceden directamente a traves del objeto.

* El segundo tipo de propiedades son las propiedades de **acceso o accesors.** Son funciones que se ejecutan para **obtener (get) y asignar (set)** un valor de una propiedad, pero que para un codigo externo se ven como propiedades normales. Get es solo se lectura y set para asignar un valor. Sirven para tomar el control sobre una propiedad privada.

Las propiedades que comienzan con un **guion bajo son internas** y **no deben ser manipuladas desde el exterior del objeto**. Esto es una convencion, pero siguen pudiendo ser accedidas y modificadas desde fuera de la clase. Para realizar **propiedades** verdaderamente **privadas** podemos utilizar **\#nombrePropiedad**. Los metodos tambien pueden ser privados.

Las propiedades de acceso se construyen con métodos de obtención “getter” y asignación “setter”. En un objeto literal se denotan con **get** y **set**. Ejemplo:

![[Pasted image 20230109125222.png]]

El getter funciona cuando se lee obj.propName, y el setter cuando se asigna.

**Ejemplo:** Tenemos un objeto “usuario” con nombre y apellido:

![[Pasted image 20230109125502.png]]
Ahora queremos añadir una propiedad de “Nombre completo”:

![[Pasted image 20230109125520.png]]
Si agregamos un setter

![[Pasted image 20230109125625.png]]
Como resultado, tenemos una propiedad virtual fullName que puede leerse y escribirse.

## Descriptores de las propiedades de acceso

Los descriptores de propiedades de acceso son diferentes a aquellos para las propiedades de datos. Para las propiedades de acceso, no hay cosas como valor y escritura, sino de get y set.

Así que un descriptor de accesos puede tener:

-get : una función sin argumentos, que funciona cuando se lee una propiedad,

-set : una función con un argumento, que se llama cuando se establece la propiedad,

-enumerable : lo mismo que para las propiedades de datos.

-configurable : lo mismo que para las propiedades de datos.

Ejemplo:

![[Pasted image 20230110123820.png]]

 Una propiedad puede ser un acceso (tiene métodos `get/set`) o una propiedad de datos (tiene un `value`), no ambas. Si intentamos poner ambos, `get` y `value`, en el mismo descriptor, habrá un error.
## Getters y setters más inteligentes

Getters y setters pueden ser usados como envoltorios sobre valores de propiedad “reales” para obtener más control sobre ellos.

Ejemplo:

![[Pasted image 20230110123838.png]]
## Getters y setters en constructores

![[Pasted image 20230110124546.png]]

**Dato:** El nombre de los getters/setters no pueden ser el mismo que la propiedad porque se produciria un bucle: al acceder a la propiedad invocariamos al metodo que a su vez accede a la propiedad que invoca al metodo. Por ello se utiliza el guion bajo para nombrar la propiedad.

## ¿ what is its use?

Se utilizan para tener control sobre propiedades privadas de un objeto. Pudiendo acceder y asignar un valor a dichas propiedades.

Además de proporcionar una capa adicional de seguridad y control en la manipulación de objetos, los getters y setters también pueden utilizarse para realizar acciones adicionales, como validación de datos o realización de cálculos adicionales en función de los valores de las propiedades del objeto.