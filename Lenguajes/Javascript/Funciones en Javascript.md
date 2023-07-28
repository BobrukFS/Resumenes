# [[Funciones]] en Javascript

Las **funciones** se declaran usando la palabra reservada **function**, seguido del nombre, seguido de parentesis donde iran los **parametros** y seguido del codigo entre llaves. 

Las funciones se **llaman** escribiendo el nombre de la función seguido de paréntesis.

```javascript
//Declaraciones de funciones, podemos acceder de cualquier parte del codigo ya que se aplica hoisting.

function nameFunction(Parametros){
	codigo de la funcion
};

nameFunction(Parametro);

//Expresiones de funciones, son parte del flujo control regular, es decir no se produce hoisting.

let nameFunction = function(Parametros){
	codigo de la funcion
};

nameFunction(Parametro);
```

Algunas funciones producen un valor, y algunas no, cuyo unico resultado es un **efecto secundario**.

Una declaracion **return** determina el valor que es retornado por la funcion. Cuando la ejecucion lo alcanza, la funcion se detiene y el valor se devuelve al codigo de llamada. Si queremos procesar el valor que devuelve la funcion, tenemos que asignar dicha funcion a una variable. El interprete primero ejecuta la funcion y luego asigna el valor que devuelve la funcion a una variable. Tambien se puede devolver una funcion que a su vez retorne algo.

```javascript
//Si utilizamos return

function sumar(a, b){
	return a + b;
}
console.log(sumar(2,4));//6

//Si no utilizamos return

function sumar(a, b){
	 a + b;
}
console.log(sumar(2,4));//undefined
```

Una funcion puede tener **multiples parametros** separandolos con coma o ningun parametro. Los parametros se comportan como variables locales de la funcion.

Un **argumento** es el valor que es pasado a los parametros de la funcion cuando esta es llamada. 

```javascript
function areaCuadrado(ancho, altura){
	return ancho * altura;
}

areaCuadrado(2, 3);//6
```

Para evitar pasar un argumento a un parametro podemos utilizar undefined. Si pasamos demasiados argumentos, los adicionales son ignorados.

Ademas, podemos especificar un valor **default** que proporciona un valor predeterminado cuando no se le pasa un argumento al parametro.

```javascript
function areaCuadrado(ancho = 2, altura = 4){
	return ancho * altura;
}

areaCuadrado(undefined, 8);//16
```

## Funciones anonimas

Estas funciones no tienen nombre, y se invocan usando el nombre de la variable que las almacena (**expresion de funcion**) o pueden ser creadas en un parametro.

```javascript

//Ejemplo 1
function ask(question, yes, no) {
    if (confirm(question)) yes()
    else no();
  }
  
  ask(
    "Estás de acuerdo?",
    function() { alert("Estás de acuerdo"); },//Funcion anonima sin asignar a una variable.
    function() { alert("Cancelaste la ejecución."); }//Funcion anonima sin asignar a una variable.
  );
  
//Ejemplo 2

let sum = function(a, b){
	return a + b
}

```

## Funciones flecha
En lugar de la palabra clave function, se puede usar una **=>**. La flecha viene **despues de la lista de parametros** y es **seguida por el cuerpo de la funcion**.

Cuando solo haya un parametro, los parentesis alrededor de la lista de parametros pueden ser omitidos. Cuando la función no posee cuerpo y sólo tiene un valor de retorno, la sintaxis de "función de flecha", te permite omitir la palabra clave return, así como los corchetes que rodean el código. Esto ayuda a simplificar las funciones más pequeñas en sentencias de una sola línea:
```javascript
let sumarDos = (a,b) => a + b;

let sumarDosMostrar = (a,b) =>{
	console.log(a + b);
}
```

Se suelen utilizar cuando tenemos una funcion que no reutilizamos en otro lugar. Es azucar sintactico.

Tiene limitaciones, como no tenemos referencia a this o super, por eso tampoco se debe usar como metodos. No se puede utilizar como constructor.
## Funciones anidadas
Una funcion puede estar dentro de una funcion produciendo nuevos ambitos o scopes para las variables que estan dentro de ellas. 

```javascript

//Ejemplo 1

function funcion1(nombre){
    return "Hola como estas " + nombre;
}

function funcion2(frase){
    alert(`${funcion1("exe")}  ${frase}`);
}

funcion("Todo bien?");// Hola como estas exe, todo bien?

//Ejemplo 2

function global(nombre){
    let variable = nombre;
    console.log(variable); //Exequiel
    function local(frase){
       console.log(`${frase} ${variable}`);
    }
    local("Como estas?")
}
global("Exequiel"); //Como estas? Exequiel.
```

**Dato**: Podemos utilizar doble parentesis para ejecutar una funcion anidada.
## Funciones de cierre (closure)
Las funciones **closure** es una funcion que guarda referencias del entorno lexico donde fue creada, recuerda el conjunto de variables a las que podian acceder, por mas que se las invoque desde otro scope. Permite tener variables, estructura de datos, etc privadas.

```javascript
//Ejemplo 1
   function multiplicador (factor){
        return numero => numero * factor; //Es una funcion
   }

   let duplicar = multiplicador(2); // numero = numero * 2
   console.log(duplicar(5));// 5 * 2 = 10
   
//Ejemplo2
 const miContador = (function(){
	 let _contador = 0;

	function incrementar() {
		return _contador++;
	}

	function decrementar() {
		return _contador--
	}

	function valor() {
		return _contador;
	}

	return {
	incrementar,
	decrementar,
	valor
	}
 })()

 console.log(miContador.incrementar()); //0

 console.log(miContador.valor()); //1

 console.log(miContador.decrementar()); //1

 console.log(miContador.valor()); //0
 
//Ejemplo 3

function crearContador () {
    let _contador = 0;
    return function incrementar(){
        return _contador += 1;
    }

}
let contador = crearContador();
console.log(contador()); //1
console.log(contador()); //2

//Ejemplo 4

function crearImpresoraDeMensajes(tipo, estilos) {
  return function mensaje(str) {
    console.log(`%c ${tipo}: ${str} `, estilos);
  }
}

const error = crearImpresoraDeMensajes('Error', 'background: red; color: white;');

const warning = crearImpresoraDeMensajes('Warning', 'background: orange; color: white;');

const exito = crearImpresoraDeMensajes('Éxito', 'background: green; color: white;');

error("Hola");

error("chau");
```

## Funciones callbacks
Es una funcion que se pasa a otra funcion como un argumento, que luego se invoca dentro de la funcion externa.

```javascript
//Ejemplo 1
function calculadora(modo, numero1, numero2) {
     return modo(numero1,numero2)
}

function multiplicar(numero1,numero2) {
     return numero1 * numero2
}

function suma(numero1,numero2) {
     return numero1 + numero2
}

console.log(calculadora(multiplicar,2,3)); // 6

//Ejemplo 2
function ask(question, yes, no){

     if (confirm(question)){
          yes();
     }
     else{
          no();
     }
}

function showOk(){
     alert("Estas de acuerdo")
}

function showCancel(){
     alert("No estas de acuerdo")
}

ask("Quieres dar tus datos", showOk, showCancel);
```

**Dato**: Cuando queremos llamar una funcion, tenemos que declarar los parentesis despues del nombre, pero cuando queremos referenciar a una funcion, debemos omitir parentesis.
## Expresiones de funcion ejecutadas inmediatamente

Los IIFE son expresiones de funciones que se ejecutan luego que se definen. Es un patron de diseño conocido como **funcion autoejecutable**. Estas solo necesitan ser invocada una vez, inmediatamente luego de su creacion. Esta forma de usar las funciones se usa muy amenudo en patrones y bibliotecas de Javascript.

Para crear un IIFE tenemos que declarar una funcion anonima dentro de un block scoping e inmediatamente llamarla.

```javascript
//Declaracion y ejecucion

function funcionNoInmediata(){
	console.log("ejemplo 0");
}

funcionNoInmediata();

//IIFE
(() =>{
	console.log("ejemplo 1")
})();

(function(){
	console.log("ejemplo 2")
})();
```

Las IIFE permiten la privacidad de los datos, es decir permite proteger el alcance de las funciones y las variables dentro de ella. Ademas permite evitar asignar un nombre a la funcion para evitar ocupar el global namespace y asi evitar la posibilidad de que ocurra alguna colision entre identificadores.

Nos permite obtener un mejor rendimiento usando IIFEs. Si pasamos objetos globales (window, document, jQuery, etc) a una funcion anonima, y luego usamos estos objetos a traves de su referencia local, Javascript no tendra la necesidad de hacer busquedas en el ambito global ya que JS primero busca propiedades en el ambito local, y mientras no encuentre la referencia adecuada continua su busqueda hacia arriba, hasta llegar al ambito global. Ser capaces de poner objetos de ambito global en un ambito local nos permite mejorar el rendimiento porque las referencias se resuelven mas rapido.

```javascript
// Función anónima con 3 argumentos

(function(window, document, $) {

// Aquí podemos usar las referencias window, document, jQuery en un ámbito local 

})(window, document, window.jQuery); // Los objetos globales son pasados a la función anónima
```

**Dato**: Se les puede pasar parametros.  

Tambien nos permite optimizar el proceso de minificacion ya que los objetos globales requeridos son pasados a la funcion anonima como parametros, un minificador puede asignar un nuevo nombre a las variables locales, que consten de una sola letra.

```javascript 
// Función anónima con 3 argumentos

(function(w, d, $) {

// Aquí se pueden usar las referencias de forma local que se han obtenido de window, document, y jQuery

})(window, document, window.jQuery); // Objetos globales pasados como parámetros
```

Se suele utilizar para utilizar async y await.

## Rest Parameter

Nos permite representar un numero indefinido de argumentos como un array.
El ultimo parametro de una funcion se puede prefijar con **...** lo que hara que todos los argumentos restantes se coloquen dentro de un array. Si hay otros parametros antes que el, sus valores no seran parte de ese array.

```javascript
//Ejemplo
function lista(a, b, ...otrosProductos){
    console.log("a=" + a);
    console.log("b=" + b);
    console.log("Resto de elementos de la lista;", otrosProductos);
};

lista("pc", "monitor", "manzana","pera", "sandia"); //a = pc
//b = monitor Resto de elementos de la lista = [manzana, pera, sandia].

//Ejemplo 2
function numerosPares (a,b,...c){
    return a + b + c[1];
}
console.log(numerosPares(2,4,2,4)); //10

//Otro ejemplo

function sum(...theArgs) {
  let total = 0;
  for (const arg of theArgs) {
    total += arg;
  }
  return total;
}

console.log(sum(1, 2, 3));
// Expected output: 6

console.log(sum(1, 2, 3, 4));
// Expected output: 10
```

**Dato**: Es parecido al objeto **arguments** (es una variable local disponible en todas las funciones que no son flecha) solo que este ultimo guarda todos los valores de los argumentos pasados a esa funcion en una estructura similar a un array mientras que rest guarda los argumentos restantes pasados en la funcion en una estructura similar a un array.  El objeto arguments es útil para funciones llamadas con más argumentos de los que declara aceptar formalmente. Esta técnica es útil para funciones a las que se les puede pasar un número variable de argumentos, como `Math.min()`.

**Dato:** Tenemos la consola de JS en la devtools. Si escribimos **window** podemos ver todas las funciones. Para limpiar la consola tocamos CTRL + L.

[[Hoisting]]
[[Scopes en javascript]]
[[Call Stack en Javascript]]