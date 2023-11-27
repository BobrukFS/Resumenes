# [[Clases]] en javascript

Las clases son una mejora sintactica sobre la herencia basada en prototipos de JavaScript pero siguen siendo lo mismo, es "azucar sintactico".

Siempre el nombre de la clase empieza con mayuscula. Se utilisa UpperCamelCase.

```javascript
//Declaracion de clases

class Animal{
	//Metodo constructor
	constructor(raza, especie, genero){
		this.raza = raza;
		this.especia = especie;
		this.genero = genero;
	}
	//Metodo de clase
	method1(){}
	method2(){}
	method3(){}
};

let conejo = new Animal(coballo, conejo, hembra);

//Expresiones de clases. Las expresiones de clase pueden ser nombradas o anónimas. El nombre dado a la expresión de clase nombrada es local dentro del cuerpo de la misma.

let Animal = class{
	//Metodo constructor. Solo puede haber un método especial con el nombre "constructor" en una clase.
	constructor(raza, especie, genero){
		this.raza = raza;
		this.especiE = especie;
		this.genero = genero;
	}
	//Metodo de clase
	method1(){}
	method2(){}
	method3(){}
};

let conejo = new Animal(coballo, conejo, hembra);
```
## Propiedades
Los **class fields** nos permite agregar una propiedad a la clase que se comparte con las instancias, no es como las propiedades en un constructor que son unicas en cada instancia. Cuando modificamos el classfields se modifica para las demas instancias. 

```javascript
class Animal {
	salvaje = true;
	constructor(color){
	this.tonalidad = color;
	}
};

let conejo = new Animal("Negro");

console.log(conejo.salvaje); //true
console.log(Animal.salvaje); //undefined
```
### Propiedades estaticas
La palabra clave **static** define una propiedad estatica para una clase. Las propiedades estaticas se utilizan cuando queremos almacenar datos a nivel de clase, **sin estar vinculados a las instancias**. Son atributos compartidos por todos los objetos.

```javascript
class Animal {
	static salvaje = true; //Es equivalente a Animal.salvaje = true;
	constructor(name){
		this.speed = 0;
		this.name = name;
	}
};

class Rabbit extends Animal {
	
};

let conejo = new Rabbit("Conejo");

console.log(conejo.speed); //0
console.log(conejo.salvaje); //undefined
console.log(Animal.salvaje); //true
```
## Metodos
Los métodos de clase no son enumerables. La definición de clase establece el indicador enumerable a false para todos los métodos en "prototype". Esto es bueno porque si hacemos for..in a un objeto usualmente no queremos iterar sus métodos de clase. **Los metodos se pueden llamar desde las instancias**.

```javascript
class Rectangulo{
	constructor(alto, ancho){
		this.alto = alto;
		this.ancho = ancho;
	}
	calcArea (){
		return this.alto * this.ancho;
	}
};

const cuadrado = new Rectangulo (10, 10);

console.log(cuadrado.calcArea()); // 100
```
### Metodos estaticos
La palabra clave **static** define un metodo estatico para una clase. Los metodos estaticos son llamados sin instanciar su clase y **no pueden ser llamados mediante una instancia de clase**. Son a menudo usados para crear funciones de utilidad para una aplicacion. Son compartidos por todos los objetos.

```javascript
//Ejemplo
class Punto {
  constructor ( x , y ){
    this.x = x;
    this.y = y;
  }

  static distancia ( a , b) {
    const dx = a.x - b.x;
    const dy = a.y - b.y;

    return Math.sqrt ( dx * dx + dy * dy );
  }
}

const p1 = new Punto(5, 5);
const p2 = new Punto(10, 10);

console.log (Punto.distancia(p1, p2)); //7,071067
```
## Herencia de clases
Para que una clase se extienda a otra utilizamos la palabra clave **extends**. Para ello escribimos la **clase hija extends clase padre**. Esto lo que va a hacer es que cuando  busquemos un metodo o una propiedad y no la encontramos en nuestra clase, la busquemos en la clase en la que se extendio, esto es lo mismo que cuando utilizamos prototipos, la clase padre sera prototipo de la clase hija.

```javascript
class Animal {
	constructor(name){
		this.speed = 0;
		this.name = name;
	}
	run(speed){
		this.speed = speed;
		alert(`${this.name} corre a una velocidad de ${this.speed}`);
	}
	stop(){
		alert(`${this.name} se ha quedado quieto`);
	}
};

let hipopotamo = new Animal("Hipopotamo");

class Rabbit extends Animal {
	jump(){
		alert("Empieza a saltar");
	}
};

let conejo = new Rabbit("Conejo");

conejo.run(5); //Conejo corre a una velocidad de 5.
hipopotamo.jump(); //error
conejo.jump(); //Empieza a saltar
console.log(conejo.speed); //Ahora es 5.

//Se puede realizar una herencia encadenada

class Coballo extends Rabbit { //Coballo < Rabbit < Animal
	roer(){
		console.log("Merodeando")
	}
};


console.log(Object.getPrototypeOf(coballo)); //Rabbit
console.log(Object.getPrototypeOf(conejo)); //Animal
```
### Sobreescribir metodos y propiedades de la clase padre.
#### Sobreescribir metodos
Podemos sobreescribir un metodo de la clase padre.

```javascript
class Animal {
	constructor(name){
		this.speed = 0;
		this.name = name;
	}
	run(speed){
		this.speed = speed;
		alert(`${this.name} corre a una velocidad de ${this.speed}`);
	}
	stop(){
		alert(`${this.name} se ha quedado quieto`);
	}
};

let hipopotamo = new Animal("Hipopotamo");
hipopotamo.run(5); //Hipopotamo corre a una velocidad de 5.

//Sobreescribir un metodo

class Rabbit extends Animal {
	run(){
		console.log("Esta corriendo");
	}
};

let conejo = new Rabbit("Conejo");
conejo.run() //Esta corriendo

//Modificar un metodo

class Rabbit extends Animal {
	saltar(){
		console.log("Saltando")
	}
	run(){
		super.run();
		this.saltar();
	}
};

let conejo = new Rabbit("Conejo");
conejo.run(10) //Conejo corre a una velocidad de 10. 
			  //Saltando
```
#### Sobreescribir propiedades

Si una clase extiende otra clase y no tiene constructor, se genera el siguiente constructor vacio:

```javascript
class Rabbit extends Animal {
	constructor(...args) {
		super(...args);
	}
};
```

Entonces si nosotros queremos agregar atributos a nuestra clase extendida o sobreescribir, tenemos que utilizar **super(...args)** antes de usar this, si no se producira un error.

```javascript
class Animal {
	constructor(name){
		this.speed = 0;
		this.name = name;
	}
};

class Rabbit extends Animal {
	constructor(name, raza) {
		super(name);
		this.speed = 5;
		this.raza = raza;
	}
};

let coballo = new Rabbit("Jack", "Coballo");
```