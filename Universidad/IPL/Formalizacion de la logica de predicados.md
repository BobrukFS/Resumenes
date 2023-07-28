# Formalizacion de la logica de predicados
Para formalizar las oraciones necesitamos de un diccionario que nos permita realizar las traducciones entre ambos lenguajes(lenguaje natural y el de predicados). Lo que nosotros definimos en el diccionario es lo unico que podemos utilizar. Al formalizar hay dos instancias, la declaracion y la aplicacion.

![[Pasted image 20230329141819.png]]

**Constantes**

Una constante es el nombre formal que utilizamos dentro del diccionario para representar a un individuo de nuestro dominio. Al definirse dentro del diccionario, se denotan con letras minusculas, donde la letra hace referencia al individuo al cual representa, es decir al sujeto de la oracion.

![[Pasted image 20230329141859.png]]
Es importante entender que sera necesario definir una constante por cada individuo del dominio, por lo cual, nuestro diccionario tendra tantas constantes como individuos necesitemos mencionar.

**Predicados**

Las propiedades y relaciones, en el lenguaje de logica de predicados se denominan formalmente como **predicados.**

En el diccionario definimos predicados de manera general, es decir, utilizando variables del dominio establecido, para luego, mediante formulas, traducir oraciones concretas, aplicando dichos predicados a los individuos representados por las constantes. Al traducir las formulas, obtenemos oraciones gramaticalmente bien formadas en el lenguaje natural, es decir, con su sujeto(constante) y su predicado (la propiedad o relacion).

Los predicados se representan en el diccionario con letras mayusculas : S, R, T, etc, relacionadas con lo que representan. La sintaxis al momento de definir un predicado es la siguiente:

![[Pasted image 20230329141959.png]]
![[Pasted image 20230329142004.png]]

**Dato**: **Aridad** es la cantidad de variables(o argumentos) que necesita un predicado. Un predicado de **aridad 1** hace referencia a una propiedad mientras que un predicado de **aridad 2** hace referencia a una relacion.

Otro ejemplo con un predicado de aridad 2(relacion).

![[Pasted image 20230329142841.png]]

**Dato**: Es importante observar que la variable se encuentra de ambos lados del igual, del lado izquierdo es necesario para conocer la cantidad de variables que necesita el predicado y el dominio al que pertenece, mientras que del lado derecho nos permitira crear la oracion para formalizar.

Como un predicado aplicado representa un valor de verdad, podemos unir varios predicados usando conectivas logicas. El valor de verdad de la formula completa sera el resultado de evaluar los predicados aplicados, y luego usar las reglas de la logica proposicional. Podemos conectar con conectivas logicas tanto predicados de aridad 1 (propiedades) como predicados de aridad 2 (relaciones).

![[Pasted image 20230329142049.png]]
Para saber si formalizamos correctamente, podemos realizar el paso inverso, es decir, traducir la formula (siempre utilizando el diccionario) y ver si obtuvimos la oracion original en el lenguaje natural.

**Cuantificadores**

Un **cuantificador** es una expresion que indica la cantidad de veces que un predicado (propiedad o relacion) se cumple (verdadero) al aplicarse a cada uno de los individuos del dominio.

**Contamos con tres tipos de cuantificadores:**

* **Cuantificador universal (∀) :** El cuantificador universal se utiliza para representar conjuntos que afirman que **todos** los individuos del dominio cumplen el predicado. Es decir, que si aplicamos el predicado a cada uno de los individuos del dominio, este debe dar verdadero en todos los casos. El simbolo **∀** **se lee “Para todo”.**

![[Pasted image 20230329143114.png]]

* **Cuantificador existencial(∃) :** El cuantificador existencial se utiliza para representar conjuntos que afirman que algun individuo del dominio (o mas de uno) cumplen el predicado. El simbolo se lee como **“Existe”**.
![[Pasted image 20230329143149.png]]
* **Cuantificador existencial negado(∃ tachada) :** El cuantificador existencial negado se utiliza para representar conjuntos que afirman que ningun individuo cumple el predicado. Es decir, que si aplicamos el predicado a cada individuo del dominio, todos los predicados evaluaran FALSO.El simbolo se lee como **“No existe”.**

![[Pasted image 20230329143300.png]]

Los cuantificadores tambien utilizan variables, pero en este caso la variable x no representa a un unico individuo, sino al dominio completo, es decir a **todos los individuos.** Los cuantificadores siempre se aplican al dominio completo, independientemente de su resultado. Es decir “Para todo individuo del dominio x, esa x cumple con el predicado”.

Es importante asignar una variable al cuantificador porque podemos cuantificar mas de un individuo. Ejemplo:

![[Pasted image 20230329143328.png]]

**Dato:** Podemos encontrar equivalentes por ejemplo en oraciones de todos y ningun si usamos la logica.