# [[Estructuras de control]] en Javascript

## Condicionales
A diferencia de los ciclos, los condicionales se ejecutan solo 1 vez.
### If, else if y else
La ejecucion condicional en Javascript se crea con la palabra clave **if** seguida de la **condicion entre parentesis** y las **instrucciones** que queremos ejecutar si se cumple la condicion entre **llaves({})**. Al evaluarse la condicion, esta devuelve un valor logico (true o false), si es true se ejecutan las instrucciones.

Podemos utilizar la palabra clave **else if**. para crear otra condicion de ejecucion alternativa, de una manera separada. Esto se utiliza si necesitamos comprobar multiples condiciones.

Podemos utilizar la palabra clave **else** seguida de las instrucciones entre llaves que se ejecutaran si no se cumple ninguna condicion.

```javascript
if(ejemplo > 20){
	//Si la evaluacion de la condicion es true se ejecuta la instruccion de este bloque.
	//Si la evaluacion de la condicion es falsa no sucede nada o se pasa hacia la siguiente condicion.
}
else if(ejemplo > 15){
	//Si la evaluacion de la condicion es true se ejecuta la instruccion de este bloque.
	//Si la evaluacion de la condicion es falsa no sucede nada o se pasa hacia la siguiente condicion.
}
else{
	//Si ninguna condicion se cumple, se ejecutan las instrucciones de este bloque.
}
```

#### Operador condicional ?

La sintaxis de este operador es: Condición? Valor1 : Valor2;. Si la condición es verdadera, el operador tomara el valor 1, de lo contrario tomara el valor 2. No se puede utilizar la palabra clave return dentro de este operador ternario. Es el remplazo de if, else, y else if.

```js
let ejemplo1 = 8; ejemplo1 > 10? ejemplo1 = "Es mayor que 10" : ejemplo1 = "Es menor que 10"; //Es menor que 10
```

##### Multiples ?

Es como utilizar else if

```js
let age = prompt('age?', 18); 

let message = (age < 3) ? 'Hi, baby!' : (age < 18) ? 'Hello!' : (age < 100) ? 'Greetings!' : 'What an unusual age!'; 

alert( message );
```

### Switch
Si tenemos que comprobar multiples condiciones, en lugar de varias instrucciones else if, podemos usar la instruccion **switch**. La instruccion evalua una expresion (generalmente una variable), compara el resultado con multiples valores y ejecuta las instrucciones correspondientes al valor que coincide con la expresion (con switch solo se puede comprobar la igualdad).

La sintaxis incluye la palabra clave **switch** seguida de la expresion entre parentesis (pueden haber varias expresiones separadas por coma), luego entre llaves iran las condiciones a cumplir (separadas por comas para cada expresion respectivamente) antecedidas por la palabra clave **case**. Si el primer case no coincide con el valor de la variable, se evalua el siguiente case, y asi sucesivamente. Si ningun case coincide con el valor, se ejecutan las instrucciones **default**.

Para evitar que el sistema ejecute las instrucciones de cada case después de que se encuentra una coincidencia, tenemos que incluir la instrucción **break** al final de cada case.

```javascript
let ejemplo = 5

switch(ejemplo){
  case "ejemplo1" : console.log("La expresion es ejemplo1");
  break;
  case 5 : console.log("La expresion es 5");
  break; // La expresion es 5
  default : console.log("No es ninguno");
  break;
}
```

```javascript
let ejemplo5 = "exe";
let ejemplo6 = "Bobruk";

switch(ejemplo5, ejemplo6){
    case "exe","Bobruk" : console.log("Mi nombre es exe y mi apellido Bobruk");
    break;
}

```

Ademas varias variantes de case que comparten el mismo codigo a ejecutar pueden ser **agrupadas**.

```javascript
let ejemplo = 5

switch(ejemplo){
  case "ejemplo1" :
  case 5 : console.log("Esta es una instruccion agrupada");
  break;
}
```

## Ciclos 
### For
La instruccion **for** ejecuta el codigo entre llaves repetidamente mientras la condicion sea verdadera. La sentencia condicional es evaluada al principio de cada iteracion del bucle y continuara siempre y cuando sea true. Cuando la condicion sea false al inicio de la iteracion, el bucle dejara de ejecutarse. La sintaxis es :

```javascript
for(inicializacion; condicion; evolucion){
	bloque de codigo a ejecutar mientras la condicion sea verdadera
}
```

El primer parametro (**inicializacion**) establece los valores iniciales del bucle (inicializamos una variable, comunmente con el nombre i de iteracion) y es el valor que sera evaluado en cada condicion. El segundo parametro (**condicion**) es la condicion que queremos comprobar. El tercer parametro (**evolucion**) es una instruccion que determina como van a evolucionar los valores iniciales en cada ciclo (En cada iteracion).

```javascript
let total = 0

for(let i=0; i < 10; i++){

 total += 2;
 console.log(total); //2, 4, 6, 8, 10, 12, 14, 16, 18, 20

}
```

**Dato:** Cualquier parametro de for puede ser omitida. Es decir nosotros podemos emitir la parte de inicialización sin poner nada, aunque siempre debe estar el ; .
#### Diferencia entre For y While
La instrucción for es útil cuando podemos determinar ciertos requisitos, como el valor inicial del bucle o el modo en que evolucionarán esos valores en cada ciclo. Cuando esta información es poco clara o cuando no sabemos el numero de iteraciones, podemos utilizar la instrucción while.
### While
La instruccion **while** solo requiere la declaracion de la condicion entre parentesis y el codigo a ser ejecutado entre llaves. El bucle se ejecuta constantemente mientras la condicion sea verdadera.

```javascript
let contador = 0;

while(contador < 10){
    contador++;
    console.log(contador)//1, 2, 3, 4, 5, 6, 7, 8, 9, 10
}
```

### Do while
Este ciclo ejecuta al menos sus instrucciones una vez y comienza a chequear si debe detenerse luego de esa ejecucion o seguir. Si la condicion es falsa, solo se habra ejecutado esa primera vez, y si no, se repetira el ciclo hasta que la condicion sea falsa.

```javascript
let tunombre;

do{
   tunombre = prompt("Escribe aqui tu nombre");
}while(!tunombre); //Se ejecutara prompt hasta que se ponga un nombre
```

### For of

La sentencion for...of ejecuta un bloque de codigo para cada elemento de un objeto iterable (Ejemplos de objetos iterables son arrays, strings, NodeList, Map, set, etc). **Of** va a guardar en la variable el elemento que se itera.

```javascript
for(let variable of iterable){
		statement
	}
```

Donde en cada iteracion el elemento correspondiente es asignado a la variable. 

```javascript
let objetoIterable = ["Hola", "Exequiel", "Bobruk", "Sofiita"];

  

for(let variable of objetoIterable){

    console.log(`El elemento que se le asigna a la variable en esta iteracion es ${variable}`); 
}
//El elemento que se le asigna a la variable en esta iteracion es "Hola"
//El elemento que se le asigna a la variable en esta iteracion es "Exequiel"
//El elemento que se le asigna a la variable en esta iteracion es "Bobruk"
//El elemento que se le asigna a la variable en esta iteracion es "Sofiita"
```

**Dato**: Se puede utilizar la funcion **entries()** en un conjunto con un bucle for of para acceder al indice de cada elemento del iterable en cada iteracion. La funcion **entries** devuelve un objeto iterable que contiene pares de clave / valor para cada elemento del iterable, donde la clave es el indice y el valor es el elemento en si. Esto se puede utilizar en cualquier bucle. En el caso del bucle `for...of`, la clave será el índice del elemento en el iterable y el valor será el propio elemento. En el caso del bucle `for...in`, la clave será el nombre de la propiedad del objeto y el valor será el valor de esa propiedad. En el caso del bucle `for` convencional, la clave será el índice del elemento en el iterable y el valor será el valor de ese elemento

```js
let myArray = ['a', 'b', 'c', 'd'];
for (let [index, value] of myArray.entries()) {
  console.log(index, value); // 0 a, 1 b, 2 c, 3 d
}
```

**Dato:** Es posible usar const en lugar de let si no se va a modificar la variable dentro del bloque.

**Dato:** No se puede utilizar para objetos.

### For in

La sentencia for...in itera sobre todas las propiedades iterables que no son simbolo de un objeto que estan codificadas por cadenas, incluidas las propiedades enumerables heradadas. **In** va a guardar en la variable: En arrays el index de la posicion del elemento y en objetos va guardar el nombre de la propiedad.

```javascript
for (let variable in iterable){
		statement
	}
```

```javascript
let objetoIterable = ["Hola", "Exequiel", "Bobruk", "Sofiita"];

objetoIterable.addProp = "PropAdd";
  

for(let variable in objetoIterable){

    console.log(`El elemento que se le asigna a la variable en esta iteracion es ${variable}`); 
}
//El elemento que se le asigna a la variable en esta iteracion es "0"
//El elemento que se le asigna a la variable en esta iteracion es "1"
//El elemento que se le asigna a la variable en esta iteracion es "2"
//El elemento que se le asigna a la variable en esta iteracion es "3"
//El elemento que se le asigna a la variable en esta iteracion es "addProp"
```

```javascript
let objeto = {
    Nombre : "Exequiel",
    Edad : "30",
    Profesion : "Agronomo",
}

for (let propiedad in objeto){
    console.log(`Estas son las propiedades ${propiedad}`);
    console.log(objeto[propiedad]);
}
//'Estas son las propiedades Nombre'
//'Exequiel'
//'Estas son las propiedades Edad'
//'30'
//'Estas son las propiedades Profesion'
//'Agronomo'


//Las propiedades de numeros enteros se ordenan, los demas apareceran segun el orden de creacion.

let codes = { 
	"49": "Germany", 
	"41": "Switzerland", 
	"44": "Great Britain", // ..
	, "1": "USA" 
	}; 
	
	for (let code in codes) { 
	alert(code); 
	}// 1, 41, 44, 49 
	
//En cambio si es un string o un numero no entero

let codes = { 
	"+49": "Germany", 
	"+41": "Switzerland", 
	"+44": "Great Britain", // ..
	, "+1": "USA" 
	}; 
	
	for (let code in codes) { 
	alert(code); 
	}// 49, 41, 44, 1 






```

Es posible que se utilice de forma más práctica con fines de depuración, ya que es una forma fácil de comprobar las propiedades de un objeto (mediante la salida a la consola o de otro modo). Aunque los arreglos suelen ser más prácticos para almacenar datos, en situaciones en las que se prefiere un par clave-valor para trabajar con datos (con propiedades que actúan como la "clave"), puede haber casos en los que desees comprobar si alguna de esas claves cumple un valor particular.

**Dato**: Debido a que el orden de iteración depende de la implementación, es posible que la iteración sobre un arreglo no visite los elementos en un orden coherente. Por lo tanto, es mejor usar un bucle `for` con un índice numérico cuando se itera sobre arreglos donde el orden de acceso es importante.

**Dato:** For in es utilizado mayormente para objetos y for of para arrays. Los objetos que pueden ser utilizados en un bucle se denominan **objetos iterables.**

[[Instrucciones de transferencia de control]]
