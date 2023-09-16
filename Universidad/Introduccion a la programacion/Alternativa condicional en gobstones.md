# Alternativa condicional en gobstones

La **alternativa condicional** es un nuevo comando que nos permite tomas decisiones ante determinada situaciones.  

Para construirla se empieza con **if** seguido de la **condicion (La condicion debe ser una expresion booleana (verdadero o falso) entre parentesis** luego viene **then** que viene seguida del bloque del codigo que se ejecutara si la condicion es verdadera. La palabra clave then es optativa. Luego viene la palabra clave **else** seguida del bloque del codigo que se ejecutara si la condicion es falsa, else es opcional, en el caso que no se tenga que hacer nada si la condicion es falsa lo podemos omitir

```gobstones
if(condicion) then{
	//codigo a ejecutarse si la condicion es verdadera
} else{
	//codigo a ejecutarse si la condicion es falsa
}

//Otra opcion

if(condicion){
	//codigo a ejecutarse si la condicion es verdadera
}else{
	//codigo a ejecutarse si la condicion es falsa
}

//Si else no hace nada

if(condicion){

}
```

Para agregar otra alternativa utilizamos **elseif** seguido de la **condicion entre parentesis** y el bloque de codigo que se va a ejecutar si cumple la condicion.

**Dato**: Yo puedo evitar que el programa haga BOOM con los condicionales, pero aveces esa no es la idea, porque si me piden que me mueva 10 casillas al este, tengo que completar la tarea si o si, entonces es mejor omitir la alternativa condicional y poner una precondicion para evitar el BOOM y asi cumplir la tarea. 

**Dato**: No es una buena practica anidar alternativas dentro de repeticiones o visceversa. Es mejor dividir en subtareas.

**Expresiones primitivas que son expresiones booleanas:**

* hayBolitas(`<color>`)
* puedeMover(`<direccion`)

Tambien puede haber funciones primitivas booleanas que vengan con el ejercicio.







