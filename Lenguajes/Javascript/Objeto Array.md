# Objeto Array
## Metodos en los arrays
Los arrays también son objetos e incluyen métodos para manipular sus valores.
### Push
El metodo **push(elementos)** agrega uno o mas elementos al final del array y devuelve una nueva extension del array. 

```javascript
let array = ["A", "B", "C", "D"];

array.push("E","F",[1,2]);

console.log(array);//['A', 'B', 'C', 'D', 'E', 'F', [1,2]]
```
### Unshift
El metodo **unshift(elementos)** agrega uno o mas elementos al comienzo del array y devuelve una nueva extension del array.

```javascript
let array = ["A", "B", "C", "D"];

array.unshift("E","F",[1,2]);

console.log(array);//['E', 'F', [1,2], 'A', 'B', 'C', 'D']
```
### Pop
El metodo **pop()** elimina el ultimo valor del array y lo devuelve (dicho elemento eliminado). El espacio asignado a dicho elemento se libera en la memoria inmediatamente.

```javascript
let array = ["A", "B", "C", "D"];

console.log(array.pop());//'D'
```
### Shift
El metodo **shift()** elimina el primer valor del array y lo devuelve (dicho elemento eliminado). El espacio asignado a dicho elemento se libera en la memoria inmediatamente.

```javascript
let array = ["A", "B", "C", "D"];

console.log(array.shift());//'A'
```
### Concat
El metodo **concat(array)** concatena el array con otro array pasado como argumento y devuelve un nuevo array como resultado. Este metodo no modifica los arrays originales.

```javascript
let arrayA = ["A", "B", "C", "D"];

let arrayB = [1, 2, 3, 4];

console.log(arrayA.concat(arrayB));//["A", "B", "C", "D", 1, 2, 3, 4];


```
### Splice
El metodo **splice(indice, nºremover, elementos)** tiene 3 parametros. El parametro **indice** indica en que posicion empezamos a introducir las modificaciones, el parametro **nºremover** indica el numero de valores que queremos eliminar desde el indice, y el parametro **elementos** es la lista de elementos que queremos agregar al array. Si solo queremos agregar elementos, debemos pasarle 0 al segundo parametro, y si solo queremos eliminar valores, podemos ignorar el ultimo parametro. Este metodo modifica el array original.

```javascript
//Si queremos eliminar elementos y reemplazarlos por otros

let array = ["A", "B", "C", "D"];

array.splice(2, 2, 1, 2);

console.log(array);//["A","B",1, 2]

//Si queremos solo agregar elementos

array.splice(2, 0, 1, 2);

console.log(array);//["A","B",1, 2, "C", "D"]

//Si queremos solo eliminar elementos

array.splice(2, 2,);

console.log(array);//["A","B"]
```
### Slice
El metodo **slice(comienzo, final)** copia los elementos en las posiciones indicadas por los parametros dentro de un nuevo array. Los parametros **comienzo** y **final** indican los indices del primer y ultimo elemento a copiar, sin incluirse el ultimo elemento en el nuevo array. Si no incluimos el final, se copiara todo el array.

```javascript
let arrayA = ["A", "B", "C", "D"];

let arrayB = arrayA.slice(0,3);

console.log(arrayB); //["A", "B", "C"]
```
### IndexOf
El metodo **indexOf(elemento, index)** devuelve el index en el que se encuentra por primera vez el elemento pasado al parametro **elemento**. El parametro **index**  determina el indice en el que queremos comenzar la busqueda, si no se especifica, la busqueda empieza desde el inicio. Se recorre el array de izquierda a derecha. El metodo devuelve el valor -1 si no se encuentra niguna coincidencia.

```javascript
let array = ["A", "B", "C", "D", "C"];

console.log(array.indexOf("C", 0)); //2

//Si se ponen numeros negativos se empieza la busqueda un nº de elementos a la izquierda del final. 

console.log(array.indexOf("C", -1));//4
```
### LastIndexOf
El metodo **lastIndexOf(elemento, posicion)** devuelve el indice en el que el elemento pasado al parametro **elemento** se encuentra por primera vez. Este metodo realiza una busqueda desde la posicion pasada al parametro **posicion** del array hacia atras, si se indica 0 la busqueda empezara desde el inicio del array y si no se especifica, la busqueda empezara desde el final del array hacia atras. El metodo devuelve el valor -1 si no se encuentra niguna coincidencia.

```javascript
let array = ["A", "B", "C", "D", "C", "E","F"];

console.log(array.lastIndexOf("C")); //4
console.log(array.lastIndexOf("C", 3));//2

```
### Filter
El metodo **filter(funcion)** envia los elementos del array a una funcion uno por uno y devuelve un nuevo array con todos los elementos que aprueba la funcion. El parametro **funcion** es una referencia a una funcion a cargo de validar los elementos. La funcion puede recibir tres argumentos: el elemento a evaluar, su indice y una referencia del array. Despues de procesar el valor, la funcion debe devolver un valor booleano para indicar si es valido o no.

```javascript
let ages = [30, 12, 27, 15, 33];

let adultAge = ages.filter(checkAdult);

function checkAdult(age){

    return age >= 18;

}
console.log(adultAge);//[30,27,33];

//Equivalente sin usar filter seria

let personasAdultas = []

for (let i = 0; i < ages.length; i++) {
	if (ages[i] > 18) {
		personasAdultas.push(ages[i]);
	} 
}

console.log(personasAdultas);// [30, 27, 33];
```
### Every
El metodo **every(funcion)** envia los elementos del array a una funcion uno por uno y devuelve true cuando la funcion aprueba todos los elementos. El parametro **funcion** es una referencia a una funcion a cargo de validar los elementos. La funcion puede recibir tres argumentos: El elemento a procesar, su indice y una referencia al array.

```javascript
let ages = [30, 12, 27, 15, 33];

let adultAge = ages.every(checkAdult);

function checkAdult(age){

    return age >= 18;

}
console.log(adultAge);//False;
```
### Some
El metodo **some(funcion)** envia los elementos del array a una funcion uno por uno y devuelve true cuando la funcion aprueba almenos uno de los elementos. El parametro **funcion** es una referencia a una funcion a cargo de validar los elementos. La funcion puede recibir tres argumentos: El elemento a procesar, su indice y una referencia al array.

```javascript
let ages = [30, 12, 27, 15, 33];

let adultAge = ages.every(checkAdult);

function checkAdult(age){

    return age >= 18;

}
console.log(adultAge);//True;
```
### Map
El metodo **map(funcion)** envia los elementos del array a una funcion uno por uno y crea un nuevo array con los valores que devuelve la funcion. El parametro **funcion** es una referencia a una funcion a cargo de procesar los elementos. La funcion puede recibir tres argumentos: El elemento a procesar, su indice y una referencia al array.

```javascript
let numeros = [10, 20, 30, 40, 50];

function sumaDos(numero){
	return numero + 2
}

let numerosDos = numeros.map(sumaDos);

console.log(numerosDos);//[12, 22, 32, 42, 52];

//Otro ejemplo

let students = [{name : "Exequiel", lastname : "Bobruk"}, {name : "Sofia", lastname : "Bobruk"}];

let fullname = students.map(function (student){
	return student.name + " " + student.lastname;
})

console.log(fullname)// [Exequiel Bobruk, Sofia Bobruk];

//Otro ejemplo

let students = [{name : "Exequiel", lastname : "Bobruk"}, {name : "Sofia", lastname : "Bobruk"}];

let studentsFullname = students.map(function (student){
	return {
		...student,
		fullname : student.name + " " + student.lastname 
	};
})

console.log(studentsFullname); // [{name : "Exequiel", lastname : "Bobruk", fullname : "Exequiel Bobruk"}, {name : "Sofia", lastname : "Bobruk", fullname : "Sofia Bobruk"}];

```
### forEach
El metodo **forEach()** ejecuta la funcion indicada una vez por cada elemento del array. El parametro **funcion** es una referencia a una funcion a cargo de procesar los valores. La funcion puede recibir tres argumentos: El elemento a procesar, su indice y una referencia al array.

```javascript
let numeros = [10, 20, 30, 40, 50];

function muestraNum(numero, index, numeros){
    console.log(`El numero es ${numero}`);
    console.log(index);
    console.log(numeros);
}

numeros.forEach(muestraNum);//El numero es 10.0.[10,20,30,40,50]
							//El numero es 20
							//El numero es 30
							//El numero es 40
							//El numero es 50
```
### Reduce
El metodo **reduce(funcion , valor inicial del acumulador)** ejecuta la funcion indicada una vez por cada elemento del array y va arrastrando el resultado parcial al proximo llamado. El parametro **funcion** es una referencia a una funcion  a cargo de procesar los valores. La funcion puede recibir cuatro argumentos: El resultado del llamado previo de la funcion, el elemento a procesar, su indice y una referencia al array.

```javascript
let ejArray = [1, 10, 20, 4];

function sumas(previousvalue, currentvalue){
	return previousvalue + currentvalue ;
}

let ejArrayRe = ejArray.reduce(sumas, 0);

console.log(ejArrayRe);//35

//El equivalente seria

let total = 0;

for(let i = 0; i < ejArray.length; i++){
total += ejArray[i];
}

console.log(total); //35


```
### Find
El metodo **find()** devuelve el valor del primer elemento del array que cumple la funcion de prueba proporcionada. Si no encuentra nada, entonces devuelve undefined. El parametro **funcion** es una referencia a una funcion a cargo de procesar los valores.  La funcion puede recibir tres argumentos: El elemento a procesar, su indice y una referencia al array.

```javascript
let ages = [30, 12, 27, 15, 33];

let adultAge = ages.find(checkAdult);

function checkAdult(age){
    return age >= 18;
}
console.log(adultAge);//30;
```
### findIndex
El método **find()** devuelve el indice del primer elemento del array que cumple la función de prueba proporcionada. Si no encuentra nada, entonces devuelve -1. El parametro **funcion** es una referencia a una funcion a cargo de procesar los valores. La funcion recibe tres valores: el valor procesar, su indice y una referencia al array. 

```javascript
let ages = [30, 12, 27, 15, 33];

let adultAge = ages.findIndex(checkAdult);

function checkAdult(age){
    return age >= 18;
}
console.log(adultAge);//0;
```

**Dato**: La mayoria de los metodos para arrays que realizan llamados a funciones aceptan un parametro adicional **thisArg** que es el ultimo argumento opcional.
### Join
El metodo **join(separador)** crea una cadena de caracteres con todos los elementos del array. El parametro **separador** especifica el caracter o la cadena de caracteres que queremos incluir entre los valores.

```javascript

let ages = ['30', '12', '27', '15', '33'] ;
let stringAges = ages.join("-");

console.log(stringAges);// "30-12-27-15-33"

```

### Reverse
El metodo **reverse()** invierte el orden de los elementos en el array. Este metodo modifica el array original.

```javascript
let ages = [30, 12, 27, 15, 33];
ages.reverse();

console.log(ages);//[33, 15, 27, 12, 30]
```
### Sort
El metodo **sort(funcion)** ordena los elementos en el array. El parametro **funcion** es una referencia a una funcion a cargo de comparar los elementos. La funcion recibe dos elementos desde el array y debe devolver un valor booleano indicando su orden. Si no se especifica la funcion, el metodo ordena los elementos segun unicode. Este metodo modifica el array original.

```javascript
let ages = [30, 12, 27, 15, 33, 2, 10];

let letters = ["B", "C", "A", "J", "E", "a", "b"];

ages.sort();

console.log(ages.sort());//[10, 12, 15, 2, 27, 30, 33]
console.log(letters.sort());//['A', 'B', 'C', 'E', 'J', 'a', 'b']

//Con una funcion que compare. Si la funcion retorna un valor menor que 0, se situa a en un indice menor que b. Es decir, a viene primero. Si la funcion retorna 0, se deja a y b sin cambios entre ellos. Si la funcion retorna un valor mayor que 0, se situa b en un indice menor que a.

//a - b orden ascendente.
//b - a orden descendente.

let numbers = [30, 12, 27, 15, 33, 2, 10];

let letras = ["B", "C", "A", "J", "E", "a", "b"];

function compare(a,b){
	return a - b;
}

numbers.sort(compare);

console.log(numbers);//[2, 10, 12, 15, 27, 30, 33]

// Otro ejemplo

const numbers = [10, 30, 1000, 100];

const sortedNumbers = numbers.sort((a, b) => a - b);

console.log(sortedNumbers);//[2, 10, 12, 15, 27, 30, 33]

//O numbers.sort((a, b) => a > b ? 1 : -1)

console.log(sortedNumbers);//[2, 10, 12, 15, 27, 30, 33]
```
### isArray
El metodo **isArray(array)** devuelve true si el valor es un array y false si no lo es.
### flat
El metodo **flat(profundidad)** crea una nueva matriz con todos los elementos incluyendo los del sub-array concatenados recursivamente hasta la profundidad especificada. Sirve para aplanar una matriz y ademas elimina las ranuras vacias en las matrices. 

```javascript
let array = [1, 2, 3, , [2, 4, [10, 20]]];

array.flat()// [1,2,3,2,4,[10,20]]
array.flat(2)// [1,2,3,2,4,10,20]
```
### flatMap
El metodo **flatMap(funcion)**  primero mapea cada elemento usando una funcion de mapeo, luego aplana el resultado en una nueva matriz. Es identico a un map, seguido de un flat de profundidad 1.

```js
let array = [1, 2, 3, 4, 5, 6];
console.log(array.flatMap (n => n % 2 === 0 ? [] : n * 2)); //[2,6,10]

//Es equivalente a 

console.log(array.filter(n => n % 2 !== 0).map(n => n * 2)); //[2,6,10]
```

### from

El metodo **from()** nos permite convertir una lista de nodos DOM en una matriz.

```js
const precio = Array.from(document.getElementsByClassName("precio-item"));
```
## Performance

Los metodos push/pop son rapidos, mientras que shift/unshift son lentos.

### ¿Por qué es más rápido trabajar con el final del array que con el principio?

Por ejemplo la operación shift debe hacer 3 cosas:

1. Remover el elemento con indice 0

2. Mover todos los elementos hacia la izquierda y renumerarlos.

3. Actualizar la longitud : la propiedad length.

Mientras que por ejemplo para pop, no necesita mover nada, porque los demas elementos mantienen sus indices, lo que tiene que hacer es extraer un elemento del final, limpiar el indice y acortar length.

Cuanto mas elementos haya en el array, mas tiempo tomara moverlos, mas operaciones en memoria.