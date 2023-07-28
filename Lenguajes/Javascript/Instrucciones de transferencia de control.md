# Instrucciones de transferencia de control
Son instrucciones que permiten detener la ejecución de bucles y condicionales:

- **Continue**: La instrucción **continue** termina la ejecución de las sentencias de la iteración actual del bucle actual o la etiqueta y continua la ejecución del bucle con la próxima iteración.

```javascript
let contador = 0

for(let i = 0; i < 10; i++){
	contador += 5 
	if (contador == 40){
	    continue;
	  }
}

//5, false
//10, false
//15, false
//20,false
//25,false
//30,false
//35,false
//40, true, continue
//45, false
//50, false
console.log(contador);//50
```

```javascript 
let contador = 0

for(let i = 0; i < 10; i++){
    
  if (contador == 40){
    continue;
  }
  contador += 5
}

//5, false
//10, false
//15, false
//20,false
//25,false
//30,false
//35,false
//40, true, continue
//40, true, continue
//40, true, continue
console.log(contador);//40
```

```javascript
let listaprecios1 = [2, 4, 6, 100 , 10];

let preciototal1 = 0;

for(let p = 0; p < listaprecios1.length; p++ ){

	let precioalto = listaprecios1[p];

	if (precioalto == 100){
	    continue;
	}
	preciototal1 += listaprecios1[p];
}
console.log(preciototal1);//22
```

- **Break**: La instrucción **break** interrumpe el bucle completamente, delegando el control a la instrucción declarada después del bucle.

```javascript

let contador = 0
while(contador < 15){
    contador++;
    console.log(contador)
    if(contador == 12){
        break;
    }
}

console.log("Instruccion despues del bucle")

//1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12
//Instruccion despues del bucle

```

- **Label(etiqueta)**: Podemos usar una etiqueta para identificar un bucle mediante la sintaxis `nombre etiqueta:`. Entonces nosotros podemos utilizar break etiqueta; o continue etiqueta;.  Una etiqueta es la única forma de usar break/continue para escapar de un bucle anidado e ir a uno exterior. 

```javascript
let array1 = ["maria", "josefa", "roberta"];

let array2 = ["pedro", "marcelo", array1, "josefina"];// [pedro, marcelo, [maria, josefa, roberta], josefina]

forTerminar:
for (let array in array2) { //Se itera array2

  if (array == 2) { //Si array es igual a 2. Es decir si el indice de array2 es 2 se ejecutara:
    for (let array of array1) { //Se itera array1
      if (array == "maria") { //Si array es igual a maria
        continue forTerminar; //Que pasaria si?
      }
      document.write(array + "<br>");
    }
  } else {
    document.write(array2[array] + "<br>"); //Si el indice del array2 no es 2, se escribe. "Pedro", "Marcelo" y "Josefina"
  }
}

//Que pasaria si? Si pongo continue forTerminar, lo que sucederia es que al encontrarse "Maria" se ira a la proxima iteracion, es decir el index 3. "Pedro", "Marcelo" y "Josefina"

//Que pasaria si? Si pongo break forTerminar, lo que sucederia es que el encontrarse "Maria" se ira a la proxima instruccion fuera del bucle. "Pedro", "Marcelo"

//Que pasaria si? Si no pongo nada, lo que sucederia es: "Pedro", "Marcelo", "Maria","Josefa","Roberta","Josefina"
```