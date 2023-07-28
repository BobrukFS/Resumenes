# Trabajando con APIs

El problema con el modelo tradicional de paginas web es que si queremos realizar una busqueda debemos cargar toda la pagina, incluso cuando solo necesitamos actualizar una parte de ella. Esto es ineficiente y puede resultar en una mala experiencia del usuario. 

![[Pasted image 20230526200958.png]]
Entonces, en lugar del modelo tradicional, muchos sitios web usan APIs de JS para solicitar datos del servidor y actualizar el contenido de la pagina sin volver a cargar la pagina. Entonces, cuando el usuario por ejemplo busca un nuevo producto, el navegador solo solicita los datos que se necesitan para actualizar la pagina.

![[Pasted image 20230526201111.png]]

Esto permite que JS se ejecute en una pagina para realizar una solicitud HTTP a un servidor para recuperar recursos especificos. Cuando el servidor los proporciona, JavaScript puede usar los datos para actualizar la pagina, generalmente mediante el uso de la API de manipulacion de DOM. Los datos solicitados suelen ser en JSON pero tambien puede ser XML, HTML o texto.

### Ventajas

* Las actualizaciones de la página son mucho más rápidas y no tiene que esperar a que la página se actualice, lo que significa que el sitio se siente más rápido y con mayor capacidad de respuesta.

* Se descargan menos datos en cada actualización, lo que significa menos ancho de banda desperdiciado. 

* Para acelerar aún más las cosas, algunos sitios también almacenan activos y datos en la computadora del usuario cuando se solicitan por primera vez, lo que significa que en visitas posteriores utilizan las versiones locales en lugar de descargar copias nuevas cada vez que se carga la página por primera vez. El contenido solo se recarga desde el servidor cuando se ha actualizado.

[[Ajax]]
[[Axios]]