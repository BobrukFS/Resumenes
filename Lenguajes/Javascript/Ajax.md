
# Ajax (Javascript asincrono y xtml)

Ajax es una tecnología que permite hacer consultas por HTTP de manera asíncrona contra el servidor. Ajax permite acceder a datos existentes en el servidor sin necesidad de recargar la pagina completamente. Estas consultas contra el servidor se realizan por medio de Javascript y los datos se procesan mediante este mismo lenguaje, permitiendo actualizar el contenido de la pagina justamente donde sea preciso.

El hecho de que Ajax sea asíncrono indica que el flujo de ejecución de solicitudes al servidor sigue ese patrón comentado. Cuando se hace la solicitud, el navegador se queda esperando una respuesta del servidor por un tiempo indeterminado. Sin embargo, durante ese tiempo de espera, el motor de Javascript permanece ocioso, o simplemente realizando otras tareas. Ese es el motivo por el que el navegador no se queda bloqueado esperando la solicitud del servidor, sino que el usuario puede continuar trabajando con la página. Una vez el servidor responde y nos llega la señal de retorno, se recibe el dato que el servidor pueda habernos hecho llegar. Ese dato puede ser tratado mediante código Javascript, para mostrarlo en el lugar donde se desee de la página, para mostrar un mensaje de éxito, error, etc.

Para implementar AJAX utilizamos el objeto **XMLHttpRequest** o **FETCH**.

[[Objeto XMLHttpRequest]]
[[Fetch]]