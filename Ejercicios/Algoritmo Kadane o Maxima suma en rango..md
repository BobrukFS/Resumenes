# Algoritmo Kadane o Maxima suma en rango

**Consigna**: Dada un array arr[] de tamaño N. La tarea es encontrar la suma del subarreglo contiguo dentro de un arr[] con la suma mas grande.

**Concepto**: La idea es mantener una variable "max_ending_here" que almacena la suma maxima de subarreglo contiguo que termina en el indice actual y una variable "max_so_far" que almacena la suma maxima de subarreglo contiguo encontrado hasta el momento. Cada vez que hay un valor de suma positivo en max_ending_here, se compara con max_so_far y actualiza max_so_Far si es mayor que max_so_far.

![[Pasted image 20230430095118.png]]

**Solucion**:

```js
//Solucion con dos bucles iteradores.

let A = [-2, -3, 4, -1, -2, 1, 5, -3];

function main (){
    let mayorSuma = 0;
    for(let i = 0; i < A.length; i++){ // 0(N * N ) => O(N^2)
        let sumaActual = 0;
        for( let j = i; j < A.length; j++){ // O(N)
            sumaActual += A[j];
            if(sumaActual > mayorSuma && sumaActual > 0){
                mayorSuma = sumaActual;
            }
        }
    }
    return mayorSuma;
}

//Solucion solo con un bucle iterador

let A = [-2, -3, 4, -1, -2, 1, 5, -3];

function maxRSQ(){
    let max_ending_here = 0; //Suma actual
    let max_so_far = 0; //Suma maxima
    for(let i = 0; i < A.length; i++){ // Complejidad de tiempo O(N)
        max_ending_here = max_ending_here + A[i];
        if(max_ending_here < 0){
            max_ending_here = 0;
        } else if (max_so_far < max_ending_here){
            max_so_far = max_ending_here;
        }
    }
    return max_so_far;
}

function main (){
    return maxRSQ();
}

// Observamos que podemos evitar utilizar un ciclo de mas.

//Suponiendo que la entrada N tarde 10^4 de tiempo. El algoritmo cuadratico seria O(N ^ 2) = O(10^8), es decir 1segundo. Mientras que el algoritmo lineal O(N) = (10^4), es decir medio segundo.
```

## Imprimir el subarreglo contiguo de suma mas grande

**Consigna**: Es igual al anterior solo que debemos mostrar cual es el rango, con el indice inicial y final.

**Concepto**: Manteniendo el concepto anterior, se le agregaria que deberiamos declarar 2 variables, start y end con valor 0. Start actualizara su valor a i + 1 cuando max_ending_here sea menor a 0. Mientras que end actualizara su valor a la posicion actual cuando max_so_far sea menor a max_ending_here.

**Solucion**: 

```js
let A = [-2, -3, 4, -1, -2, 1, 5, -3];

function maxRSQ(){
    let max_ending_here = 0;
    let max_so_far = 0;
    let start = 0;
    let end = 0;

    for(let i = 0; i < A.length; i++){ // Complejidad de tiempo O(N)
        max_ending_here = max_ending_here + A[i];
        if(max_ending_here < 0){
            max_ending_here = 0;
            start = i + 1;
        } else if (max_so_far < max_ending_here){
            max_so_far = max_ending_here;
            end = i;
        }
    }
    
    return `La suma maxima es ${max_so_far} y el rango (${start}, ${end})`;

}

function main (){
    return maxRSQ();
}
```

## Implementacion recursiva del algoritmo de Kadane

**Concepto**: Para determinar la suma máxima de subarreglo de un arreglo de enteros, el Algoritmo de Kadane utiliza una estrategia Divide y vencerás. El concepto fundamental de este algoritmo es dividir la matriz dada en subarreglos más pequeños, resolver recursivamente el problema para cada subarreglo y luego combinar las soluciones para encontrar la solución general.

```js

function kadaneRecursive(A, left, right) {
  if (left == right) {
    return A[left];
  }
  
  let middle = Math.floor((left + right) / 2);
  let maxLeftSum = kadaneRecursive(A, left, middle);
  let maxRightSum = kadaneRecursive(A, middle + 1, right);

  let leftBorderSum = 0, leftBorderMax = 0;
  for (let i = middle; i >= left; i--) {
    leftBorderSum += A[i];
    leftBorderMax = Math.max(leftBorderMax, leftBorderSum);
  }

  let rightBorderSum = 0, rightBorderMax = 0;
  for (let i = middle + 1; i <= right; i++) {
    rightBorderSum += A[i];
    rightBorderMax = Math.max(rightBorderMax, rightBorderSum);
  }

  return Math.max(maxLeftSum, maxRightSum, leftBorderMax + rightBorderMax);
}

// Tiene una complejidad de tiempo de O(n log n).
```
