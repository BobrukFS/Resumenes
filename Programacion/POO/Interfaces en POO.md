# Interfaces en POO

La **interfaz** es un medio comun para que los objetos no relacionados se comuniquen entre si. Una interfaz se utiliza para definir un contrato que debe ser cumplido por un objeto o una clase que lo implemente. Es decir, que nuestra interfaz tiene metodos y propiedades, que deben tener obligatoriamente los objetos u clases que lo implementen, en caso contrario, arrojara un error en tiempo de compilacion o en tiempo de ejecucion dependiendo de como se este utilizando el objeto u clase.

En Javascript a diferencia de otros lenguajes, no tiene interfaces. Sin embargo, TypeScript da soporte para interfaces.

Podemos definir a una interfaz como una coleccion de metodos abstractos y propiedades constantes en las que se especifica que se debe hacer pero no el como, es decir, solo tiene metodos abstractos y variables constantes. Seran las clases hijas las que definan el comportamiento. A diferencia de una clase abstracta, una interfaz no puede hacer nada por si sola. Las clases hijas, que implementan la interfaz, deben obligatoriamente definir el comportamiento de todos los metodos abstractos.

La principal diferencia entre interface y abstract es que una interface no fuerza a utilizar la herencia.

![[Pasted image 20231015183736.png]]