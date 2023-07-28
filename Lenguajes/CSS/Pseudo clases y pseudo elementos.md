# Pseudo clases y pseudo elementos

## Pseudoclases

Las **pseudoclases** permite seleccionar a un elemento cuando esta en un estado particular.

* **:hover** : La pseudoclase **:hover** selecciona un elemento solo cuando el puntero del mouse se desplaza sobre el.

* **:active** : La pseudoclase **:active** selecciona un elemento solo cuando el usuario presiona el boton primario del mouse y termina cuando se suelta.

* **:focus** : La pseudoclase **:focus** representa un elemento que ha recibido el foco. Generalmente se activa cuando el usuario hace click.

* **:link** : La pseudoclase **:link** representa a un elemento que aun no se ha visitado.

* **:visited** : La pseudoclase **:visited** representa enlaces que el usuario ya ha visitado.

* **:root** : La pseudoclase **:root** selecciona el elemento raiz de un arbol que representa el documento. Esto generalmente sirve para hacer paletas con variables CSS.

* **:required**: La pseudoclase **:required** selecciona al elemento que no ha sido completado y requiere que se complete.

* **:user-invalid**: La pseudoclase **:user-invalid** selecciona al elemento que no ha sido valido despues de la interaccion del usuario.

* **:invalid**: La pseudoclase **:invalid** selecciona a aquellos elementos que no ha sido validados.

* **:valid** : La pseudoclase **:valid** selecciona al elemento que ha sido validado.

* **:checked** : La pseudoclase **:checked** selecciona al elemento checkeado.

* **:nth-child(valor)** : Este pseudoelemento selecciona un elemento de una lista de elementos hermanos hijos del elemento seleccionado, que se encuentra en la posición especificada por el valor entre paréntesis. Si ponemos de valor odd (selecciono a los impares), si ponemos de valor even (selecciono a los pares). Si por ejemplo pongo 3n+4 selecciono 4, 7, 10, 13, etc.

* **:nth-of-type(valor):** Este pseudoelemento selecciona un elemento de una lista de elementos del mismo tipo.

* **:first-child** : Este pseudoelemento selecciona el primer elemento de una lista de elementos hermanos.

* **:last-child** : Este pseudoelemento selecciona el último elemento de una lista de elementos hermanos.

* **:only-child** : Este pseudoelemento selecciona un elemento cuando es el único hijo de otro elemento.

* **:first-of-type** : Este pseudoelemento selecciona al primer elemento hijo de un tipo especifico.

* **:last-of-type** : Este pseudoelemento selecciona al ultimo elemento hijo de un tipo especifico.

## Pseudoelementos

Los **pseudoelementos** seleccionan una determinada parte de un elemento en lugar del elemento en si.

* **::before(antes)** : crea un pseudoelemento que es el primer hijo del elemento seleccionado. A menudo se usa para agregar contenido cosmético a un elemento con la propiedad **content**. 

* **::after(despues)** : crea un pseudoelemento que es el último hijo del elemento seleccionado. A menudo se usa para agregar contenido cosmético a un elemento con la propiedad **content**.

[[Content]]