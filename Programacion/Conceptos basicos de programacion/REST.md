# REST

La arquitectura **REST (Representative State Transfer)** es un estilo de arquitectura de software para sistemas distribuidos que utiliza el protocolo HTTP para intercambiar información entre clientes y servidores.

REST se basa en los siguientes principios:

- **Interfaz uniforme:** Los recursos se identifican mediante **URI (Uniform Resource Identifiers)** y se accede a ellos mediante métodos HTTP. 
- **Representación de estado transferencial:** Los recursos se representan mediante formatos de datos estándar, como JSON o XML.
- **Sin estado:** Los clientes y servidores no necesitan mantener ningún estado entre solicitudes. Es decir, cada operacion debe contar con todo lo que necesita para funcionar en si misma. Una arquitectura sin estado significa que la petición contiene en sí misma todo lo necesario, sin necesidad de datos extra en el servidor.
- **Cliente-servidor:** El cliente y el servidor son componentes separados y autónomos. 
- **Cacheo:** Los clientes pueden almacenar en caché las respuestas del servidor para mejorar el rendimiento.
- **Computación capa por capa:** Las aplicaciones REST se pueden diseñar en capas para facilitar el mantenimiento y la escalabilidad.

Los endpoints REST son puntos de acceso a los recursos de un sistema REST. Cada endpoint se identifica mediante una URI y se puede acceder a él mediante un método HTTP.

Los métodos HTTP más comunes utilizados en REST son:

- **GET:** Obtiene un recurso.
- **POST:** Crea un nuevo recurso.
- **PUT:** Actualiza un recurso existente.
- **DELETE:** Elimina un recurso existente.

La arquitectura REST tiene una serie de ventajas, entre ellas:

- **Simplicidad:** REST es un estilo de arquitectura relativamente simple de entender y implementar.
- **Escalabilidad:** REST es escalable a grandes volúmenes de tráfico.
- **Portabilidad:** REST es un estándar abierto que puede ser utilizado por una amplia gama de aplicaciones.

```jsx
// En el servidor

app.delete('/users/:id', (req, res) => {
  const id = req.params.id;

  // Elimina el recurso del servidor

  // ...

  res.status(200).json({ message: 'Recurso eliminado' });
});

// En el cliente

const response = await fetch('https://api.example.com/users/12345', {
  method: 'DELETE',
});//Se enviara la peticion al endpoint que sea users y coincida con el metodo, es decir, delete, si habria dos endpoints con la misma URI y el mismo meotod se eligiria el primero, igualmente no tendria que porque suceder.

if (response.ok) {
  // El recurso se eliminó correctamente
} else {
  // Ocurrió un error al eliminar el recurso
}

```
## URI

La URI es el identificador único para cada recurso. La URI debe ser corta, describir con precision el recurso, debe centrarse en el recurso y no en la accion ya que la accion se delega al metodo por el cual se accede a la URL, y puede contener parametros.

Ejemplo de una buena URIs: /productos, /usuarios/:id

[[Peticiones HTTPS]]