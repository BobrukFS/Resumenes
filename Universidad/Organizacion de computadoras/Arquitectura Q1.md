# Arquitectura Q1

Q1 tiene las siguientes caracteristicas

* **Ochos registros** **de uso general** de 16 bits, es decir que son variables para usar en los programas, denominados **R0** a **R7**.
* Cinco instrucciones de 2 operandos: ADD(suma), SUB(resta), MUL(multiplicacion), DIV(division entera) y MOV(asignacion).

![[Pasted image 20230911201914.png]]

**Dato**: En el esquema, la flechita es donde se guarda el resultado, en la multiplicacion se guarda la parte menos significativa de bits en el destino pero tambien la parte mas significativa de bits en R7. Esto se debe que por ejemplo al multiplicar 16 bits nos da 32 bits, por lo que no se puede guardar solamente en el destino ya que supera los 16bits de almacenamiento.

* Al primer operando se lo denomina **operando destino**, por ser ademas donde se almacenara el resultado, y al segundo se lo denomina **operando origen**.
* Los operandos pueden ser referencias a variables(uno de los registros, es decir, R0 a R7) o valores constantes.
* Los valores constantes al igual que los registros tienen 16 bits, y se escriben en hexadecimal con la sintaxis: **0xhhhh**(donde h es un caracter hexadecimal). Por ejemplo, 0xFEFE.
* El sistema de numeracion soportado por esta arquitectura es BSS, considerando una ALU.

Un ejemplo de una instruccion sintacticamente valida en el lenguaje Q1 es MOV R5, 0xFF00, que copia el valor constante FF00 al registro R5. Otro ejemplo es ADD R5, R3, que suma el contenido de R3 con el contenido R5 y almacena el resultado en R5 (operando destino).

La instruccion debe incluir informacion acerca de la operacion a ejecutar y sobre que datos. Entonces, debe incluir el codigo de la operacion y un mecanismo para llegar hasta los operandos, mediante lo que llamamos **modos de direccionamiento**, es decir un mecanismo por el cual la unidad de control obtiene el operando requerido. Hay dos modos de direccionamiento.

* **Direccionamiento inmediato**: El operando esta presente en la propia instruccion. Este modo puede utilizarse para definir y utilizar constantes.
* **Direccionamiento registro**: El operando ahora se encuentra en un registro del sistema. La ventaja principal de este modo es que solo es necesario un pequeño campo de direcciones en la instruccion. Ademas, el tiempo de acceso a un registro interno de CPU es muy reducido. La desventaja principal es que el espacio de direccionamiento esta limitado.

**Dato**: El destino nunca puede ser un direccionamiento inmediato, es decir, una constante ya que no hay lugar donde se guarden los datos.

Para que los programas escritos en el lenguaje de Q1 sean ejecutables por una computadora, deben estar escritos en codigo maquina. Entonces es necesario establecer las reglas de traduccion codigo fuente a codigo maquina que debe aplicar un ensamblador. Esas reglas se conocen como **formatos de instrucciones**. Estos definen la organizacion de los bits dentro de una instruccion en terminos de las partes que la componen.

![[Pasted image 20230911203728.png]]

El siguiente es el formato de las instrucciones de Q1, que son instrucciones de 2 operandos, y el tamaño de cada campo esta expresado en bits.

![[Pasted image 20230911164612.png]]

En los campos **modo destino** y **modo origen** se codifica el modo de direccionamiento (inmediato o registro) de cada uno de los operandos. Y en particular, en el modo registro se indica tambien de que registro se trata. Esos 6 bits se completan considerando el cuadro 4.1. El campo **Origen u Operando origen y Destino u Operando destino** son opcionales, pues es necesario solo cuando el operando origen es Inmediato, es decir, que si son registros se ignoran ya que estan en el CPU porque son registros entonces la CPU ya conoce esos registros y no hay que indicarle nada. Asimismo, las instrucciones que tienen en Modo Destino operandos del tipo Inmediato son consideradas como invalidas por el procesador. Por otro lado, el campo de codop se completa con el codigo de operacion correspondiente a cada instruccion, siguiendo la codificacion indicada en el cuadro 4.2, donde se detallan las instrucciones de Q1, mostrando el codigo de operacion y el efecto esperado. El resultado de la operacion MUL es de 32 bits en lugar de 16, ocupando el registro R7 (los 2 bytes mas significativos) y el operando Destino (los 2 bytes menos significativos). Ademas, la operacion DIV es una division entera en el sistema BSS(16).


![[Pasted image 20230911165017.png]]
Por ejemplo si es R0, seria 100000 y si es R7 seria 100111

![[Pasted image 20230911164718.png]]
![[Pasted image 20230911165059.png]]

Si se considera esta característica al diseñar una arquitectura, se debe asumir el caso del resultado más grande. En particular, en la arquitectura Q, al multiplicar dos cadenas binarias de 16 bits, es posible obtener como máximo una cadena de 32 bits. Sin embargo, ¿cómo almacenar 32 bits en las celdas o registros de Q, que son de 16 bits?

Una posible solución a este problema es almacenar los 16 bits más significativos del resultado en R7 y los 16 menos significativos en el operando de destino. De modo que ante la cadena `xxxx xxxx xxxx xxxx yyyy yyyy yyyy yyyy`, los bits `x` se guardarán en R7, y los bits `y` en el destino. En caso de que el resultado sea una cadena con una cantidad de bits menor a 32, la ALU completa con ceros a la izquierda hasta llegar a 32 bits.

El codigo maquina se presenta en dos notaciones binaria y hexadecimal, dado que la version en hexadecimal, ademas de ser mas compacta, es mas legible.

![[Pasted image 20230911210937.png]]

Ejemplo:

![[Pasted image 20230911204626.png]]

**Dato**: El operando destino no lo tengo que especificar porque ya se que esta en R1

Otro ejemplo:

![[Pasted image 20230911205211.png]]

Ejercicios:

![[Pasted image 20230911205159.png]]

1. MUL R0, 0x000C
2. ADD R0, R1
3. MOV R2, R0