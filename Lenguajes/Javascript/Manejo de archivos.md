# Manejo de archivos

Nosotros al realizar peticiones podemos obtener texto, objetos, numeros, pero no podemos manejar imagenes, audios, etc. Es por ello que contamos con la API BLOB y la API URL que nos permiten manejar por ejemplo una imagen que nos devuelve el servidor o una api.

```js
// Realizar una petición HTTP para obtener la imagen
var request = new XMLHttpRequest();
request.open('GET', 'https://example.com/image.jpg');
request.responseType = 'blob';
request.onload = function() {
  // Obtener el objeto Blob
  var blob = request.response;

  // Crear una imagen con el objeto Blob
  var image = new Image();
  image.src = window.URL.createObjectURL(blob);

  // Mostrar la imagen en la página web
  document.querySelector('img').src = image.src;
};
request.send();
```

