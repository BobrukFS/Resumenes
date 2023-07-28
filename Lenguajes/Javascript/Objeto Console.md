# Objeto Console
El objeto **Console** se asigna a la propiedad **console** del objeto **Window** y se transforma en la conexión entre nuestro codigo y la consola del navegador. Los siguientes son algunos de los metodos que se incluyen en el objeto Console para manipular la consola.

**Metodos de registro:**

* **log(valor) :** Este metodo muestra el valor entre parentesis en la consola. Es un mensaje de depuracion.

* **assert(condicion, valores) :** Este metodo muestra en la consola los valores que especifican los atributos si la condicion especificada por el primer atributo es falsa.

* **clear() :** Este metodo limpia la consola. Los navegadores tambien ofrecen un boton en la parte superior de la consola con la misma funcionalidad.

* **error(mensaje) :** Muestra un mensaje de error en la consola web.

* **info(mensaje) :** Emite un mensaje informativo a la Consola Web. En Firefox y Chrome, se muestra un pequeño ícono "i" junto a estos elementos en el registro de la Consola Web.

*  **table() :** Muestra datos tabulares como una tabla.Esta función toma un argumento obligatorio: data, que debe ser un array o un objeto, y un parámetro adicional: columns.

* **warn() :** Imprime un mensaje de advertencia en la Consola Web.

**Metodos de conteo:**

* **count() :** Registra el numero de veces que se llama a count(). Esta funcion toma como argumento opcional una etiqueta. Se utiliza para ver cuantas veces se ejecuta algo.

* **countReset() :** Resetea el contador console.count().

**Metodos de agrupacion:**

* **group() :** Crea un nuevo grupo en linea en el registro de la consola web.

* **grupEnd() :** Remueve un grupo en linea en el registro de la consola web.

* **groupCollapsed() :** Crea un grupo en linea pero contraido, el usuario debe expandirlo para verlo.

**Metodos de temporizacion**

* **time() :** Inicia un temporizador.

* **timeEnd() :** Detiene un temporizador.

* **timeLog() :** Registra el valor actual de un temporizador.

**Dato:** Para **modificar el estilo** del texto de la consola, en **console.log(“%cstring”,”aquí van los estilos”)**