# Bisect

Este comando permite revisar el historial de commits y testear el proyecto, en cada uno de los puntos de restauración anteriores, para identificar dónde surgió el problema realmente.

Primero se debe iniciar la operación de bisect de Git con el subcomando **git bisect start**. El shell indica que ahora estamos en modo “Bisecting”. El paso siguiente será indicarle a Git un punto fijo en el que se considera que el proyecto funcionaba sin problemas y otro en el que ya no esté funcionando.

Para indicarle a Git qué commit es el que funciona y cuál no, se utilizan los subcomandos git bisect good y git bisect bad.

Al volver a revisar el log, se observa que Git, en lugar de hacernos avanzar commit por commit como quizás hubiéramos hecho manualmente, movió automáticamente el HEAD hasta un punto intermedio. En este punto, se pueden volver a realizar los test correspondientes para indicar, nuevamente, a Git si este commit es “bueno” o “malo”. Nuevamente Git va a mover el HEAD a un punto intermedio entre los commits que le hayamos indicado que eran “malos” y “buenos. De la misma manera, volvemos a realizar los tests para verificar el estado del programa.

Una vez terminado el proceso, se puede ejecutar el subcomando git bisect reset que volverá el HEAD a la posición original.

**Dato**: Con git checkout nos movemos entre commits.