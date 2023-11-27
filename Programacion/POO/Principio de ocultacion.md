# Principio de ocultacion

Cada objeto está aislado del exterior, es un módulo natural, y cada tipo de objeto expone una interfaz a otros objetos que especifica cómo pueden interactuar con los objetos de la clase. El aislamiento protege a las propiedades de un objeto contra su modificación por quien no tenga derecho a acceder a ellas, solamente los propios métodos internos del objeto pueden acceder a su estado. Esto asegura que otros objetos no pueden cambiar el estado interno de un objeto de maneras inesperadas, eliminando efectos secundarios e interacciones inesperadas. Algunos lenguajes relajan esto, permitiendo un acceso directo a los datos internos del objeto de una manera controlada y limitando el grado de abstracción.

El objetivo del encapsulamiento es ocultar los valores o el estado de un objeto de datos estructurados dentro de una clase, evitando el acceso directo a ellos por parte de los clientes de una manera que podría exponer detalles de implementación ocultos o violar la invariancia de estado mantenida por los métodos .

El encapsulamiento se logra mediante el uso de modificadores de acceso, como `private`, `public`, y `protected`, que limitan el acceso a las propiedades y métodos de una clase. Si un elemento (me refiero a propiedades y metodos) de una clase es public, tendremos acceso a el desde cualquier clase o instancia del proyecto sin importar la procedencia de este. Si un elemento de una clase es protected, tendremos a acceso desde la misma clase, ademas podemos acceder de clases del mismo paquete y de clases que heredes de ella. Si un elemento de una clase es private solo puede ser accedido por la misma clase.

Si es privado solo puede modificarse por los metodos que tenga la clase.

Un ejemplo común de encapsulamiento son los **getters y setters** de las propiedades dentro de una clase. Estos métodos permiten controlar el acceso y la modificación de las propiedades privadas de un objeto, proporcionando un acceso restringido a los elementos que necesita un miembro y no a ninguno más.

En resumen, el encapsulamiento es una forma de ocultación de información entre entidades, mostrándose entre ellas solo la información más necesaria. Esto permite mantener la integridad de los datos y facilita la modularización del código, ya que los detalles de implementación de una clase están ocultos y protegidos de cambios externo