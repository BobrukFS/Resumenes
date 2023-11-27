# Modulo Operating System

Este modulo nos va a permitir obtener informacion sobre el sistema operativo en el cual se ejecuta la aplicacion. Este modulo no es un modulo que este disponible de forma global por lo que debemos importarlo con require.

```js
const os = require('os');
```

Algunas de las propiedades y métodos más útiles del módulo `os` son:

* **os.type()**: Devuelve el tipo de sistema operativo
- **os.arch():** Devuelve la arquitectura del sistema operativo.
- **os.cpus():** Devuelve una matriz de objetos que representan las CPU del sistema operativo.
- **os.freemem():** Devuelve la cantidad de memoria libre disponible en el sistema operativo.
- **os.hostname():** Devuelve el nombre de host del sistema operativo.
- **os.platform():** Devuelve la plataforma del sistema operativo (por ejemplo, `linux`, `darwin`, `windows`).
- **os.tmpdir():** Devuelve la ruta al directorio temporal del sistema operativo.