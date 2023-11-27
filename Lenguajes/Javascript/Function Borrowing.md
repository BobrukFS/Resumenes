# Function Borrowing

El prestamo de funciones nos permite utilizar los metodos de un objeto en un objeto diferente sin tener que hacer una copia de ese metodo y mantenerlo en dos lugares separados. Se logra mediante el uso de **.call()**, **apply()** y **.bind()**, todos los cuales existen para establecer esto explicitamente en el metodo que estamos tomando prestado.

```js
class Dog {
	constructor(nombre, raza){
		this.nombre = nombre;
		this.raza = raza; 
	}

	info(){
		return `El nombre es ${this.nombre} y su edad es ${this.raza}`;
	}
}

let fido = new Dog("Fido", "Holandesa")

class Cat {
	constructor(nombre, raza){
		this.nombre = nombre;
		this.raza = raza;
	}
}

let sparkles = new Cat("Sparkles", "Argentina");
sparkles.info();//TypeError: sparkles.info is not a function

//Para lograr utilizar el metodo info de la clase Dog y evitar heredar utilizamos .call() o .apply()

fido.info.call(sparkles);



```

Tanto .call() y .apply() sirven para tomar prestado un metodo de otro objeto y se ejecuta inmediatamente. Por lo contrario, .bind()  guarda la funcion prestada para mas adelante

```js
//Utilizando .bind() para guardar la funcion prestada

const infoSparkles = fido.info.bind(sparkles);
infoSparkles();
```

El beneficio central del préstamo de funciones es que le permite renunciar a la herencia. No hay ninguna razón para que fuerces que una clase herede de otra si solo lo haces para otorgar acceso a las instancias de la clase secundaria a un único método.
La aplicación práctica más importante del préstamo de funciones se refiere a los métodos nativos y, específicamente, a `Array.prototype.slice`. Hay varias estructuras de datos similares a listas que no son matrices, y es útil poder tratarlas como matrices y operar con ellas como tales