# Listas / arrays en gobstones

Una **lista** es un dato con estructura, la lista esta compuesto por otros datos del mismo tipo. Se pueden hacer recorridos sobre los elementos de una lista.

**¿Que operaciones puedo hacer con el dato lista?**

* ¿Cuántos elementos hay en la lista?
* ¿Cuál es el primer elemento? 
* ¿Cuál es el último elemento? 
* ¿Cuál es el elemento más grande? 
* ¿Cuál es el elemento más chico?

Para construir listas de forma literal enumeramos sus elementos entre corchetes, y deben ser todas del mismo tipo.

```gbs
[<exp1>, <exp2>, ... , <expN>]//lista con n elementos
[]//lista vacia
```

El tipo de una lista es el tipo de sus elementos.

Otra forma de construir listas es juntando dos existentes, para eso se usa el operador para agregar **(append)**. El resultado es una lista que tiene los elementos de ambas, en el mismo orden, es una operacion asociativa.

```gbs
//Ejemplo 1
segundaMitad(mazo) ++ primeraMitad(mazo);
//Ejemplo 2
[1, 2, 3, 4] ++ [5, 6, 7] // [1, 2, 3, 4 ,5 ,6 , 7]
```

Combinando listas literales y append se pueden construir otras operaciones interesantes, por ejemplo:

```gbs
//Agregar elemento adelante de la lista

function cons(elemento,lista){
	 /* PROPÓSITO: Describir la lista resultante de agregar el elemento dado al principio de la lista dada.     
	 PRECONDICIONES: Ninguna.     
	 PARÁMETROS: * elemento: Un tipo cualquiera.     
	 * lista: Una lista de elementosdel mismo tipo que **elemento**.     
	 * TIPO: El mismo que **lista**.
	 */
	return ([elemento] ++ lista)
}

//Agregar elemento atras de la lista

function snoc(lista, elemento){
	/* PROPÓSITO: Describir la lista resultante de agregar el elemento dado al final de la lista dada.     
	PRECONDICIONES: Ninguna.     
	PARÁMETROS: * lista: Una lista de cualquier tipo.     
	* elemento: Del tipo de los elementos de **lista**.     
	* TIPO: El mismo que **lista**.  
	*/
	return (lista ++ [elemento])
}

//Dado dos valores, devuelva la secuencia entre ellos

function secuenciaAritméticaDeNúmerosDe_A_(valorInicial, valorFinal) {  
	/* PROPÓSITO: Describir la lista que contiene a todos los números entre **valorInicial** y **valorFinal**, inclusive, en orden.     
	PRECONDICONES: Ninguna     
	PARÁMETROS: * valorInicial: Número.     
	* valorFinal: Número.     
	TIPO: [Número].     
	OBSERVACIÓN: Si **valorFinal** es menor a **valorInicial** describe a la lista vacía.  
	*/  
	próximoNúmero := valorInicial  
	listaHastaAhora := []  
	repeat (valorFinal - valorInicial + 1) {    
		listaHastaAhora := listaHastaAhora ++ [ próximoNúmero ]    
		próximoNúmero := próximoNúmero + 1  
	}  
	return (listaHastaAhora) 
}

secuenciaAritméticaDeNúmerosDe_A_(40,45) //[40,41,42,43,44,45]

//Dada una cantidad y un elemento, describe una lista con esa cantidad del elemento.

function enTotal_IgualesA_(cantidad, elemento) {  
	/* PROPÓSITO: Describir la lista con **cantidad** elementos iguales a **elemento**.     PRECONDICONES: Ninguna.     
	PARÁMETROS:* cantidad: Número.     
	* elemento: Un tipo cualquiera.     
	* TIPO: Una lista de elementos del mismo tipo que **elemento**.     
	* OBSERVACIÓN: Si **cantidad** es menor a 0 describe a la lista vacía.  
	* */  
	
	listaHastaAhora := []  
	repeat (cantidad) {    
		listaHastaAhora := [ elemento ] ++ listaHastaAhora  
	}  
	return (listaHastaAhora) 
}

Ejemplo: enTotal_IgualesA_(5, Norte)//[Norte, Norte, Norte, Norte, Norte]

enTotal_IgualesA_(5, Norte) ++ enTotal_IgualesA_(4, Este)
//[Norte, Norte, Norte, Norte, Norte, Este, Este, Este, Este]

//Describe la fila actual del tablero como una lista de celdas.

function filaActual() {  
	/* PROPÓSITO: Describir la fila actual del tablero como una lista de celdas.
	 PRECONDICONES: Ninguna.     
	 TIPO: [Celda]  
	*/  
	
	filaProcesada := []  
	IrAlBorde(Oeste)  
	while (puedeMover(Este)) {    
		filaProcesada := filaProcesada ++ [ celdaActual() ] //Se agrega al final para que el orden sea el mismo que en el que fueron recorridas  
		Mover(Este)  
	}  
	return (filaProcesada ++ [ celdaActual() ]) 
}

//Describir el tablero como una lista de listas de celdas.

function tableroActual() {  
	/* PROPÓSITO: Describir el tablero como una lista de listas de celdas.
	  PRECONDICONES: Ninguna.     
	  TIPO: [[Celda]]  
	*/  
	tableroProcesado := []  
	IrAlBorde(Norte)  
	while (puedeMover(Sur)) {    
		tableroProcesado := tableroProcesado ++ [ filaActual() ]    
		Mover(Sur)  
	} 
	return (tableroProcesado ++ [ filaActual() ]) 
}
```

Algunas primitivas:

```gobstones
//Describe el primer elemento de la lista dada. La lista dada no es vacia.
- primero(lista)

//Describir una lista con los elementos de la lista dada, excepto que sin el primero de ellos. La lista dada no es vacia. El argumento de resto debe ser una lista, no puede ser resto(primero([10,20])), si puede ser al revez primero(resto([10,20])). Puede ser 
resto(resto(lista))
-resto(lista)

//Indicar si la lista esta vacia. Ninguna precondicion.
-esVacia(lista)
```

Las secuencias aritmeticas pueden ser de otros tipos. Para tipos básicos, Gobstones provee notación especial:

`[ <expValorInicial> .. <expValorFinal> ]`
![[Pasted image 20231023213719.png]]
`[ <expInicial>, <expSegundo> .. <expFinal> ]`
![[Pasted image 20231023213732.png]]

## Procesamiento de listas

Ejemplo: Contar la cantidad de elementos que hay en determinada lista

```gobstones
function cantidadDeElementosEn_(lista){
 /* PROPÓSITO: Describir la cantidad de elementos en la       lista dada.     PRECONDICONES: Ninguna.     PARÁMETROS:     * lista: Una lista de cualquier tipo.     TIPO: Número.     OBSERVACIÓN: Es un recorrido sobre la lista dada.  
 */
	listaRestante := lista
	cantidadContada = 0
	while(not esVacia(listaRestante)){
		cantidadContada = cantidadContada + 1
		listaRestante := resto(listaRestante)
	}
	return (cantidadContada)
}
```

Ejemplo: Encontrar el minimo elemento

```gbs
function minimoElementoDe_(lista){

 /* PROPÓSITO: Describir el menor elemento de la lista dada.     
 PRECONDICONES: La lista dada no es vacía.     
 PARÁMETROS:     * lista: Una lista de cualquier tipo básico.     TIPO: El de los elementos de la lista dada.     
 OBSERVACIÓN: Es un recorrido sobre la lista dada.  
 */
 
	listaRestante := lista
	minimoElemento := primero(lista)
	while(not esVacio(listaRestante)){
		minimoElemento := minimoEntre_y_(minimoElemento, primero(listaRestante))
		listaRestante := resto(listaRestante)
	}
	return (minimoElemento)
}

function mínimoEntre_y_(elemento1, elemento2) {  
/* PROPÓSITO: Describir el mínimo entre los dos elementos dados. Si son iguales, describe cualquiera de ellos.     
PRECONDICIONES: Ninguna.     
PARÁMETROS:  * elemento1: De un tipo básico cualquiera.     
* elemento2: Del mismo tipo que **elemento1**.     
* TIPO: El mismo que **elemento1**.  */  
return (choose elemento1 when (elemento1 < elemento2)                 
               elemento2 otherwise // (elemento1 >= elemento2)
        ) 
}
```

Ejemplo: Transformar una lista, se recorre y en cada paso, se transforma el actual y se lo agrega al resultado

```gbs
function numerosDeLasCartasDe_(mazo){
	 /* PROPÓSITO: Describir la lista de números de las       cartas del mazo dado.     PRECONDICIONES: Ninguna.     
PARÁMETROS: * mazo: [Carta].     
TIPO: [Número].    
OBSERVACIÓN: Es un recorrido de transformación sobre el mazo dado (una lista).
	 */
mazoRestante := mazo
listaTransformada := []

while(not esVacio(mazoRestante)){
	listaTransformada ++ [numero(primero(mazoRestante))]
	mazoRestante := resto(mazoRestante)
}
return (listaTransformada)
}
```

Ejemplo: Eliminar elementos que no queremos, se recorre y en cada paso, se decide si el elemento actual se deja o se quita.

```gobstones
function soloLosOrosDe_(mazo) {  
/* PROPÓSITO: Describir la lista de cartas del mazo dado que son de Oros.     PRECONDICIONES: Ninguna.     
PARÁMETROS: * mazo: [Carta].     
TIPO: [Carta].     
OBSERVACIÓN: Es un recorrido de filtrado sobre el mazo dado (una lista).  
*/  

mazoRestante := mazo
mazoDeOrosVistos := []

while(not esVacia(mazoRestante)){
	mazoDeOrosVistos := mazoDeOrosVistos ++ singular_si_(primero(mazoRestante), esDeOros_(primero(mazoRestante)))
	mazoRestante := resto(mazoRestante)
}
return (mazoDeOrosVistos)

}

function singular_Si_(elemento, condición) {  
/* PROPÓSITO: Describir una lista según el valor de la condición dada. Si es verdadera, describe la lista singular con **elemento**. Si no, describe la lista vacía.     PRECONDICIONES: Ninguna.     
PARÁMETROS: * elemento: De un tipo cualquiera.     
* condición: Booleano.     
TIPO: Lista del tipo de **elemento**.  
*/  
return (choose [elemento] when (condición)                
               []         otherwise) 
}

```

Ejemplo: Buscar un elemento. Se recorre, y si encuentra lo buscado, termina

```gobstones
function estáElAnchoDeEspadasEn_(mazo) {  
/* PROPÓSITO: Indicar si el mazo dado contiene algún ancho de Espadas.     PRECONDICIONES: Ninguna.     
PARÁMETROS:  * mazo: [Carta].     
TIPO: Booleano.     
OBSERVACIÓN: Es un recorrido de búsqueda sobre el mazo dado (una lista).  
*/  

mazoRestante := mazo
while(not esVacia(mazoRestante) && not esAnchoDeEspadas_(primero(MazoRestante))){
	
	mazoRestante := resto(mazoRestante)
}
return (not esVacia(mazoRestante))
}
```
### Procesamiento modularizado

Ejemplo: Si quiero eliminar una carta. Por ejemplo, dar el mazo sin el ancho de espadas.

```gbs
function sinElAnchoDeEspadas_(mazo) {  
/* PROPÓSITO: Describir al mazo resultante de quitar el ancho de Espadas del mazo dado. PRECONDICIONES: El mazo dado contiene a lo sumo UN ancho de Espadas.     
PARÁMETROS: * mazo: [Carta].     
TIPO: [Carta].     
OBSERVACIÓN: Usa la idea de separar la lista en dos partes.  
*/  
return ([cartasAntesDelAnchoDeEspadasEn_] ++ [cartasDesdeElAnchoDeEspadasEn_] )

}


function cartasAntesDelAnchoDeEspadasEn_(mazo) {  
/* PROPÓSITO: Describir la lista con las cartas del mazo dado que están antes del ancho de Espadas.     
PRECONDICIONES: Ninguna.     
PARÁMETROS: * mazo: [Carta].
TIPO: [Carta].     
OBSERVACIÓN: Es un recorrido de búsqueda con acumulación sobre el mazo dado.  
*/ 

mazoRestante := mazo  
	while (not esVacía(mazoRestante) && not esAnchoDeEspadas_(primero(mazoRestante))) { 
		mazoRestante := resto(mazoRestante)  
	}  
return (mazoRestante)
} 

function cartasDesdeElAnchoDeEspadasEn_(mazo) {  
/* PROPÓSITO: Describir la lista con las cartas del mazo dado que están a partir del ancho de Espadas.     
PRECONDICIONES: Ninguna.     
PARÁMETROS: * mazo: [Carta].     
TIPO: [Carta].     
OBSERVACIÓN: Es un recorrido de búsqueda sobre el mazo dado.  
*/  

 mazoRestante := mazo  
 cartasVistas := []  
 while (not esVacía(mazoRestante) && not esAnchoDeEspadas_(primero(mazoRestante))      ) {    
 cartasVistas := cartasVistas ++ [ primero(mazoRestante) ]   
 mazoRestante := resto(mazoRestante)  
 }  
 return (cartasVistas) 
}

```

**Dato**: Las listas serian como arrays, a los cuales se los puede recorrer.
### Foreach

La repetición indexada usa la palabra clave foreach.

![[Pasted image 20231120001444.png]]
Ejemplos:

```gobstones
//Ejemplo 1
function montoAPagarPor_Indexada(carritoDeCompras) {  
montoHastaAhora := 0  
foreach producto in carritoDeCompras {    
	montoHastaAhora := montoHastaAhora + precio(producto)  
	}  
return (montoHastaAhora) 
}
//Ejemplo 2
Poner(Verde)
foreach dir in (con_veces_(3, Norte) ++ con_veces_(2,Este) ++ [sur]){
	Mover(dir)
	Poner(verde)
}
```

**Dato**: Foreach in seria como un for in en JS

**Dato**: La repetición indexada sirve para recorrer listas (pero NO recorridos de búsqueda)

