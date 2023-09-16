# Parametros en gobstones

Los procedimientos pueden tener **parametros**, es decir, un dato que falta y debe proveerse al usarlo. A esos parametros le pasamos **argumentos**, es decir, el valor especifico usado en la invocacion de un procedimiento con parametros. A la hora de invocar el procedimiento al pasarle los argumentos debemos respetar el mismo orden de los parametros.

Los parametros deben comenzar con una letra minuscula, pueden contener solo letras, numeros y guiones bajos.  Se puede CamelCase, debe estar asociado con lo que representa y debe ser un sustantivo.Tambien hay que utilizar la notacion Mix-FIX, es decir, mantenemos CamelCase para separar palabras y usamos guion bajo para indicar donde deberia leerse un argumento, es decir va haber tantos guiones bajos como parametros que tenga el procedimiento

```gobstone
Sacar_DeColor_(cantidadAPoner, colorAPoner)
```

Un **procedimiento parametrizado** representa a muchos otros procedimientos simples y permite solucionar muchos problemas parecidos de una sola vez.

Si definimos un parametro pero no le pasamos un argumento al procedimiento va a dar error. Lo mismo si damos un argumento pero no definimos el parametro

Los parametros solo se pueden utilizar dentro del scope, es decir la region del programa donde el mismo tiene validez y puede ser utilizado. Cada parametro es unico, no se repite en otros procedimientos. Si nosotros declaramos un parametro, solo puede ser utilizado dentro del procedimiento y dentro de los procedimientos donde pasamos el parametro como argumento.

Los procedimientos parametrizados en el contrato tienen una nueva seccion llamada parametros donde nombramos a los parametros, aclaramos el tipo de dato y lo que hace.

![[Pasted image 20230824212532.png]]

**Dato**: Los procedimientos sin parametros se denominan procedimientos simples.

![[Pasted image 20230826033750.png]]

[[Tipos de datos y expresiones]]