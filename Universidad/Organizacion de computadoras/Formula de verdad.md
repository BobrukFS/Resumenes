# Formula de verdad

Para llevar a cabo este paso nosotros tenemos dos metodos:

1. Suma de productos(SoP)
2. Producto de sumas(PoS)

## Suma de productos

Es una suma (disyuncion) de terminos que son productos (conjuncion) entre literales, es decir, entre una variable o su negacion.

Para construir esta expresion, se debe extraer el termino que describe cada caso de la tabla de verdad que verifica la formula, es decir, cada fila donde la salida vale 1.

Con cada uno de esos casos se describe un termino con todas las variables, segun aparezcan afirmadas o negadas. 

![[Pasted image 20230826220456.png]]

Finalmente, los terminos se componen con una disyuncion:

![[Pasted image 20230826220517.png]]

Otro ejemplo:

![[Pasted image 20230826182539.png]]
![[Pasted image 20230826182610.png]]
## Producto de sumas

Es una conjuncion de disyunciones. A diferencia del SoP, describe la formula a partir de los casos donde no se cumple la proposicion. Por lo tanto en esta expresion, se deben tomar los casos donde la formula vale 0.

![[Pasted image 20230826220715.png]]

Luego, esos casos se niegan y se unen con conjuncion, ya que no debe cumplirse ninguno de ellos: 

![[Pasted image 20230826220809.png]]

Finalmente, se puede aplicar las leyes de Morgan, donde los terminos negados se convierten en disyunciones

![[Pasted image 20230826220902.png]]

Otro ejemplo:

![[Pasted image 20230826182644.png]]

Ejemplo: circuito mayoria

![[Pasted image 20230826221801.png]]
![[Pasted image 20230826221812.png]]

![[Pasted image 20230826182658.png]]
