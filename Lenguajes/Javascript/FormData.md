# FormData

**FormData** es una interfaz que proporciona una forma de construir un conjunto de pares clave/valor que representan campos de formulario y sus valores, que se pueden enviar utilizando los metodos fetch(), XMLHttpRequest.send() o navigator.sendBeacon(). Al usar new FormData() estamos creando un nuevo objeto FormData.

## Metodos

* **FormData.append()** :  Agrega un nuevo valor a una clave existente dentro de un objeto `FormData`, o agrega la clave si aún no existe.

* **FormData.delete()** : Elimina un par clave/valor de un objeto `FormData`. 

* **FormData.entries()** : Devuelve un iterador que itera a través de todos los pares clave/valor contenidos en el `FormData`.

* **FormData.get(clave)** : Devuelve el primer valor asociado con una clave determinada desde dentro de un objeto `FormData`.

* **FormData.getAll(clave)** : Devuelve una matriz de todos los valores asociados con una clave dada desde dentro de un archivo `FormData`.

* **FormData.has(clave)** : Devuelve true si un objeto `FormData` contiene una determinada clave.

* **FormData.keys() :** Devuelve un iterador que recorre en iteración todas las claves de los pares clave/valor contenidos en el `FormData`.

* **FormData.set()** : Establece un nuevo valor para una clave existente dentro de un objeto `FormData` o agrega la clave/valor si aún no existe.

* **FormData.values()** : Devuelve un iterador que recorre en iteración todos los valores contenidos en `FormData`.
## Ventajas y desventajas

### Ventajas:

- Ideal para enviar datos de formularios tradicionales que contienen campos de texto, selecciones, casillas de verificación, etc.

- Puede manejar fácilmente el envío de archivos binarios, como imágenes y archivos adjuntos.

### Desventajas:

- Requiere configurar el encabezado `'Content-Type': 'multipart/form-data'`.

- Puede ser un poco más complejo de construir y manejar en el frontend.

- No es tan intuitivo para enviar datos estructurados en comparación con JSON.