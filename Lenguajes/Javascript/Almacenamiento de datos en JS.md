# Almacenamiento de datos en JS

Para almacenar datos en JS podemos utilizar cookies, la api llamada Storage, cache y el api IndexedDB que nos permite tener un tipo de base de datos relacional en el navegador. 

**Dato**: En la consola en Application podemos observar esto.

## API Storage

La **interfaz de la API de almacenamiento web** proporciona acceso al almacenamiento de la sesión o al local para un dominio particular. Esto le permite, por ejemplo, agregar, modificar o eliminar elementos de datos almacenados.

Si deseas manipular el almacenamiento de sesión para un dominio, llama al método **Window.sessionStorage.** Este método permite acceder a un objeto de almacenamiento de sesión para el origen actual. Los datos almacenados se borran cuando finaliza la sesion de la pagina. Una sesión de página dura todo el tiempo que el navegador está abierto y sobrevive a las recargas y restauraciones de página. Abrir una página en una nueva pestaña o ventana provocará que se inicie una nueva sesión, que difiere de cómo funcionan las cookies de sesión.

Si deseas manipular el almacenamiento local de un dominio, llama a **Window.localStorage**. La propiedad localStorage de solo lectura permite acceder a un objeto con la capacidad de persistir información en la memoria del navegador. Es decir, los datos almacenados se guardan en las sesiones. Los objetos de almacenamiento son simples almacenes de clave-valor, similares a los objetos, pero se mantienen intactos a través de las cargas de página. Las claves y los valores son siempre cadenas (tener en cuenta que las claves enteras se convertirán automáticamente en cadenas, al igual que lo hacen los objetos). Puedes acceder a estos valores como un objeto o con los métodos localStorage.getItem() y localStorage.setItem().

* **setItem(key, value)** : Agrega esa clave al almacenamiento o actualizara el valor de esa clave si ya existe. Si el almacenamiento esta lleno arroja una excepcion.
* **getItem(key, value)**: Este metodo lo que hace es devolver el valor de la clave que pasemos si es que se encuentra. 
* **clear()**: Limpia el localStorage.
* **removeItem(key)**: Elimina el dato almacenado segun la key.

  
El evento `storage` se produce cuando se modifica el almacenamiento local o de sesión de una página web. Este evento se puede utilizar para detectar cambios en los datos almacenados y actualizar la página en consecuencia.

El evento `storage` tiene las siguientes propiedades:

- `key`: La clave del elemento de almacenamiento que se ha modificado.
- `oldValue`: El valor antiguo del elemento de almacenamiento.
- `newValue`: El nuevo valor del elemento de almacenamiento.
- `url`: La URL de la página web que ha modificado el almacenamiento.

```js
window.addEventListener("storage", (event) => {
  if (event.key === "nombre") {
    console.log("El nombre de usuario ha cambiado de", event.oldValue, "a", event.newValue);
  }
});
```
## Cookies  
Las cookies son pequeños archivos de texto que los sitios web almacenan en tu navegador. Se utilizan para recordar información sobre ti, como tus preferencias, inicios de sesión y carritos de la compra.

En JavaScript, puedes usar el objeto `document.cookie` para crear, leer, actualizar y eliminar cookies.

Las cookies en JavaScript tienen las siguientes propiedades:

- **name:** El nombre de la cookie.
- **value:** El valor de la cookie.
- **domain:** El dominio al que pertenece la cookie.
- **path:** La ruta en el dominio al que pertenece la cookie.
- **expires:** La fecha de caducidad de la cookie.
- **secure:** Si la cookie solo se puede enviar a través de conexiones seguras.
- **httpOnly:** Si la cookie solo se puede acceder a través de HTTP.