# Diseño de varias columnas
Habilitamos multicol usando una de dos propiedades: **column-count** o **column-width**. La propiedad column-count toma un número como su valor y crea ese número de columnas. Las columnas que crea tienen anchos flexibles: el navegador calcula cuánto espacio asignar a cada columna.

![[Pasted image 20221214114915.png]]
Para cambiarle el ancho a la columna podemos utilizar **column-width.** El navegador ahora le dará tantas columnas como pueda del tamaño que especifique; cualquier espacio restante se comparte entre las columnas existentes. Esto significa que no obtendrá exactamente el ancho que especifique a menos que su contenedor sea exactamente divisible por ese ancho. Para utilizar las propiedades column-count y column-width al mismo tiempo podemos utilizar la propiedad **column**.

Las columnas creadas por multicol no se pueden diseñar individualmente. No hay forma de hacer que una columna sea más grande que otras columnas o de cambiar el fondo o el color del texto de una sola columna. Tiene dos oportunidades para cambiar la forma en que se muestran las columnas:

* Cambiando el tamaño del espacio entre columnas usando el **column-gap**.

* Agregar una regla entre columnas con **column-rule.** La propiedad column-rule es una forma abreviada de **column-rule-width, column-rule-style y column-rule-color**

![[Pasted image 20221214115046.png]]
![[Pasted image 20221214115050.png]]
Para hacer que un elemento abarque todas las columnas, especifique el valor de all para la propiedad **column-span**.

![[Pasted image 20221214115103.png]]