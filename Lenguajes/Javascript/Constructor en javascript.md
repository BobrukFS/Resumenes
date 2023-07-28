# [[Constructor]] en javascript

```javascript
let constructor = function() {
	let objeto = {
		nombre : "Exe",
		edad : 22,
		mostrarNombre(){
			console.log(`Mi nombre es ${this.nombre}`);	
		}
	};
	return objeto;
}

let objetoNuevo = constructor();
objetoNuevo.mostrarNombre(); //Exe
```

Usando constructores podemos crear nuevos objetos de forma dinamica.

```javascript
let constructor = function(nombre, edad) {
	let objeto = {
		nombre : nombre,
		edad : edad,
		mostrarNombre : function(){
			console.log(`Mi nombre es ${this.nombre}`);	
		}
	};
	return objeto;
}

let objetoNuevo = constructor("Sofia", 19);
objetoNuevo.mostrarNombre(); //Sofia
```

**Dato**: Aunque los objetos creados desde un constructor comparten las mismas propiedades y metodos, se almacenan en diferentes espacios de memoria, por lo que son diferentes objetos.

## Operador New

Tambien podemos crear nuevos objetos a traves de una **funcion constructora** y el operador **new**. Este tipo de constructores **requiere que las propiedades y los metodos de los objetos sean identificados mediante la palabra clave this**.

```javascript
//Ejemplo 1

function Objeto(){
	this.nombre = "Exe",
	this.edad = 22,
	this.mostrarNombre = function(){
		console.log(`Mi nombre es ${this.nombre}`);	
	}
};

let objetoNuevo = new Objeto();
objetoNuevo.mostrarNombre(); //Exe

//Ejemplo 2

function Objeto(nombre, edad){
	this.nombre = nombre,
	this.edad = edad,
	this.mostrarNombre = function(){
		console.log(`Mi nombre es ${this.nombre}`);	
	}
};

let objetoNuevo = new Objeto("Sofia", 19);
objetoNuevo.mostrarNombre(); //Sofia
```

[[Herencia prototipica en JS]]