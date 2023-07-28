# Especificidad

La especificidad es como el navegador decide que regla se aplica si varias reglas tienen diferentes selectores, pero aun podrian aplicarse al mismo elemento. Es basicamente una medida de que tan especifica sera la seleccion de un selector :

Ejemplo:

![[Pasted image 20221201191645.png]]

Un selector de clase tiene mas peso que un selector de elemento, por lo que las propiedades definidad en la clase anularan las aplicadas directamente al elemento. Una practica comun es definir estilos genericos para los elementos basicos y luego crear clases para aquellos que son diferentes.
## Como medir la especificidad
La cantidad de especificidad que tiene un selector se mide utilizando cuatro valores (o componentes) diferentes, que se pueden considerar como miles, centenas, decenas y unidades:

1. **Miles :** marque uno en esta columna si la declaración está dentro de un atributo style , también conocido como estilos en línea. Tales declaraciones no tienen selectores, por lo que su especificidad siempre es 1000.

2. **Cientos :** marque uno en esta columna para cada selector de ID contenido dentro del selector general.

3. **Decenas :** puntúe uno en esta columna para cada selector de clase, selector de atributo o pseudoclase contenido dentro del selector general.

4. **Unos :** puntúe uno en esta columna para cada selector de elemento o pseudoelemento contenido dentro del selector general.

![[Pasted image 20221201191708.png]]