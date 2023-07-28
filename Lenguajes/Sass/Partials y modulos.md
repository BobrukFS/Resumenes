# Partials y modulos

## Partials

Puede crear archivos Sass parciales que contengan pequeños fragmentos de CSS  que puede incluir en otros archivos Sass. Esta es una excelente manera de modularizar su CSS y ayudar a que las cosas sean más fáciles de mantener. Un **partials** es un archivo Sass nombrado con un guión bajo al principio. El guión bajo le permite a Sass saber que el archivo es solo un archivo parcial y que no debe generarse en un archivo CSS . Sass parciales se utilizan con la regla **@use**. La sintaxis seria : @use "`url`" as `namespace`.

Ejemplo:

![[Pasted image 20221214225415.png]]

Otro ejemplo:

![[Pasted image 20221214225427.png]]

Otro ejemplo:

![[Pasted image 20221214225501.png]]

**Dato**: No hace falta utilizar el guion bajo al importar o usar un partial.

### Ventajas de usar @use frente a @import

* El archivo solo se importa una vez, sin importar cuantas veces haga @use en un proyecto.
* Las variables, los mixins y las funciones (lo que Sass llama "miembros") que comienzan con un guion bajo o un guion medio se consideraran privados y no se importan.
* Los miembros del archivo usado solo estan disponibles localmente, pero no se trasmiten a futuras importaciones.


## Modulos

No tiene que escribir todo su Sass en un solo archivo. Puedes dividirlo como quieras con la regla @use. Esta regla carga otro archivo Sass como un módulo, lo que significa que puede hacer referencia a sus variables, combinaciones y funciones en su archivo Sass con un espacio de nombres basado en el nombre del archivo.

[[Modulos incorporados en Sass]]