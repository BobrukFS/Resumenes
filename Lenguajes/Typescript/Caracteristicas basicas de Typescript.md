# Caracteristicas basicas de Typescript

* Typescript es Javascript pero con algunas funcionalidades extras.

* Es de tipado **estatico**. Es decir que los valores de las variables NO pueden cambiar a través del tiempo.

* Para que el codigo se pueda ejecutar, hay que compilarlo o transpilarlo a javascript.

## Compilar TS

Para compilar se utiliza el comando en la terminal **tsc index.ts**
###  Configurar compilador

Si ponemos en la terminal **tsc -init** me genera un archivo **tsconfig.json** para configurar el compilador. Cada vez que inicie un directorio tengo que configurar el copilador tsc, es como cuando utilizo sass.

Ahora ya que tenemos configurado el compilador, podemos compilar utilizando el comando **tsc**.

## Depurando typescript

Para depurar tocamos el depurador, tocamos create launch json, node js. nosotros estamos depurando con node js.

Tuve que poner en launch.json "preLaunchTask" : "tsc: build - tsconfig.json"



