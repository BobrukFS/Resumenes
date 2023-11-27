# Arquitectura Q2

* Tiene 8 registros de uso general de 16 bits: R0 a R7.
* Tiene instrucciones de 2 operandos.

![[Pasted image 20230917195923.png]]

* Tiene direcciones de 16 bits.
* Los operandos pueden estar en registros, ser constantes(inmediato) o estar en direcciones de memoria. Entonces Q2 permite 3 modos de direccionamiento:

	* **Modo registro:**  El valor buscado esta en registro
	* **Modo inmediato:** El valor buscado esta codificado dentro de la instruccion
	* **Modo directo:** Especifica la direccion de memoria donde se encuentra el valor del operando

Para utilizar este modo de direccionamiento la direccion del operando se escribe entre corchetes.

![[Pasted image 20230917200238.png]]

Por ejemplo en la segunda operacion lo que sucede es que se realiza una lectura en lo que haya en la celda `[0xAB01]` y en `[0xFFEE]` con esos dos datos se lo vamos a paasar al circuito que hace la suma y el resultado se guarda en la celda de memoria, entonces se hace una operacion de escritura. Es decir en este ejemplo se realizan 2 lecturas y una escritura.

**Dato**: Tiene que tener 0x, es decir `[0xFFEE]`

![[Pasted image 20230917200833.png]]
![[Pasted image 20230917200852.png]]
![[Pasted image 20230917200939.png]]
![[Pasted image 20230917201244.png]]
![[Pasted image 20230917201439.png]]
![[Pasted image 20230917201548.png]]



**Dato** Para calcular el **tamaño de la memoria** por ejemplo cada celda tiene 16 bits y el bus de direcciones tiene 16 bits. El tamaño total de la memoria seria de 2^16 * 16.

**Dato**: La ejecucion de un programa depende de los accesos a memoria. Si los datos estan en memoria va a tardar mas que si esta en registro.

## Accesos a memoria durante el ciclo de ejecucion

Ejemplo: Se considerara como ejemplo una instruccion que esta ensamblada a partir de la celda 0xD401m, y por lo tanto PC=D401. El estado inicial de las celdas de memoria y el registro R5 es el siguiente:

![[Pasted image 20230918164705.png]]

1. Busqueda de la instruccion: Se lee la celda indicada por el PC y se almacenan en IR. 

![[Pasted image 20230918164756.png]]

Por lo tanto IR=3225. Ademas, se actualiza el PC para que quede preparado para la siguiente lectura PC=D402.

2. Decodificacion de la instruccion: A partir de la interpretacion de la cadena en IR, la unidad de Control entiende lo siguiente:

Ya que 2 es 0010, 3 es 0011 y  5 es 0101. Entonces 0011 001000 100101

![[Pasted image 20230918165025.png]]

Dado que el modo de direccionamiento del operando destino es directo, la UC entiende que hace falta la lectura de otra celda.

3. Completar la busqueda de la instruccion: Se lee la celda indicada por el PC(D402) y se almacena tambien en IR. Por lo tanto IR 3225F3F3

4. Completar la decodificacion de la instruccion:

	![[Pasted image 20230918165520.png]]

Dicho codigo maquina corresponde a la instruccion `SUB [0XF3F3], R5`

5. Busqueda de operandos: La UC solicita una lectura de la celda F3F3 para obtener el operando destino. Para esto realiza los siguientes pasos: Copia la direccion F3FE del registro IR al registro MAR. Indica a la Memoria Principal una lectura a traves de las lineas correspondientes en el Bus de control. Cuando la memoria Principal indica que el dato esta disponible ( a traves del bus de control), la UC tiene disponible el dato en el registro MBR.

![[Pasted image 20230918165803.png]]

6. Ejecucion de la instruccion: La UC le indica a la ALU la operacion SUB y le suministra los dos operandos:

	a. Operando destino: desde el registro MBR (BBBB)
	b. Operando origen: desde el registro R5(0011)

7. Almacenamiento de resultado: La unidad de control solicita una escritura en Memoria Principal para almacenar el resultado en el operando destino. Para esto realiza los pasos:

	a. Copia la direccion F3F3 del registro IR al registro MAR.
	b. Copia el resultado arrojado por la ALU en el registro MBR.
	c. Indica a la memoria principal una escritura a traves de las lineas correspondientes en el bus de control.

![[Pasted image 20230918170056.png]]

8. Comienza un nuevo ciclo con la siguiente instruccion

El cuadro de accesos a memoria principal es el siguiente:

![[Pasted image 20230918170147.png]]

Se utiliza para describir el contenido de los buses en cada operacion de lectura o escritura a memoria al ejecutar todo el ciclo de la instruccion.



Otros ejemplos:

![[Pasted image 20230917205634.png]]
Busqueda de la instruccion 2. Por el codoops y modops. Y por la direccion del modop directo.
![[Pasted image 20230917205914.png]]

Tiene 1, el codops y los modops (16 bits)
![[Pasted image 20230917210203.png]]
