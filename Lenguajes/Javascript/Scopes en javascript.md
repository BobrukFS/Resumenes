# [[Scope]] o ambito lexico en javascript

El **alcance lexico o ambito lexico** se refiere al area donde una funcion o variable es visible y accesible para otro codigo. En otras palabras, determina dónde una variable o función se puede referenciar y utilizar en un programa. 

El entorno léxico se determina una vez y luego se fija durante todo el curso del programa. Esta es la razón por la que JavaScript se denomina lenguaje de alcance estático: los lugares donde los nombres dados (de variables y funciones) son accesibles en un programa son estáticos (es decir, no cambian) y se rigen por el código fuente.

El **contexto de ejecución** se refiere a la configuración y estado en el que se ejecuta un programa o una función en un determinado momento. Incluye información sobre variables, sus valores, funciones llamadas y otros datos relevantes necesarios para seguir la ejecución del programa en un momento dado. Cada vez que se invoca una función, se crea un nuevo contexto de ejecución que contiene variables locales y parámetros específicos de esa llamada. En resumen, el contexto de ejecución es el entorno temporal que se crea durante la ejecución de un programa y contiene información sobre las variables y funciones en ese momento, mientras que el ámbito léxico determina la visibilidad y accesibilidad de las variables y funciones en diferentes partes del código en tiempo de diseño.

JS habilita tres ambitos para la declaracion de una variable: Ambito global, ambito local y ambito de funcion.

- **Ambito global**: Cuando se declara una variable fuera de una funcion o bloque, se le denomina **variable global** porque **esta disponible para cualquier parte del codigo**. Las variables globales son accesibles desde cualquier funcion a menos que se le superpongan variables locales con el mismo nombre. Estas variables estaran en memoria durante toda la ejecucion del programa.

```javascript
let variableGlobal = "Soy variable global";


function llamarGlobal(){
	console.log(variableGlobal);
}

llamarGlobal();//"Soy variable global"
```

- **Ambito local (scope de bloque o de funcion)**: Cuando se declara una variable dentro de una funcion o bloque (es todo codigo que este encerrado entre llaves), se le denomina **variable local** ya que no podemos acceder a esta variable fuera de esta funcion o bloque. Estas variables estaran en memoria durante la ejecucion de un bloque o una funcion. En un ámbito léxico local, las variables declaradas dentro de una función pueden acceder a las variables declaradas en su función contenedora (cuando hay una función anidada). Esto se debe a que las funciones anidadas pueden acceder a las variables de su función contenedora, pero no viceversa.

**Dato:** Un **bloque de Código** es un conjunto de instrucciones que se agrupan de forma secuencial entre llaves.

```javascript
let variableGlobal = "Soy variable global";


function llamar(){
	let variableLocal = "Soy una variable local"
	console.log(variableGlobal);
	console.log(variableLocal);
}

llamar();//"Soy variable global" "Soy una variable local"
console.log(variableLocal); //ReferenceError: variableLocal is not defined
```

Debido a que las variables declaradas en diferentes ámbitos se consideran diferentes variables, dos variables con el mismo nombre, una en el ámbito global y otra en el ámbito local (dentro de una función), se considerarán dos variables distintas (se les asigna un espacio de memoria diferente). La variable local tiene precedencia sobre la variable global.

```javascript
let variable = "Soy variable global";


function llamar(){
	let variable = "Soy una variable local"
	console.log(variable);
}

llamar();//"Soy una variable local" "undefined"
console.log(variable);//"Soy una variable global"
```

**Dato**: En el navegador podemos ver el entorno lexico de una funcion viendo el atributo `[[Scope]]`
## ¿Como funciona?

Cuando asignamos un nuevo valor a una variable, esa actualizacion se realiza en el entorno lexico (contexto de ejecucion) de esa variable. Los objetos, las funciones y los arrays se guardan como referencia a las posiciones de memoria en donde realmente se encuentran. Dentro del entorno lexico, los nombres de las variables (claves) son unicas. 
Cada entorno lexico tiene un puntero a su entorno lexico exterior, el entorno donde este fue creado. Debido a esto nosotros podemos buscar variables en el entorno lexico actual, o en el entorno lexico exterior pero nunca viceversa.

![[Pasted image 20221006164121.png]]

### Contexto de ejecucion global

En la **fase de creacion**, se **crea nuestro objeto global y this**(apunta al objeto window), **nuestras variables se declaran en la memoria de la computadora y el motor de JS le asigna un valor undefined**(empty value) mientras que las funciones se colocan directamente en la memoria.

En la **fase de ejecucion** se comienza a **ejecutar linea por linea** (asi ejecuta el motor de js), cuando llega a la linea donde estan nuestras variables, **las variables dejan de ser undefined y se le asigna un valor**.

```javascript
let variable1 = 5;
let variable2 = 10;

function sumar(num1, num2){
	return num1 +  num2;
}
```

![[Pasted image 20221006163837.png]]
![[Pasted image 20221006163929.png]]

### Contexto de ejecución de funcion

Si una funcion se define en el ambito global, su entorno lexico es simplemente el entorno global, mientras que si se crea en una funcion, su entorno lexico es el de la funcion en el que se creo.

Cada vez que se invoca una funcion se crea el contexto de ejecucion de la funcion. Cuando se invoca una funcion y se crea un contexto de ejecucion de funcion no se crea el objeto global si no el objeto **arguments**, que posee los argumentos pasados a la función, el resto funciona igual que en el contexto de ejecucion global.

```javascript
function funcion1(){
    let variableGlobal2 = 20;
    let variableLocal = 12;
  function funcion2(num1,num2){
    return num1 + num2;
  }
}

funcion1();
```

![[Pasted image 20221006165615.png]]
![[Pasted image 20221006165641.png]]
![[Pasted image 20221006165650.png]]
![[Pasted image 20221006165838.png]]
Cada vez que se ejecuta una funcion en javascript se crea un nuevo contexto de ejecucion con un nuevo entorno lexico.

