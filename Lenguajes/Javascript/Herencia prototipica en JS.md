# Herencia prototipica en JS

El **prototipo** es el primer ejemplar que se fabrica que sirve de modelo para fabricar otras iguales.

La mayoria de los objetos tienen una propiedad oculta especial llamada **prototype** que puede ser null o hacer referencia a otro objeto llamado prototype. 

Un prototipo es otro objeto que se utiliza como reserva de propiedades alternativa. Cuando un objeto recibe una solicitud por una propiedad si esta la tiene lo devuelve, en caso de no tenerla, se buscara en su prototipo la propiedad, luego en el prototipo del prototipo y asi sucesivamente hasta devolverla o si el prototipo no la tiene mostrar undefined. Es decir la propiedades propia tiene mayor prioridad que las propiedades heredadas ( esto se llama propiedad shadowing).

Los prototipos son útiles para definir propiedades en las cuales todas las instancias de una clase compartan el mismo valor, como métodos.

Cuando introducimos cambios al prototipo, los objetos siguientes en la cadena heredan estos cambios. Debido a la cadena de prototipos, este nuevo metodo es accesible tambien desde las otras instancias.

El prototipo raiz es **Object.prototype**.

Una forma de configurar la propiedad Prototype es utilizando el nombre especial **__proto__**.

```javascript
//Ejemplo 1

let animal = {
	comer : true,
};

let conejo = {
	saltar: true,
}

conejo.__proto__ = animal;

console.log(conejo.comer); //true
console.log(conejo.saltar); //true

let pajaro = {
	volar : true,
}

console.log(pajaro.comer); //undefined
console.log(pajaro.saltar); //undefined
console.log(pajaro.volar); //true
```

Otra forma de configurar la propiedad Prototype es utilizando la sintaxis **constructor.prototype.propiedadometodo.** Las propiedades creadas al prototipo no se crearan en la funcion constructora, si no en las instancias creadas a partir de la funcion constructora.

```javascript
//Agregando propiedad al prototipo

function Carrito(nombre, precio, modelo){
    this.nombre = nombre;
    this.precio = precio;
    this.modelo = modelo;
    this.mostraretiqueta = function(){
        console.log(`${this.nombre} cuesta $${this.precio} del modelo ${this.modelo}`);
    }
};



let producto = new Carrito("Celular", 500, "j600");

//Ejemplo 1

Carrito.prototype.año = 2020;
console.log(producto.año); //2020
producto.año = 2022;
console.log(producto.año); //2022

//Ejemplo 2

Carrito.prototype.año = 2020;
console.log(producto.año); //2022

//Si uno el ejemplo 1 y 2 y lo continuo

let producto1 = new Carrito("Celular", 500, "j600");
console.log(producto1.año); //2020 ya que cambie la propiedad del prototipo pero no de la instancia creada antes que se cambie dicha propiedad
console.log(producto.año); //2022 

//Agregando metodo al prototipo

function Carrito(nombre, precio, modelo){
    this.nombre = nombre;
    this.precio = precio;
    this.modelo = modelo;
    this.mostraretiqueta = function(){
        console.log(`${this.nombre} cuesta $${this.precio} del modelo ${this.modelo}`);
    }
};

Carrito.prototype.precioymodelo = function (){
    return `El producto se llama ${this.nombre} ${this.modelo}`;
}
```

**Dato**: Para obtener el prototipo de un objeto podemos utilizar **Object.getPrototypeOf(objeto)**.

**Dato**: Podemos utilizar **Object.create(prototipo)** para elegir el prototipo del objeto que deseas crear, sin tener que definir una funcion constructora.

**Dato**: La propiedad prototype tiene como valor un objeto que contiene una propiedad constructor. Esta propiedad constructor apunta a la funcion constructor original. Por lo que nosotros podremos crear una instancia nueva a partir de esta propiedad si por alguna razon no se tiene disponible facilmente una referencia al constructor original.

**Dato**:  Un patrón bastante común para la mayoría de definiciones de objetos es declarar las propiedades dentro del constructor, y los métodos en el prototipo. Esto hace el código más fácil de leer, ya que el constructor sólo contiene las definiciones de propiedades, y los métodos están en bloques separados