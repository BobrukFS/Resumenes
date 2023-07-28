# Caracteristicas basicas de CSS

* Es un lenguaje que trabaja junto con HTML para proporcionar estilos visuales a los elementos de un documento web. 

* Si un navegador está analizando sus reglas y encuentra una propiedad o valor que no comprende, lo ignora y pasa a la siguiente declaración. Hará esto si ha cometido un error y ha escrito mal una propiedad o un valor, o si la propiedad o el valor son demasiado nuevos y el navegador aún no los admite(Se puede mirar el soporte de las propiedades en caniuse.com). Si un navegador encuentra un selector que no comprende, simplemente ignorará toda la regla y pasará a la siguiente.

* Algunas propiedades y funciones CSS todavía se consideran experimentales. Por esta razón, se deben declarar con un prefijo que representa el motor web utilizado. Por ejemplo, si queremos que la función linear-gradient() funcione en Google Chrome, tenemos que declararla como -webkit-linear-gradient(). Si quiere usar esta función en su sitio web, deberá repetir la propiedad background para cada navegador existente con su correspondiente prefijo. Los prefijos requeridos para los navegadores más populares son -moz- para Mozilla Firefox, -webkit- para Safari y Google Chrome, -o- para Opera, y -ms- para Internet Explorer.
## ¿Como funciona CSS?

1. El navegador carga el HTML.

2. Convierte el HTML en un DOM (Document Object Model). El DOM representa el documento en la memoria de la computadora.

3. El navegador obtiene la mayoria de los recursos a los que esta vinculado el documento HTML, como imagenes y videos incrustados, CSS y Javascript.

4. El navegador analiza el CSS obtenido y ordena las diferentes reglas por sus tipos de selector en diferentes “cubos”, por ejemplo, elemento, clase, ID, etc. En funcion de los selectores que encuentra, determina que reglas se deben aplicar a que nodos en el DOM y les asigna el estilo según sea necesario.

5. La visualizacion de la pagina se muestra en la pantalla.

## Utilizar CSS
### En archivo externo
Para utilizar CSS en un archivo externo lo que tenemos que hacer es:

```HTML
<link rel="stylesheet" href="styles.css">
```

Es lo que se utiliza siempre.

### En el mismo HTML
Para poner estilos en el mismo codigo HTML lo que tenemos que hacer es:

```HTML
<style>
	h1 {
		color: blue;
	}

</style>
```
### En linea
Para poner estilos en linea lo que tenemos que hacer es:

```HTML
<h1 style="color : blue; blackground-color : red;">
```

Se suele utilizar para algunas etiquetas, pero sin abusar.

## Cascada

CSS actua en **cascada**, es decir va a aplicar el valor final. El orden de las reglas CSS es importante; cuando se aplican dos reglas que tienen la misma **especificidad**, se utiliraza la ultima en la hoja de estilos.

Ejemplo:

![[Pasted image 20221201191005.png]]

Hay tres factores a considerar, enumerados aquí en orden creciente de importancia:

* **Orden de origen**

* **[[Especificidad]]**

* **[[Importancia]]**