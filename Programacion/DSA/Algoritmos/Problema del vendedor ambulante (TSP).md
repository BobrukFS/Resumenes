# TSP

**Problema** : Supongamos que nos dan un brazo robotico equipado con un soldador. Al fabricar placas de circuitos, todos los chips y otros componentes deben sujetarse al sustrato. Cada chip tiene un conjunto de puntos de contacto que deben soldarse a la placa. Para programar el brazo robotico para este trabajo, primero debemos construir un orden de los puntos de contacto para que el robot visite y suelde hasta terminar el trabajo y luego regresa al primer punto de contacto para prepararse para la siguiente placa.

Una suposicion razonable es que el brazo del robot se mueve con una velocidad fija, por lo que el tiempo para viajar entre dos puntos es proporcional a su distancia.

```
Problem: Optimizacion del recorrido del robot
Input: Un conjunto S de n puntos en el plano
Output: Cual es el recorrido del ciclo mas corto que visita cada punto del conjunto S
```

**Concepto**: Para solucionar puedo pensar en un principio que debo utilizar la idea del "vecino mas cercano". Donde a partir de algun punto inicial P0, caminamos a su vecino mas cercano P1. Desde P1, caminamos a su vecino mas cercano no visitado, ecluyendo asi solo a P0 como candidato. Ahora repetimos esto hasta que nos quedemos sin puntos no visitados, despues de lo cual volvemos a P0 para cerrar el tour.

```js
NearestNeighbor(P)
	Elija y visite un punto inicial p0 del conjunto de puntos P
	p = p0
	i = 0
	Mientras haya puntos no visitados
		i = i + 1
		Seleccione pi no visitado mas cercano a pi-1
		Visite pi
	Regreso a p0 desde pn-1
```

Sin embargo, esto puede ser correcto pero no es eficiente. El algoritmo siempre encuentra un recorrido, pero no necesariamente encuentra el recorrido mas corto posible. Un recorrido mucho mas optimo para estos puntos comienza desde el punto mas a la izquierda y visita cada punto mientras caminamos hacia la derecha, antes de regresar al punto mas a la izquierda nuevamente. El enfoque del vecino mas cercano esta condenado a fracasar en ciertos conjuntos de puntos.

![[Pasted image 20230619222938.png]]

Otro enfoque seria conectar repetidamente el par mas cercano de puntos finales cuya conexion no creara un problema , como la terminacion prematura de un ciclo. Cada vertice comienza como su propia cadena de vertice unico. Despues de fusionar todo, terminaremos con una sola cadena que contiene todos los puntos. Conectar los dos puntos finales nos da un ciclo. En cualquier paso, durante la ejecuccion de esta heuristica de par mas cercano, tendremos un conjunto de vertices unicos y el final de cadenas disjuntas de vertices unicos y el final de cadenas disjuntas de vertices disponibles para fusionar.

```
	ClosestPair(P)
		Sea n el numero de puntos del conjunto P
		Para i = 1 hasta n - 1 do
			d = infinite
			Para cada par de extremos (s,t) de distintas cadenas de vertices
				if dist(s,t) <= d entonces 
					Sm = S 
					Tm = t 
					d = dist(s, t)
			Connect (Sm, Tm) por un borde
		Conecte los dos pintos finales por un borde
```

Este enfoque hace lo correcto en el ejemplo. Comienza conectando "0"  a sus dos vecinos inmediatos, los puntos 1 y -1. Posteriormente, el siguiente par mas cercano alternara de izquierda a derecha haciendo crecer la ruta central en un enlace a la vez. Sin embargo, este enfoque es incorrecto para otros recorridos

La busqueda de un algoritmo eficiente para resolver este problema llamado "Problema del viajante de comercio" (TSP) es dificil.