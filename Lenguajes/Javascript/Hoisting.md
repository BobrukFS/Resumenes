# Hoisting
## Hoisting en variables
Las variables declaradas con la palabra clave **var** son asignadas en memoria durante la fase de creacion y se inicializan con un valor undefined, al ya estar declaradas en memoria desde la fase de creacion, podemos acceder a ellas desde antes de la linea de codigo donde se inicializo (asigno un valor) y por consola podriamos ver el valor que tiene en ese momento (undefined), y cuando llegan a la linea de codigo donde se inicializo solamente se actualiza el valor en su entorno lexico, esto es lo que se llama variable hoisting.

```javascript
function hoisting(){
  console.log(variableHoisting);// undefined
  var variableHoisting = "Tiene un valor en este entorno";
  console.log(variableHoisting); // "Tiene un valor en este entorno"
}

hoisting();
```

### Temporal dead zone
Ademas de var, se eleva **let** y **const** a la **Temporal dead zone.** Esta es una  region de nuestro codigo donde una variable no se puede acceder porque la ejecucion del programa todavia no paso por la linea de codigo donde es declarada. Si declaramos una variable con let o const y queremos acceder a dicha variable antes de su declaracion, cuando JS intente ejecutar esa linea de codigo veremos un error en la consola, haciendo mas facil que veamos los errores que cometemos.  Se encuentran en el scope, pero no han sido declaradas todavía, estas salen de la temporal dead zone cuando son declaradas. Esta caracteristica permite crear variables con alcance de bloque.

**Dato** let y const son **block-scoped** que significa que solo son accesibles dentro de las llaves {} que les rodean.

## Hoisting en funciones
Las funciones durante la fase de creacion del contexto de ejecucion se colocan por completo en memoria. Esto es lo que se llama function hoisting.

```javascript
hoisting(); //Se ejecuta

function hoisting(){
  console.log(variableHoisting);// undefined
  var variableHoisting = "Tiene un valor en este entorno";
  console.log(variableHoisting); // "Tiene un valor en este entorno"
}


```

Si escribimos la funcion como una expresion en lugar de una declaracion, lo que se va a elevar es su declaracion, y cuando se eleve obtendremos un error porque tiene el valor undefined.

```javascript
hoisting();//TypeError: hoisting is not a function

var  hoisting = function(){
  console.log(variableHoisting);
  var variableHoisting = "Tiene un valor en este entorno";
  console.log(variableHoisting);
}



```

**Dato:** En las clases no funciona este comportamiento,  las clases solo podemos usarlas despues de haberlas declarado.