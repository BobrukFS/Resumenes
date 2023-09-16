# Tipos de datos y expresiones

Toda expresion tiene un tipo de dato. Un **tipo de datos** es un conjunto de datos que sirven para un proposito comun. El tipo sirve para saber que dato poner en un argumento, esto se especifica en el contrato en la seccion parametros.

Tipos de datos basicos:

* Color
* Direccion
* Numero
* booleanos

Un comando acepta datos de cierto tipo y no de otro. Por ejemplo, Poner(`<color>`) es una forma de indicar que se espera un argumento de un tipo determinado, en este caso espera un color. Si pongo por ejemplo una direccion en Poner(color) va a ocurrir un **error de tipo**.

## Expresiones primitivas

Una expresion primitiva sirven para sensar el tablero y obtener informacion. Estas ya vienen predefinidas en gobstones. Por ejemplo, nroBolitas(`<color>`) describe la cantidad de bolitas de un determinado color que hay en una celda determinada en el momento actual y retorna un numero.

Las expresiones empiezan en minuscula como los parametros salvo las expresiones literales que son aquellas que representan al dato directamente, como Negro, Azul.

## Operadores

Un operador es una expresion que permiten hacer transformaciones de informacion.
### Operadores numericos

Los operadores numericos es un operador numerico, es decir que actua sobre dos operandos. Sirven para hacer cuentas con cualquier numero.

* +
* -
* *
* ^
* div: En gobstone se divide en enteros, si divido 20 por 3, me da 6.
* mod

**Dato**: Podemos utilizar los parentesis que ayudan a desambiguar.

### Operador de enumeracion

Los operadores de enumeracion permiten calcular nuevos valores en base a uno dado.

* opuesto(`<Direccion>`): Es un operador unario
* siguiente(`<Direccion>`)
* previo(`<Direccion>`)

![[Pasted image 20230910114306.png]]


Decimos que un **operador esta sobrecargado** cuando con el mismo nombre hablamos de dos operadores distintos.

Por ejemplo, previo y siguiente estan sobre cargados ya que se puede utilizar tambien para colores y numeros.

* siguiente(`<color>`)
* previo(`<color>`)
* siguiente(`<numero>`)
* previo(`<numero>`)

![[Pasted image 20230910114412.png]]

Sin embargo, para los numeros existe una alternativa, que es utilizar los operadore numericos

![[Pasted image 20230910114525.png]]
### Operadores de comparacion

Estos operadores comparan dos valores y dan como resultado una operacion booleana.

![[Pasted image 20230910153721.png]]
![[Pasted image 20230910153731.png]]

No solo funcionan con numeros, tambien con colores y direcciones

![[Pasted image 20230910153813.png]]
![[Pasted image 20230910153826.png]]

### Operador negacion

El operador negacion **not** es un operador binario que da como resultado el valor booleano expuesto al valor que se le aplique.

Por ejemplo, not hayBolitas(rojo);

### Operadores logicos

* conjuncion: **&&**
* disyuncion: **||**