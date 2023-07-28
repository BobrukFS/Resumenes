# Container queries CSS

Los CSS container proporciona una nueva forma para aislar secciones de una página e indicarle al navegador que estas secciones son independientes del resto de la página en términos de estilos y disposición. Los container queries nos permiten aplicar estilos al contenido segun el tamaño del contenedor. Se suele utilizar para micro-layouts

Para usar container queries, necesito declarar un **containment context** en un elemento, de esta manera el navegador sabra que estamos interesados en consultar las dimensiones del contenedor. Para ello se utiliza la propiedad **container-type** con los valores size, inline-size, o normal.

![[Pasted image 20230715155321.png]]

Una vez el container es creado podemos utilizar la regla **@container** para escribir una container query

Tambien podemos darle un nombre al container con la propiedad **cointainer-name** y luego hacemos referencia a este containment context usando la regla @container seguida del nombre.

## Unidades de longitud de container queries

![[Pasted image 20230715160026.png]]