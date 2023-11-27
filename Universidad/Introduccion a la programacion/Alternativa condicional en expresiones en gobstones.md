# Alternativa condicional en expresiones en gobstones

La alternativa condicional en expresiones se escribe:

```gobstones

return (choose <expresion1> when (<condicion>)
		<expresion2> otherwise)
		
Si la condicion es verdadera, elige la expresion1, y en otro caso, elige la expresion2.

//Ejemplo de varias alternativas anidadas

function direccionParaElCodigo(codigo){
/*
	PROPOSITO: Describir la direccion correspondiente al codigo dado.
	PRECONDICIONES: **codigo** esta entre 1 y 4.
	PARAMETROS: **codigo** es de tipo Numero.
	TIPO: Direccion.
*/

return (choose Norte when (codigo == 1)
				Este when (codigo == 2)
				Sur when (codigo ==3)
				Oeste otherwise
		)
}
```

La separacion entre comandos y expresiones, junto con las variables dificulta la modularizacion. Preferimos modularizacion sobre eficiencia.
