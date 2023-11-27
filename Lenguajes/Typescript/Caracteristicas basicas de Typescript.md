# Caracteristicas basicas de Typescript

* Typescript es Javascript pero con algunas funcionalidades extras.

* Es de tipado **estatico**. Es decir que los valores de las variables NO pueden cambiar a través del tiempo.

* Para que el codigo se pueda ejecutar, hay que compilarlo o transpilarlo a javascript. Es decir, typescript es estatico solo funciona en tiempo de compilacion.

* TypeScript y JavaScript tienen total interoperabilidad, lo que significa que puede usar código TypeScript en proyectos JavaScript y viceversa. TypeScript es un superconjunto de JavaScript, lo que significa que cualquier código JavaScript válido también es código TypeScript válido.

## Compilar TS

Para nstalar el compilador debemos poner

```npm
npm install -g typescript
```

Para compilar se utiliza el comando en la terminal **tsc index.ts**
### Configurar compilador

Si ponemos en la terminal **tsc -init** me genera un archivo **tsconfig.json** para configurar el compilador. Cada vez que inicie un directorio tengo que configurar el copilador tsc, es como cuando utilizo sass.

- `target`: la versión de JavaScript para compilar.
- `module`: el sistema de módulos a utilizar.
- `strict`: habilita/deshabilita la verificación estricta de tipos.
- `outDir`: el directorio para generar los archivos JavaScript compilados.
- `rootDir`: el directorio raíz de los archivos TypeScript.
- `include`: una serie de patrones de archivos/directorios para incluir en la compilación.
- `exclude`: una serie de patrones de archivos/directorios para excluir de la compilación.

Ahora ya que tenemos configurado el compilador, podemos compilar utilizando el comando **tsc** seguido del nombre del archivo para compilar.

### ts-node

Con ts-node podemos ejecutar eficientemente scripts typescript mediante el comando npx ts-node index.ts.

```npm
npm install ts-node
```

