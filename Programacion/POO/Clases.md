# Clases

Una **clase** es una plantilla para la creacion de objetos. Las clases se utilizan para representar entidades, como los sustantivos en el lenguaje normal. Cada clase tiene definida variables(propiedades) y metodos. 

El objeto creado a partir de una clase es llamado una **instancia** de la clase.

## Clases abstractas

En el contexto de la POO, también se utiliza el concepto de clases abstractas, que son aquellas sobre las que no se pueden instanciar objetos. Las clases abstractas pueden contener métodos abstractos, que son métodos declarados en la clase padre pero no implementados, lo que permite a las clases hijas definir su propia implementación. Esto facilita el polimorfismo, es decir, la capacidad de tratar a objetos de diferentes clases como si fueran objetos de una clase común. Una clase abstracta es aquella que tiene al menos un metodo abstracto, y tambien puede tener metodos con implementaciones parciales o completas. Un metodo abstracto es un metodo vacio, por ende no puede realizar ninguna accion, la utilidad de esto es definir que se debe hacer pero no el como hay que hacerlo. Pueden tener variables de instancia o constante.

En lenguajes como Java, una clase puede heredar de una unica clase abstracta, pero puede implementar multiples interfaces. Esto permite lograr la herencia multiple en lenguajes que no la admiten directamente.

Las clases abstractas pueden tener constructores, mientras que las interfaces no pueden tenerlos. Los constructores en las clases abstractas son utilizados por las subclases para inicializar las variables de instancia heredadas

En resumen, las clases abstractas son más adecuadas cuando se desea proporcionar una base común para varias clases relacionadas, que comparten algunas implementaciones y estructuras. Por otro lado, las interfaces son ideales cuando se desea definir un contrato común para varias clases, pero no se necesita proporcionar ninguna implementación específica.