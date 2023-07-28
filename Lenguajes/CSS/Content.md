# Content

La propiedad **content** se emplea para generar nuevo contenido de forma dinámica e insertarlo en la página HTML, ese nuevo contenido se puedo cambiar de estilo con las propiedades tipicas de CSS. Como CSS es un lenguaje de hojas de estilos cuyo único propósito es controlar el aspecto o presentación de los contenidos, algunos diseñadores defienden que no es correcto generar nuevos contenidos mediante CSS.

En primer lugar, el estándar CSS 2.1 indica que la propiedad content sólo puede utilizarse en los pseudo-elementos ::before y ::after. Como su propio nombre indica, estos pseudo-elementos permiten seleccionar (y por tanto modificar) la parte anterior o posterior de un elemento de la página.

Se suele poner **content : ""** para crear un pseudoelemento vacio pero tambien le podemos incluir contenido. Ejemplo: content : "hola";. Por ejemplo, una posibilidad sería generar contadores o introducir imagenes.

[[Counter]]