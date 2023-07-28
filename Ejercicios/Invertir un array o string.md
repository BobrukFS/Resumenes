# Invertir un array o string

**Consigna:** Dado un array o una cadena la tarea es invertirla.

**Example** :

```js
//Ejemplo 1

Entrada: arr[] = {1, 2, 3}
Salida: arr[] = {3, 2, 1}

//Ejemplo2

Entrada: arr[] = {4, 5, 1, 2}
Salida: arr[] = {2, 1, 5, 4}

```

**Concepto** : El concepto principal a mi parecer es que debemos observar que el primer elemento del array va a ser el ultimo, mientras que el ultimo elemento del array sera el primero. Lo mismo se aplica para el segundo elemento y el ante ultimo elemento del array, y para todos los demas elementos siguiendo la logica.

![[Pasted image 20230428214307.png]]
![[Pasted image 20230428214338.png]]
**Solucion** : Podemos llegar a una solucion utilizando la iteracion o la recursion:

```js

let array1 = [1, 2, 3, 4, 5, 6];

//Utilizando la iteracion
function reverseArray (array, start, end){
	while(start < end){ //Mientras start sea menor que end, se sigue ejecutando
	let helper = array[start]; //Es una ayuda ya que necesitamos guardar el valor del elemento start, porque al asignar array[start] = array[end], perdemos el valor array[start].
	array[start] = array[end]; // El elemento start del array sera igual al end
	array[end] = helper; //El elemento end del array sera igual a start.
	start++ //Sirve para ir iterando hacia adelante el array
	end-- //Sirve para ir iterando hacia atras el array
		}
		return array;
}

console.log(reverseArray(array1, 0, array1.length - 1)); //[6, 5, 4, 3, 2, 1];

//Utilizando la recursividad

function reverseArray(array, start, end){
	let helper = array[start];
	array[start] = array[end];
	array[end] = helper;
	if (start + 1 < end - 1){
		reverseArray(array, start + 1, end - 1);
	}
	return array
}

// Podemos ver que al utilizar recursividad lo que estamos haciendo al asignar un if, es que si start + 1 es menor que end - 1, podemos volver a llamar la funcion, actualizando start y end, pero en todo los demas aspectos cumple con el mismo concepto.
```

Ambas soluciones tienen una complejidad de tiempo: O(n);