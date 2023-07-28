# Conversion y coercion de tipos de datos

La **coercion de tipos** es la conversion automatica o implicita de valores de un tipo de datos a otro. La **conversion de tipos** es similar a la coercion de tipos porque convierten valores de un tipo de datos a otro con una diferencia clave: la coercion de tipos es implicita. Por el contrario, la conversion de tipos puede ser implicita o explicita.

## Implicita(Coercion)

La conversión de un tipo de valor de datos a otro tipo de forma implicita se denomina **coercion**. Si es necesario, el motor de JavaScript convierte automáticamente un tipo de valor en otro tipo que sea correcto para realizar determinada operacion.  Por ejemplo alert() convierte automaticamente cualquier valor a string para mostrarlo.

Podemos ver el ejemplo a continuación:

```js
var numero = 10; // número entero 
var decimal = 3.14; // número decimal 
var resultado = numero + decimal; // La coerción de tipo convierte 'numero' a decimal 
console.log(resultado); // El resultado es 13.14, un número decimal
```

El motor de javascript convierte automaticamente en caso de ser necesario a string, numeros o boleano.

* **A string**: La conversion a string ocurre cuando necesitamos la representacio en forma de texto de un valor. La conversion a string es bastante obvia. Por ejemplo el boolean false se convierte en "false", null en "null", etc.

* **A number**: La conversion numerica ocurre automaticamente en funciones matematicas y expresiones.

![[Pasted image 20221005020520.png]]

Casi todas las operaciones matemáticas convierten valores a números. Una excepción notable es la suma `+`. Si uno de los valores sumados es un string, el otro valor es convertido a string.

* **A boleano**: Ocurre en operaciones lógicas (más adelante veremos test condicionales y otras cosas similares).

![[Pasted image 20221005020502.png]]


## Explicita

La conversion de tipo explicito la realizamos nosotros utilizando funciones de Javascript. La conversion se llama **typecasting**.

* **Number(value)**: Convierte un valor a un numero. Si el valor no se puede convertir a un numero valido, devuelve NaN.

* **Boolean(value)**: Convierte un valor a un boleeano.

* **String(value)**: Convierte un valor a una cadena de caracteres.

* **toString(value)**: Convierte un valor a una cadena de caracteres invocando el metodo toString() del objeto.

* **parseInt(value)**: Convierte una cadena de caracteres o un numero decimal a un numero entero. Si la cadena de caracteres no comienza con un número válido, devuelve NaN.

* **parseFloat(value)**: Convierte una cadena de caracteres o numero entero a un número de punto flotante (decimal). Si la cadena de caracteres no comienza con un número válido, devuelve NaN. 








