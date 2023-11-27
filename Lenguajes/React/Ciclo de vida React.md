# Ciclo de vida React

El ciclo de vida de un componente es el conjunto de pasos secuenciales que transcurren **desde que se inserta un componente en la interfaz hasta que es quitado y limpiada la memoria**.

A grandes rasgos, cuando se trata de gestionar a los componentes de una interfaz, React tiene tres tareas principales:

1. La primera tarea es el **montado**. Montar un componente significa **insertarlo en el VirtualDOM** de la página.
2. Una vez que el componente está montado, debe reaccionar a los cambios en los datos a través de la **actualización**. La actualización se dispara al cambiar el estado o el valor de las props de un componente y ocasiona que se vuelva a procesar con los nuevos datos.
3. Finalmente, cuando el componente debe ser quitado de la interfaz, se procede con el **desmontado**. En esta fase el componente se quita y se liberan los recursos utilizados.

## Ciclo de vida en componentes funcionales

### Montado

Se llama a la funcion y el retorno de la funcion es el componente que se inserta en el DOM. React lee la funcion una sola vez al inicio. El montado, sera el unico lugar donde se procese un codigo diferente al que esta retornado (el cuerpo de la funcion). Tambien va a inicializar todos los hooks necesarios.
### Actualizacion

La actualizacion es ocasionado por un cambio de estado o props. Consiste en volver a ejecutar el elemento JSX retornado por la funcion (y no toda la misma).
### Desmontado
El desmontado consiste en la liberacion de forma automatica de todos los recursos consumidos por la funcion.