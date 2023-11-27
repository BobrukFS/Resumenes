# Polimosfirmos

El **polimorfismo** es la posibilidad de que una clase presente un comportamiento distinto de acuerdo a una situacion-

## Tipos de polimorfismos

### Ad-hoc

#### Por sobrecarga

En el polimorfismo por sobrecarga, dos o mas metodos tienen el mismo nombre pero diferentes parametros, lo que permite llamar a un metodo u otro con diferentes argumentos en funcion de su tipo. 

Nos permite definir varios metodos con el mismo nombre pero con diferentes parametros y tipos de retorno.

```js

//Ejemplo, en JS no hay polimorfismo por sobrecarga

class Robot {
    constructor(tipo){
        this.tipo = tipo;
    }

    saludar(string) {
        console.log(`Hola ${string}`)

    }

    saludar(){
        console.log("Hola humano");
    }
}

let r2d2 = new Robot("azul");
console.log(r2d2);

  
r2d2.saludar(); //Hola humano.
r2d2.saludar("juan"); //Hola Juan.
```

Sin la existencia de este mecanismo, se debería crear una operación distinta por cada “versión” de nuestra operación. Sin la sobrecarga de operaciones, las operaciones están limitadas a los parámetros de una sola definición de operación.
#### Por coercion

El polimorfismo por coercion es una tecnica que permite que los valores de diferentes tipos sean utilizados de forma intercambiable. La coerción es un proceso en el cual un valor de un tipo de dato se convierte automáticamente en otro tipo de dato compatible sin necesidad de realizar una conversión explícita. Esto permite que un mismo método o función pueda ser utilizado con diferentes tipos de datos sin necesidad de sobrecargarlo con múltiples versiones para cada tipo de dato específico.

Por ejemplo, en JS, el operador de suma (+) tiene una funcionalidad polimorfica por coercion, lo que significa que puede operar con diferentes tipos de datos y producir diferentes resultados dependiendo de los tipos de datos que recibe.

### Universal

#### Parametrico

El polimorfismo paramétrico es una técnica de lenguaje de programación que permite la definición genérica de funciones y tipos, sin una gran preocupación por los errores basados en tipos. Esta técnica permite que el lenguaje sea más expresivo al escribir código genérico que se aplica a varios tipos de datos. Las funciones escritas en contexto con polimorfismo paramétrico funcionan en varios tipos de datos. El polimorfismo paramétrico es la capacidad para definir varias funciones utilizando el mismo nombre, pero usando parámetros diferentes (nombre y/o tipo). El polimorfismo paramétrico selecciona automáticamente el método correcto a aplicar en función del tipo de datos pasados en el parámetro.

En resumen, el polimorfismo paramétrico es una técnica que permite a los programadores escribir funciones y tipos genéricos que funcionan en varios tipos de datos, facilitando la reutilización de código y la adaptabilidad a diferentes situaciones.

JavaScript no tiene soporte nativo para polimorfismo paramétrico en el sentido tradicional que se encuentra en lenguajes de programación con tipos estáticos y fuertes, como Java o C#. Sin embargo, debido a la naturaleza dinámica y débilmente tipada de JavaScript, es posible lograr un comportamiento similar al polimorfismo paramétrico utilizando funciones genéricas que aceptan argumentos sin importar su tipo.

#### Por herencia o polimorfismo por redefinicion de metodo

El polimorfismo por herencia es una propiedad de la programación orientada a objetos que permite que un método invocado varíe en función de la clase de la instancia de un objeto. En otras palabras, diferentes clases pueden tener un método con el mismo nombre, pero con distintas implementaciones, es decir, con distintos comportamientos segun la clase de la instancia del objeto. Si la clase hija no redefiniera ese comportamiento, el comportamiento sería el mismo de la clase padre (tras invocar a dicho método).

```js
class Shape {
  constructor() {
    if (this.constructor === Shape) {
      throw new Error("Shape es una clase abstracta y no puede ser instanciada");
    }
  }

  calculatePerimeter() {
    throw new Error("Método calculatePerimeter() debe ser implementado en clases derivadas");
  }

  calculateArea() {
    throw new Error("Método calculateArea() debe ser implementado en clases derivadas");
  }
}

class Circle extends Shape {
  constructor(radius) {
    super();
    this.radius = radius;
  }

  calculatePerimeter() {
    return 2 * Math.PI * this.radius;
  }

  calculateArea() {
    return Math.PI * this.radius * this.radius;
  }
}

class Rectangle extends Shape {
  constructor(height, width) {
    super();
    this.height = height;
    this.width = width;
  }

  calculatePerimeter() {
    return 2 * (this.height + this.width);
  }

  calculateArea() {
    return this.height * this.width;
  }
}
```