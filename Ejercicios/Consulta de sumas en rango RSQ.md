# Consulta de sumas en rango (RSQ)

**Consigna**: Dado un array, debemos realizar consultas donde nos daran un indice inicial y un indice final, donde debemos realizar la suma.

**Solucion**: 

```js
//Primero lo podriamos pensar hacer con un bucle

let A = [10, 6, 8, -3, 2, 7, 2, 1, 3, 2, 7, 9, -2, 1];

function sumar(ini, end){
	let suma = 0;
	while (ini < end){ // Complejidad de tiempo O(N) Estamos iterando sobre los elementos del array que pueden ser N elementos.
		suma += A[ini]
		ini++;
	}
	return suma;
}

function consultas (consultas, ini, end){
	while (consultas > 0){ // Complejidad de tiempo O(N * Consultas)
		sumar(ini, end);
		consultas--;
	}
}

console.log(consultas(10, 0, 2)) // 10 veces nos dara 16;

//Forma optimizada, podemos crear un arrays con el acumulado de la suma del indice actual y el anterior.

let S = []; Array con las sumas acumuladas

function sumar(ini, end){
	if(ini == 0){
		return S[end];
	} else {
		return S[end] - S[ini - 1]
	}
}

function consultas (consultas, ini, end){
	S[0] = A[0];
	for(let i = 1; i < A.length; i++){
		S[i] = S[i - 1] + A[i];
	}
	
	while (consultas > 0){ // Complejidad de tiempo O(Consultas * 1)
		sumar(ini, end);
		consultas--;
	}
}

//Podemos ver en que tenemos menor cantidad de tiempo de la segunda forma, ya que la function sumar no esta iterando sobre un array, si no que esta seleccionando un elemento del array, por lo que tiene complejidad O(1).


```