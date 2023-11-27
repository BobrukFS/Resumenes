# [[Objetos]] literales en Javascript

Un **objeto** es util para almacenar datos de forma estructurada y pueden representar objetos del mundo real.

## Declarando objetos

Los objetos se suelen declarar utilizando la palabra clave **const** seguida del **nombre del objeto**, seguida de **llaves** donde dentro de esas llaves se declararan las **propiedades y metodos**. 

Cuando una variable de objeto es copiada, se copia solo la referencia a la direccion en memoria, el objeto no es duplicado.

```javascript
const miobjeto = {
	nombre : "Exe",
	edad : 22,
	mostrarDatos : function(){
		console.log(`Mi nombre es ${miobjeto.nombre} y mi edad ${miobjeto.edad}`);
	}
};

//Otro ejemplo

const createPersona = function (nombre, edad) {
    return {
        nombre: nombre,
        edad: edad,
    };
};

console.log(createPersona("Exe", 23));
//Azucar sintactico

const createPersona = function (nombre, edad) {
    return {
        nombre,
        edad,
    };
};


```

**Dato:** Un efecto secundario importante de almacenar objetos como referencias es que un objeto declarado con const puede ser modificado.

### Propiedades

Las **propiedades** se declaran utilizando el nombre de la propiedad(**key**) seguida de dos puntos y el valor de dicha propiedad, para separar las propiedades utilizamos la coma. A diferencia de las variables, no podemos acceder a los valores de las propiedades de un objeto usando solo sus nombres. 

**Dato:** En un objeto las propiedades no siempre estan ordenadas

Para poder **acceder/leer** a los valores de las propiedades de un objeto tenemos que utilizar el nombre del objeto seguido del nombre de la propiedad usando **notacion de puntos** o **corchetes**. La notacion de puntos se utiliza cuando ya conocemos con antelacion el nombre de la propiedad a la que queremos acceder.

```javascript
const miobjeto = {
	nombre : "Exe",
	edad : "22",
};

console.log(miobjeto.edad); //22
console.log(miobjeto["nombre"]);//Exe
```

El uso de cualquiera de estas tecnicas es irrelevante, salvo cuando necesitamos acceder a la propiedad a traves del valor de una variable, tenemos que usar corchetes o si el nombre de la variable tiene caracteres no validos como por ejemplo "espacios" o numeros.

Los corchetes ademas nos proveen una forma para obtener la clave de la propiedad como resultado de cualquier expresion de una variable (**propiedades calculadas**). Es decir que el nombre de la propiedad puede ser una variable.

```javascript
//Ejemplo 1

const miobjeto = {
	nombre : "Exe",
	edad : 22,
};

var nombrePropiedad = "nombre";

console.log(miobjeto[nombrePropiedad]); //Exe

//Ejemplo 2

let fruta = prompt("¿Que fruta comprar?", "Manzana")
const comida = {
	[fruta] : 5	
}

console.log(comida.manzana);// 5

//Ejemplo 3
let fruta = prompt("¿Que fruta comprar?")

const comida = {
	["fru" + "ta"] : 5	
}
console.log(comida[fruta]);// 5, el nombre de la propiedad sera el que especifiquemos
```

Ademas de leer los valores de las propiedades tambien podemos **asignar nuevas propiedades al objeto o modificarlas** usando notacion de puntos o notacion de corchetes.

```javascript
const miobjeto = {
	nombre : "Exe",
	edad : 22,
};

console.log(miobjeto.nombre); //Exe

console.log(miobjeto.carrera); //undefined

miobjeto.nombre = "Sofia";

console.log(miobjeto.nombre); //Sofia

miobjeto.carrera = "Turismo";

console.log(miobjeto.carrera); //Turismo

```

Los objetos tambien pueden **contener objetos**. Si queremos acceder a las propiedades del objeto dentro del objeto, tenemos que indicar el nombre del objeto al que pertenecen y el nombre del objeto al que ese objeto pertenece. Los nombres se concatenan con notacion de puntos en el orden en el que se han incluido en la jerarquia.

```javascript
const miobjeto = {
	nombre : "Exe",
	edad : 22,
	carrera : {
		nombre : "Informatica",
		duracion : 5,
	}
};

console.log(miobjeto.nombre); //Exe

console.log(miobjeto.carrera.nombre); //Informatica
  
console.log(miobjeto["carrera"]["nombre"]); //Informatica
```

El operador **delete** es un operador unario, que cuando se aplica a la propiedad de un objeto o elemento de un array lo elimina. El problema es que no es recomendable ademas de no tener una buena optimizacion, por lo que podemos poner la propiedad objeto en undefined (Esto no sucede con los maps).

```javascript
delete miobjeto.propiedad;
delete miobjeto["propiedad"];
//La forma mas optima

miobjeto.propiedad = undefined;
miobjeto["propiedad"] = undefined;
```

Para saber que propiedades tiene un objeto, se puede utilizar el metodo **Object.keys(objeto)** y devuelve un array de strings con los nombres de las propiedades del objeto.

Tambien se utiliza **objeto.hasOwnProperty(“nombre de propiedad”)** devuelve true si la propiedad existe en el objeto.

#### Configuracion de las propiedades de objetos

Las propiedades de objeto, aparte de un value, tienen tres atributos especiales llamados **indicadores**. 

* **writable**: Si es true, puede ser editado, de otra manera es solo lectura.

* **enumerable**: Si es true, puede ser listado en bucles, de otro modo no puede serlo.

* **configurable**: Si es true, la propiedad puede ser borrada y estos atributos pueden ser modificados, si es false no, aunque se permite el cambio del valor de la propiedad.

Al crear una propiedad, todos los indicadores son true. 

Hay metodos de objetos que nos permiten interactuar con los indicadores, y el valor devuelto por estos se los denomina **descriptor de propiedad**.

```javascript
//1-Object.getOwnPropertyDescriptor(objeto, nombre propiedad)
//Permite consultar toda la informacion sobre una propiedad.

let objeto = {
    nombre : "Exe",
    apellido : "Bobruk"
}

let descripcion = Object.getOwnPropertyDescriptor(objeto, "nombre");

//2-Object.getOwnPropertyDescriptors(objeto).
//Permite obtener todos los descriptores al mismo tiempo.

let objeto = {
    nombre : "Exe",
    apellido : "Bobruk"
}

let descripcion = Object.getOwnPropertyDescriptors(objeto);

//3-Object.defineProperty(objeto, nombre propiedad, descriptores)
//Permite modificar los indicadores y la propiedad value de la propiedad o crear nuevas propiedades. Si el indicador no es proporcionado, es asumido como false salvo que la propiedad ya haya sido creada y solo estemos modificando un valor, el resto queda igual.

let objeto = {};

Object.defineProperty(objeto,"DNI",{
	value: "43264335",
	writable: true,
	enumerable: false,
});

//4-Object.defineProperties(objeto, propiedades).
//Permite definir varias propiedades nuevas al mismo tiempo o modficiar.

let objeto = {};

Object.defineProperties(objeto,{
	dni : {value : 43264335, writable : false},
	edad : {value : 22, writable : false},
});

//5-Podemos clonar clonar un objeto de la siguiente forma:

let objetoClonado = Object.defineProperties({},Object.getOwnPropertyDescriptors(objeto));
```

##### Object freeze y Object seal

Para evitar que se puedan modificar los objetos y que no se puedan eliminar propiedades, agregar nuevas propiedades, y modificar propiedades existentes se utiliza **Object.freeze(objeto)**. Si queremos evitar que se puedan eliminar propiedades o agregar propiedades pero que si se puedan modificar sus valores utilizamos **Object.seal(objeto)**. 

```javascript
const objeto = {
	nombreObjeto : "Persona",
	edad : 22,
};

Object.freeze(objeto); //Evita que se pueda modificar el objeto.
```

Para ver si un objeto esta frozen o sealed utilizamos **Object.isFrozen(objeto)** o **Object.isSealed(objeto)**.
### Metodos
Las propiedades que contienen funciones generalmente son llamados **metodos**. Los metodos son funciones que solo se aplican a un objeto y tambien pueden devolver valores.

```javascript
const miobjeto = {
	nombre : "Exe",
	edad : 22,
	mostrarDatos : function(){
		console.log(`Mi nombre es ${miobjeto.nombre}`);
	}
};

miobjeto.mostrarDatos(); //Mi nombre es "Exe"

miobjeto.mostrarEdad = function(){
	console.log(`Mi edad es ${miobjeto.edad}`);
};

miobjeto.mostrarEdad(); //22


//Azucar sintactico
const miobjeto = {
	nombre : "Exe",
	edad : 22,
	mostrarDatos(){
		console.log(`Mi nombre es ${miobjeto.nombre}`);
	}
};
```


## Destructurando objetos
Para destructurar objetos se utiliza **const {nombre de la propiedad} = nombre objeto**. Le asignamos a una variable el valor de la propiedad de un objeto.

```javascript
const objeto = {
	nombre : "Persona",
	edad : 22,
};

const {nombre} = objeto;
const {edad} = objeto;
// Ahora la variable nombre y edad tienen el valor de la propiedad nombreObjeto y edad.
console.log(nombre); //Persona
console.log(edad); //22

//Forma simplificada

const {nombre, edad} = objeto;

//Tambien podemos ponerle nombres a las variables.

const {nombre : nombreObjecto, edad : edadObjeto} = objeto;

//Desestructuracion para asignar variables desde objetos anidados


const user = {
  johnDoe: { 
    age: 34,
    email: 'johnDoe@freeCodeCamp.com'
  }
};

//Le asignamos a las variables age y email el valor de use.johnDoe.age y use.johnDoe.email respectivamente.
const { johnDoe: { age, email }} = user;

//Le asignamos a las variables userAge y userEmail el valor de use.johnDoe.age y use.johnDoe.email respectivamente.
const { johnDoe: { age: userAge, email: userEmail }} = user;

//Podemos utilizar la sintaxis de desestructuracion para pasar un objeto como parametro de funcion.

const stats = {
  max: 56.78,
  standard_deviation: 4.34,
  median: 34.54,
  mode: 23.87,
  min: -0.75,
  average: 35.85
};
const half = (stats) => (stats.max + stats.min) / 2.0; 

// Es equivalente a 

const stats = {
  max: 56.78,
  standard_deviation: 4.34,
  median: 34.54,
  mode: 23.87,
  min: -0.75,
  average: 35.85

};

const half = ({max, min}) => (max + min) / 2.0;

```
## Spread Operator para objetos
El **spread operator**  para objetos se utiliza para crear copias de objetos existentes con valores nuevos o actualizados, o mismo para hacer una copia de un objeto con mas propiedades. 

```javascript
const objeto = {
	nombreObjeto : "Persona",
	edad : 22,
};

const objetoClonado = {
    raza : "Blanca",
    ...objeto //Spread operator
};

console.log(Object.keys(objetoClonado)); //Raza, nombreObjeto, edad
```

Tambien se puede utilizar **Object.assign()** para crear un NUEVO objeto copiando los valores de otro y siendo guardados en un nuevo espacio en memoria. La función `Object.assign()` acepta cualquier número de objetos como argumentos. Los objetos se combinan en el orden en que se especifican. Si una propiedad existe en dos o más objetos, el valor de la propiedad del último objeto especificado se usa en el nuevo objeto.

```javascript
const objeto = {
	nombreObjeto : "Persona",
	edad : 22,
};

const objetoClonado = Object.assign({}, objeto);
```
## This
Para asegurar que siempre referenciamos al mismo objeto con el que estamos trabajando, podemos utilizar **this**. La palabra clave this **referencia el objeto en el que la instruccion se esta ejecutando**. 

```javascript
const miobjeto = {
	nombre : "Exe",
	edad : 22,
	mostrarDatos : function(){
		console.log(`Mi nombre es ${this.nombre}`);
	}
};

miobjeto.mostrarDatos(); //Mi nombre es "Exe"
```

El valor de this dentro de una funcion depende de como se llama a esa funcion. Si la funcion se llama en el contexto de un objeto, el valor de this sera el objeto. Si la funcion se llama sin un objeto especifico en el contexto, el valor de this sera el objeto global en el navegador. Si la function se llama sin un objeto especifico en el contexto en modo estricto, el valor de this sera undefined.

Sin embargo, en una función definida con la palabra clave `function`, el valor de `this` no se mantiene en el alcance lexico. Esto significa que si intentas acceder a `this` dentro de una función definida con `function`, no podrás acceder al `this` del alcance lexico.

```js
let myObject = {
  myProperty: 'value',
  myMethod: function() {
    console.log(this.myProperty);
  }
};

myObject.myMethod(); // imprime 'value'
let myFunction = myObject.myMethod;
myFunction(); // imprime 'undefined'
```

Para solucionar este problema, puedes usar una función de flecha en lugar de una función definida con `function`. Las funciones de flecha tienen una vinculación de `this` léxica, lo que significa que el valor de `this` se mantiene en el alcance lexico. Por lo tanto, en el siguiente código:

```js
let myObject = {
  myProperty: 'value',
  myMethod: function() {
    let myFunction = () => {
      console.log(this.myProperty);
    };
    myFunction();
  }
};

myObject.myMethod(); // imprime 'value'
```

La función de flecha `myFunction` puede acceder a `this` en el alcance de `myMethod` y se refiere al objeto `myObject`.

En los eventos, this se refiere al elemento que recibe el target.
## Encadenamiento opcional
El operador de **encadenamiento opcional** **?.** permite leer el valor de una propiedad ubicada dentro de una cadena de objetos conectados sin tener que validar expresamente que cada referencia en la cadena sea válida, ya que si no es valida, en vez de causar un error retorna undefined.

```javascript
const persona = {
	nombre : "Mariana",
	pais : "Mexico",
	edad : 25,
	lenguajes: {
		javascript: true,
		PHP: false
	},
	saludar (){
		alert("Hola")
	}
}

console.log(persona.lenguajes.javascript)// True

const persona1 = {};

console.log(persona1.lenguajes)// undefined
console.log(persona1.lenguajes.javascript)// error
console.log(persona1.lenguajes?.javascript)// undefined
```

**Dato:** Deberíamos usar ?. solo donde está bien que algo no exista. Por ejemplo, si de acuerdo con la lógica de nuestro código, el objeto user debe existir, pero address es opcional, entonces deberíamos escribir user.address?.street y no user?.address?.street. De esta forma, si por un error user no está definido, lo sabremos y lo arreglaremos. De lo contrario, los errores de codificación pueden silenciarse donde no sea apropiado y volverse más difíciles de depurar.

[[Constructor en javascript]]
[[Herencia prototipica en JS]]
[[Clases en javascript]]
[[Getters y setters]]
[[Metodos globales]]
[[Objetos nativos]]
[[Objeto Number]]
[[Objetos  String]]
[[Objeto Array]]
[[Objeto Date]]
[[Objetos map y set]]
[[Objeto Math]]
[[Objeto Window]]
[[Objeto Document]]
[[Objeto Element]]
[[Objeto Console]]
[[Function Borrowing]]