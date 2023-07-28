# Problema de la bandera nacional holandesa

**Consigna**: Dado un array A[] que consta de solo 0, 1 y 2. La tarea es escribir una funcion que ordene el array dado. Las funciones deben poner todos los 0 primero, luego todos los 1 y todos los 2 al final.

Dadas N bolas de color rojo, blanco o azul dispuestas en una línea en orden aleatorio. Tienes que colocar todas las bolas de modo que las bolas con los mismos colores estén adyacentes en el orden de las bolas, siendo el orden de los colores rojo, blanco y azul (es decir, todas las bolas de color rojo vienen primero y luego las bolas de color blanco). y luego las bolas de color azul).

**Examples**: 

```js
Entrada : {0, 1, 2, 0, 1, 2}  
Salida : {0, 0, 1, 1, 2, 2}

Entrada : {0, 1, 1, 0, 1, 2, 1, 2, 0, 0, 0, 1} 
Salida: {0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 2, 2}
```

## Ordenar utilizando el enfoque de puntero

**Concepto**: Se trata de tener un puntero que podemos llamar "mid" que lo inicializamos con un valor 0. Tambien vamos a tener una variable "low" que se inicializa con un valor 0. Ademas tendremos una variable "hight" que se inicializa con el valor del indice final (array.length - 1).

![[Pasted image 20230430212730.png]]

En primer lugar vamos a tener un bucle while que se va ejecutar mientras mid sea menor o igual a hight. En segundo lugar vamos a tener un switch que compara array[mid] con 0, 1 y 2. En caso de que coincida con 0, lo que debe suceder es intercambiar el lugar del valor que apunta el puntero mid, con el puntero low, ademas de aumentar en 1 tanto la variable low como mid. En caso de que coincida con 1, lo que sucede es aumentar en 1 la variable mid. En caso de que coincida con 2, lo que debe suceder es intercambiar el lugar del valor que apunta el puntero mid, con el puntero higth, ademas de decrementar en 1 la variable higth.

**Solucion**:

```js
let A = [0, 1, 1, 0, 1, 2, 1, 2, 0, 0, 0, 1];

function holanda(array) {
    let low = 0;
    let mid = 0;
    let hight = array.length - 1;
    
    while (mid <= hight) {
        let midVal = array[mid];
        switch (array[mid]) {
            case 0:
                array[mid] = array[low];
                array[low] = midVal;
                low++;
                mid++;
                break;
            case 1: 
	            mid++;
                break;
            case 2:
                array[mid] = array[hight];
                array[hight] = midVal;
                hight--;
                break;
        }
    }
    return array;
}

//Complejidad de tiempo: O(n), solo se necesita un recorrido al array.
//Complejidad espacial: 0(1), no se requiere espacio adicional.
```

## Ordenar una matriz utilizando el enfoque de conteo

**Concepto**: En este concepto lo que hacemos es inicializar los contadores de 0, 1, 2 e indice con 0. Luego mediante un bucle vamos contabilizando la cantidad de ceros, unos y dos. Luego con bucles while lo que hacemos es ir agregando al array mientras va aumentando el index los ceros, unos y dos en orden.

**Solucion**: 

```js
let A = [0, 1, 1, 0, 1, 2, 1, 2, 0, 0, 0, 1];

function holanda(array) {
    let cnt0 = 0;
    let cnt1 = 0;
    let cnt2 = 0;
    let index = 0;

    for(let i = 0; i < array.length; i++){
        if(array[i] === 0){
            cnt0++;
        }else if (array[i] === 1){
            cnt1++;
        } else {
            cnt2++
        }
    }

    while(cnt0 > 0){
        array[index++] = 0;
        cnt0--;
    }

    while(cnt1 > 0){
        array[index++] = 1;
        cnt1--;
    }

    while(cnt2 > 0){
        array[index++] = 2;
        cnt2--;
    }
    return array;
}

//Complejidad de tiempo: O(n), solo se necesitan iteraciones no anidadas del array.
//Complejidad espacial: O(1).

```
