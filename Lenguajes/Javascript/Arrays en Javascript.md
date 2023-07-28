# [[Arrays]] en Javascript

En javascript los arrays son dinamicos, no tienen un tamaño fijo. Esto se debe a que se busca un espacio en la memoria libre para poder almacenar el array, y se libera la direccion que ocupaba el array antes.

Ademas de que pueden tener diferentes tipos de datos, a diferencia de otros lenguajes. Esto se debe a que JS va encontrar el elemento con el tamaño maximo de byte en el array.

## Inicializar un array

Las matrices se construyen con **corchetes**, que contiene una lista de elementos separados por comas. 

```javascript
// Inicializando un array con elementos, sin tamaño fijo.

let array = [valor 1, valor 2, valor 3, valor 4];

// Inicializando un array sin elementos, sin tamaño fijo.

let arrayVacio = [];

//Inicializando un array con un tamaño

const arr = new Array(3);

//Inicializando un array vacio

const arr = new Array();

```

## Operaciones en un array

### Acceder a elementos en el array

Los arrays trabajan exactamente igual que otras variables con la excepcion que tenemos que acceder a los elementos individuales en la matriz mediante el uso de corteches y el indice del elemento al que queremos leer.

```javascript
let array = ["Dato1", 2, true, null];

array[1]; //2

let cuatro = array[1] + 2; //4


```

Si intentamos leer un valor en un índice que aún no se ha definido, JavaScript devuelve el valor undefined.

### Inserting elements

Nosotros podemos agregar elementos a un array en una posicion determinada. 

```javascript
// Podemos agregar un elemento en un array es una posicion especifica.

array[5] = "Dato2";// ["Dato modificado", 4, true, null, empty, "Dato 2"];

```

### Searching elements

Nosotros podemos encontrar un valor particular en el array, para hacerlo necesitamos acceder a todos los elementos del array y buscar el valor particular. Para ello utilizamos bucles, como puede ser for o  for..of.

```js
let array = [1,2,3,4];

for (let i =0; i < array.length ; i++){
	console.log(array[i]);
}

// 1, 2, 3 ,4
```

### Updating elements

Los elementos de nuestro array se pueden actualizar o modificar asignando un nuevo valor a un indice especifico.

```js
// Podemos modificar un elemento en un array ya que los elementos son mutables aunque esten declarados con const.

let array = ["Dato1", 2, true, null];

array[1] += 2 // ["Dato1", 4, true, null];

array[0] = "Dato modificado";// ["Dato modificado", 4, true, null];
```

## Arrays bidimensionales

Los arrays que tiene dentro otros arrays se denominan **bidimensionales.** Para acceder a los valores del array, tenemos que declarar los índices de cada nivel entre corchetes, uno después del otro.

```javascript
let coloresPrimarios = ["Rojo", "Azul", "Amarillo"];
let coloresBasicos = ["Blanco", "Negro"];
let coloresTotales = [coloresPrimarios, coloresBasicos]; 
coloresTotales[1][1]; // "Negro"

//let coloresTotales = [["Rojo", "Azul", "Amarillo"], ["Blanco", "Negro"]]
```
## Destructurando arrays

```javascript
let array = ["A", "B", "C", "D", "E"];

let [A, B,,, C] = array;

console.log(A)//"A"
console.log(B)//"B"
console.log(C)//"E"

//Otro ejemplo
const [A, B, ...list] = [1, 2, 3, 4, 5, 6];
console.log(A); //1
console.log(B); //2
console.log(list); //3,4,5,6

//Otro ejemplo asignandole valores predeterminados

let a, b;
[a = 5, b = 7] = [1];
console.log(a); //1
console.log(b); //7
```

## Spread Operator para arrays
Un enfoque nuevo es mantener los datos originales y entonces crear un array nuevo con los nuevos datos. Para ello se recomienda utilizar el **Spread Operator.** Al utilizar Spread Operator lo que hacemos es agregar nuevos elementos sin modificar el array original. 

```javascript
let arrayA = ["A", "B", "C"];
let arrayB = [...arrayA, "D"]; // ["A", "B", "C", "D"]

//Si yo no utilizo el spread operator lo que sucede es esto:

let arrayB = [arrayA, "D"]; //[["A", "B", "C"], "D"]
```

## Longitud de un array

Para averiguar la longitud de un array se utiliza la propiedad **length**. Esto puede ser util cuando desconocemos la longitud de nuestra matriz o mismo para arrays dinamicos. La propiedad length automáticamente se actualiza cuando se modifica el array. El indice del array es array.length - 1

```javascript
let array = ["A", "B", "C"];
array.length//3
```


**Dato**: Otra forma de ver los valores incluidos en el array, es utilizar **console.table(miarray);**

[[Objeto Array]]
