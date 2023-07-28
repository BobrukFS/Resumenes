# Logica de predicados
La **logica de predicados** o **logica de orden uno**, nos va a permitir formalizar oraciones sobre individuos, sobre sus propiedades, y sobre como esos individuos se relacionan entre si. La diferencia con la logica propoposicional, es que la logica de predicados nos va a permitir determinar de forma mas rapida el valor de verdad, y vamos a tener mas certeza porque tenemos mas informacion. Nosotros en logica de predicamos dividimos la proposicion en dos partes: el individuo y el predicado.

**Dato:** Todo lo que se puede formalizar con logica proposicional, tambien se puede formalizar con logica de predicados, pero no al reves.

Para formalizar las oraciones primero debemos elaborar un diccionario donde debemos reconocer los 4 elementos principales que nos brinda la logica de predicados:

![[Pasted image 20230329134922.png]]
## Elementos de la logica de predicados
### Dominio

El **dominio** es el conjunto de valores que puede tomar cada individuo al cual le queremos aplicar una propiedad o relacion. Basicamente, es el conjunto de individuos que queremos representar. El dominio puede identificarse con el universo total o puede ser un conjunto restringido del mismo (un subconjunto).

Hay **dos formas de definir el dominio**:

* **Por extension:** Enumeramos uno por uno cada valor. Ejemplo: Dominio = \[“La vida es bella”, “El hijo de la novia”, “Tiempo de valientes”, “Duro de matar”]. Este caso se utiliza para conjuntos muy reducidos.

* **Por comprension :** Simplemente mencionamos el nombre del conjunto. Por ejemplo : Dominio = peliculas.

**Dato:** Pueden coexistir mas de un dominio.

#### Individuo
Un **individuo** es un elemento unico e irrepetible del dominio. Puede ser una persona, un animal, o un valor mas abstracto. Para determinar un individuo es necesario que sea **identificable de forma univoca**. Lo que importa es lo que queremos representar no lo que escribimos, por ejemplo es el mismo individuo escribir 5 que V. Un individio nunca podra ser un sustantivo colectivo. A los individuos los debemos expresar con **nombres propios** es decir, empiezan con mayuscula. Si mi individuo no esta en mi dominio, la proposicion sera falsa, en caso contrario, sera verdadera.

![[Pasted image 20230329135344.png]]
Los individuos **tienen propiedades**.
##### Propiedad
Una **propiedad** es un adjetivo, una cualidad, caracteristica o atributo que puede **aplicarse a un individuo** perteneciente a un dominio.

![[Pasted image 20230329135408.png]]
Para que un individuo tenga una propiedad, debemos “aplicar” dicha propiedad al individuo. De esta manera podemos tratar la expresion como una proposicion. Por ejemplo, si tenemos la propiedad “es un caballo” , vamos a aplicar a “Rocinante” esta propiedad para obtener la proposicion “Rocinante es un caballo”, y asi obtener un valor de verdadero o falso.

![[Pasted image 20230329135419.png]]
Hay **propiedades que dependen de otras propiedades.** El hecho de que una propiedad dependa de otra implica el uso de conectivas, se evita utilizar la disyuncion para evitar ambiguedades, por lo que se utiliza la conjuncion y la negacion.

![[Pasted image 20230329135444.png]]
Tambien existen **propiedades compuestas.**

![[Pasted image 20230329135452.png]]
##### Relacion
Cuando vemos que en una propiedad estamos haciendo mencion a un individuo para aplicar a otro individuo, lo que en realidad queremos expresar es una **relacion / vinculo entre estos dos individuos del mismo o diferentes dominios.**

Una relacion, **se aplica sobre dos individuos**.

![[Pasted image 20230329135745.png]]
Tambien existen **relaciones compuestas** que son aquellas que utilizan conectivas.

![[Pasted image 20230329135759.png]]
Hay diferentes maneras de expresar lo mismo, esto se logra indicando el orden correcto de los individuos para sostener la proposicion original.

![[Pasted image 20230329135809.png]]

**Dato**: Una relacion que se aplica por lo menos a un individuo que no esta en el universo, es falsa.

## Variables
Una **variable** representa a un individuo dentro de una propiedad o relacion, pero que al momento de definirla, desconocemos cual es. Para esta representacion se utilizan letras en minusculas. Por convencion se utilizan x, y, z, etc.

### ¿Cómo utilizamos las variables para formar oraciones?

Para ello sustituimos el individuo de la oracion por la variable (letra) la cual ira tomando distintos valores según se vaya necesitando para formar las diferentes oraciones.

Este metodo lo realizaremos cada vez que necesitemos que los individuos tomen diferentes valores, es decir que podemos utilizar variables tanto al definir propiedades como relaciones. De esta manera, las propiedades tendran 1 variable (que representa a un individuo) y las relaciones 2 variables ( que representan a los individuos que se relacionan)

![[Pasted image 20230329140109.png]]
#### Representando relaciones

![[Pasted image 20230329141432.png]]
#### Instancias de las variables
Tenemos dos instancias. El momento de **definicion** de los elementos dentro del diccionario, y el momento de **aplicación** de dichos elementos para formalizar (traducir). Las definiciones se realizan una sola vez, y las aplicaciones se realizan tantas veces como sea necesaria.
## Representando conjuntos
### Todos
Para hacer que una propiedad aplique a todo un conjunto (todos los individuos del dominio) y no a solo un individio lo que debemos hacer es crear una nueva propiedad, que seria igual a aplicar la propiedad a cada individuo del dominio y unirlos por conectivas. En el caso de “todos”, estamos aplicando la propiedad a cada individuo del dominio uniéndolos mediante conjunciones.

![[Pasted image 20230329141525.png]]
### Algun/ Alguien
Para hacer que una propiedad aplique a todo un conjunto (todos los individuos del dominio) y no a solo un individio lo que debemos hacer es crear una nueva propiedad, que seria igual a aplicar la propiedad a cada individuo del dominio y unirlos por conectivas. En el caso de alguien, estamos aplicando la propiedad a cada individuo del dominio uniéndolos mediante disyunciones.

![[Pasted image 20230329141543.png]]
### Ningun
Para hacer que una propiedad aplique a algun individuo del conjunto como minimo lo que debemos hacer es crear una nueva propiedad, que seria igual a aplicar la propiedad a cada individuo del dominio y unirlos por conectivas. En el caso de “ningun”, debemos aplicar la propiedad como una conjunción de la negación de cada individuo del dominio.

![[Pasted image 20230329141558.png]]
[[Formalizacion de la logica de predicados]]