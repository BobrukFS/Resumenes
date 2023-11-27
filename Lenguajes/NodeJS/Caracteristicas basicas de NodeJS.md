# Caracteristicas basicas de NodeJS

NodeJS es un entorno de ejecucion de Javascript. Es decir la infraestructura en la que se ejecuta la aplicacion.

Node utiliza un modelo de entrada (de solicitudes) y salida (de respuestas) **sin bloqueo controlado por eventos**. Esto es lo que hace que este sistema sea ligero y mantenga una altísima eficiencia aún cuando usamos aplicaciones en tiempo real. Puede referirse a cualquier operación, desde leer o escribir archivos de cualquier tipo hasta hacer una solicitud HTTP. 

Al ser capaz de manejar múltiples conexiones en simultáneo con un alto nivel de rendimiento, Node.js se vuelve una excelente herramienta para crear aplicaciones de red rápidas y de alto rendimiento.

![[Pasted image 20231005141126.png]]
![[Pasted image 20231005141133.png]]

Mientras que las técnicas de servicio web generan un nuevo subproceso con cada conexión (hilo o thread) y ocupan la RAM del sistema, Node.js opera en un solo subproceso: utiliza el modelo de entrada y salida sin bloqueo de la salida y, por eso, logra soportar decenas de miles de conexiones en simultáneo mantenidas en el bucle de eventos. Es decir, esta **orientado a eventos asincronos.**

Podemos decir que Node.js está controlado por eventos:

● Frente a una nueva solicitud se genera un tipo de evento. 

● Inmediatamente, el servidor lo procesa y, frente a la operación de bloqueo de entrada y salida, no espera a que esté completa y devuelve esa orden. 

● En ese momento, el servidor empieza a procesar un nuevo evento y, tras finalizar la operación de entrada y salida continúa trabajando en la solicitud ejecutando la devolución de llamada tan pronto como tenga tiempo.

Como el servidor nunca necesita crear más subprocesos, tiene muy poca sobrecarga.

## Usar NodeJS REPL (interprete interactivo)

Node.js REPL (Read Eval Print Loop: intérprete interactivo) representa un entorno informático, similar a la terminal del sistema Windows o la consola de Unix y Linux, donde podemos introducir el comando en una terminal y recibir la respuesta del sistema.






Para empezar un servidor hacemos node nombreDelArchivo o podemos utilizar nodemon para que cada vez que se actualice el servidor no haya que cerrarlo ya brirlo nuevamente.

[[NPM]]