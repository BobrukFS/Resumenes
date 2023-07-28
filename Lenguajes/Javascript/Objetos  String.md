# Objetos String
Las siguientes funcionalidades son las propiedades y los metodos mas usados de los objetos **String.**

* **Length() :** Esta propiedad devuelve un entero que representa la cantidad de caracteres en la cadena.

* **toLowerCase() :** Este metodo devuelve una cadena con los caracteres convertidos a letras minusculas.

* **toUpperCase()** :Este metodo devuelve una cadena con los caracteres convertidos a letras mayusculas.

* **Trim()** **:**  Este metodo elimina espacios en blanco a ambos lados de la cadena de caracteres. JS tambien incluye los metodos **trimLeft()** y **trimRight()** para limpiar la cadena de caracteres en un lado especifico (izquierda o derecha).

* **substr (Comienzo, extension) :** Este metodo devuelve una nueva cadena de caracteres con caracteres extraidos de la cadena original. El atributo **comienzo** indica la posicion del primer carácter a leer, y el atributo **extension** determina cuantos caracteres queremos incluir. Si no se especifica la extension, el metodo devuelve todos los caracteres hasta el final de la cadena.

* **substring(Comienzo, final) :** Este metodo devuelve una nueva cadena de caracteres con caracteres extraidos de la cadena original. Los atributos **comienzo y final** son el indice que determinan las posiciones del primer y ultimo carácter a incluir.

* **Split(Separador, limite) :** Este metodo divide la cadena de caracteres y devuelve un array con todas las partes. El atributo **separador** indica el carácter en el que se va a cortar la cadena(Por ejemplo si especificamos “//” va a separar en donde haya esas barras) y el atributo **limite** es un numero entero que determina el numero maximo de partes. Si no especificamos un limite, la cadena se cortara cada vez que se encuentre el separador. Se puede unir nuevamente con un carácter que especificamos con **join().**

* **Slice(comienzo, final) :** Este metodo copia los valores en las posiciones indicadas por los atributos y genera una nueva cadena de caracteres con dichos valores copiados. Los atributos comienzo y final indican los indices del primer y ultimo valor a copiar. El ultimo valor no se incluye en la nueva cadena de caracteres.

* **StartsWith(valor) :** El método startsWith() indica si una cadena de texto comienza con los caracteres de una cadena de texto concreta, devolviendo true o false según corresponda.

* **EndsWith(valor):** El método endsWith() determina si una cadena de texto termina con los caracteres de una cadena indicada, devolviendo true o false según corresponda.

* **includes(buscar, posicion) :**  Este metodo busca el valor del atributo buscar dentro de la cadena y devuelve true o false de acuerdo con el resultado. El atributo **buscar** es el texto que queremos buscar, y el atributo **posicion** determina el indice en el que queremos comenzar la busqueda. Si el atributo **posicion**  no se especifica, la busqueda comienza desde el inicio de la cadena.

* **indexOf(valor, posicion):** Este metodo devuelve el indice en el que el texto especificado por el atributo **valor** se encuentra por primera vez. El atributo **posicion** determina el indice en el que queremos comenzar la busqueda. Si el atributo **posicion** no se especifica, la busqueda comienza desde el inicio de la cadena. El metodo devuelve el valor -1 si ninguna coincidencia es encontrada.

* **lastIndexOf(valor, posicion) :** Este metodo devuelve el indice en el que se encuentra por primera vez el texto especificado por el atributo **valor**. A diferencia de indexOf(), este metodo realiza una busqueda hacia atrás, desde el final de la cadena. El atributo **posicion** determina el indice en el que queremos comenzar la busqueda. Si no se especifica el atributo **posicion**, la busqueda comienza desde el final de la cadena. El metodo devuelve el valor -1 si no se encuentra ninguna coincidencia.

* **replace(expresion, reemplazo) :** Este metodo reemplaza la parte de la cadena de caracteres que coincide con el valor del atributo **expresion** por el texto especificado por el atributo **reemplazo.** El atributo **expresion** se puede especificar como una cadena de caracteres o como una expresion regular para buscar un texto con un formato particular.

* **repeat(repeticiones) :** El método repeat() construye y devuelve una nueva cadena que contiene el número especificado de copias de la cadena en la cual fue llamada, concatenados.

* **localeCompare(string) :** El método localeCompare() compara dos strings en la configuración regional local.

* **Concat(string) :** Este metodo concatena el string con el string especificado por el atributo y devuelve un nuevo string con el resultado. Los arrays originales no se modifican.

* **padStart(longitud, string) :** El método padStart() rellena la cadena actual desde el inicio con una cadena dada (repetida eventualmente) de modo que la cadena resultante alcance una longitud dada. El relleno es aplicado desde el inicio (izquierda) de la cadena actual.

* **padEnd(longitud,string) :** El método padEnd() rellena la cadena actual desde el final con una cadena dada (repetida eventualmente) de modo que la cadena resultante alcance una longitud dada. El relleno es aplicado desde el inicio (izquierda) de la cadena actual.

**Dato:** Las cadenas de caracteres se almacenan como arrays. Es decir cada carácter es un elemento.