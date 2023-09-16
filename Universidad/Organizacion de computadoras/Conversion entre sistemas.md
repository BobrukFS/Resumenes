# Conversion entre sistemas

## Interpretacion de cadenas

La interpretacion (I) es el proceso para determinar que numero (o cantidad) representa una cadena.
### Binario a decimal

Para ello lo que hacemos es en este caso al ser de base 2, lo que hacemos es multiplicar el digito de la cadena por la base exponente n-1.

Ejemplo:

![[Pasted image 20230818134242.png]]
### Hexadecimal a binario o a decimal
![[Pasted image 20230818184201.png]]
![[Pasted image 20230501160019.png]]
## Representacion de valores

La representacion (R) es un proceso permite construir las cadenas a partir de un valor. Para hacerlo se presenta el mecanismo de las **divisiones sucesivas**, donde se aplica el siguiente algoritmo hasta obtener un cociente igual a 0.

![[Pasted image 20230818133844.png]]
### Decimal a binario

Para ello debemos realizar divisiones sucesivas por 2 y escribir los restos obtenidos en cada division en orden inverso al que han sido obtenidos.

![[Pasted image 20230501155332.png]]

### Decimal a Hexadecimal

Para ello debemos realizar divisiones sucesivas por 16 y escribir los restos obtenidos en cada division en orden inverso al que han sido obtenidos.

![[Pasted image 20230501155642.png]]
## Agrupacion de bits

La cadena binaria se segmenta formando cuartetos de bits comenzando por el bit menos significativo. Dado que cada cuarteto es alguna de las combinaciones de 4 bits del sistema BSS(4) y por lo tanto el rango que cubren es `[0,15]`.

![[Pasted image 20230501155930.png]]
![[Pasted image 20230818190220.png]]
![[Pasted image 20230818190234.png]]

