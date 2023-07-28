# Herencia en CSS
Algunos valores de propiedad CSS establecidos en los elementos principales son heredados por sus elementos secundarios y otros no.

Ejemplo:

![[Pasted image 20221201193058.png]]

Propiedades como anchos (como se mencionó anteriormente), márgenes, relleno y bordes no se heredan.

## Controlando la herencia

CSS proporciona cuatro **valores de propiedad universales** especiales para **controlar la herencia**. Cada propiedad CSS acepta estos valores:

* **inherit** : Establece el valor de propiedad aplicado a un elemento seleccionado para que sea el mismo que el de su elemento principal. Es decir activa la herencia.

* **initial** : Establece el valor de propiedad aplicado a un elemento seleccionado en el valor inicial de esa propiedad.

* **revert** : Restablece el valor de propiedad aplicado a un elemento seleccionado al estilo predeterminado del navegador en lugar de los valores predeterminados aplicados a esa propiedad.

* **unset** : Restablece la propiedad a su valor natural, lo que significa que si la propiedad se hereda de forma natural, actua como inherit, de lo contrario actua como initial.