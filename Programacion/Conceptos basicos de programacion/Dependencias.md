# Dependencias

Una **dependencia** es cualquier archivo o variable que utiliza nuestro proyecto ya sea en la fase de desarrollo (cuando nosotros escribimos el codigo) o la fase de produccion (cuando el codigo final se sube al servidor). En el package.json ponemos dependencias que instalamos de terceros. Las variables no van en el package.json. 

La diferencia semántica aquí es que `dependencies` son para **uso en producción**, lo que sea que eso implique para su proyecto, son necesarias para que el proyecto funcione correctamente en produccion.

Por otro lado, `devDependencies`**son una colección de las dependencias que se usan solo en el desarrollo de su aplicación**: los módulos que usa para construirla, pero que no necesita usar cuando se está ejecutando. Esto podría incluir cosas como herramientas de prueba, un servidor local para acelerar su desarrollo y más. En `node`, una `dev dependency` podría ser `less`, con `less` generarías los hojas de estilo de tu aplicación web, no obstante cuando tu subes tu aplicación web a producción solamente subes los archivos `.css` generados por `less` , como puedes ver tu proyecto no depende de `less` en la fase de ejecución / distribución.
