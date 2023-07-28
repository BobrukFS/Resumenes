# Validacion de formularios con JS

Para mejorar mas la validacion de los formularios, se puede utilizar la API de validacion de restricciones de JavaScript.

La API de validacion de restricciones consta de un conjunto de metodos y propiedades disponibles en las siguientes interfaces DOM de elementos de formulario:

* **HTMLButtonElement** (Representa al elemento button)
* **HTMLFieldSetElement** (Representa al elemento fieldset)
* **HTMLInputElement** (Representa al elemento input)
* **HTMLOutputElement** (Representa al elemento output)
* **HTMLSelectElement** (Representa al elemento select)
* **HTMLTextAreaElement** (Representa al elemento textarea)

La API de validación de restricciones hace que las siguientes propiedades estén disponibles en los elementos anteriores.

* **validationMessage**: Devuelve un mensaje localizado que describe las restricciones de validacion que el control no cumple (si las hay).

* **validity** : Devuelve un objeto ValidityState que contienen varias propiedades que describen el estado de validez del elemento.

* **willValidate** : Devuelve true si el elemento se validara cuando se envie el formulario; false de lo contrario.

La API de validacion de restricciones tambien pone a disposicion los siguientes metodos:

* **checkValidity()**: Devuelve **true** si el valor del elemento no tiene problema de validez; de lo contrario devuelve false. Si el elemento no es valido, este metodo tambien activa un evento invalid.

* **reportValidity()**: Reporta campos invalidos usando eventos.

* **setCustomValidity(message)** : Agrega un mensaje de error personalizado al elemento; si establece un mensaje de error personalizado, se considera que el elemento no es valido y se muestra el error especificado.

## Proporcionar mensajes de error significativos

Para lograr esto hay que utilizar **setCustomValidity()**

```js

//Ejemplo

const nameInput = document.querySelector('[name="name"]');  
  
nameInput.addEventListener('invalid', () => {  
nameInput.setCustomValidity('Please enter your name.');  
});
```

Con el evento onblur, valida la entrada cuando un usuario abandona un campo del formulario.