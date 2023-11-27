# NPM

**Npm** es el sistema de gestion de paquetes por defecto para Node.js. Es un entorno de ejecucion para JavaScript.

Para utilizar NPM hay que installar Node.js.

**Dato**: Con && concatenamos comandos.

## Package.json

Es un archivo que se puede describir como un manifiesto de nuestro proyecto que incluye los paquetes(dependencias) y las aplicaciones de los que depende, informacion sobre su control de fuente unico y metadatos especificos como el nombre, la descripcion y el autor del proyecto.

### Metadatos

Los metadatos ayudan a identificar el proyecto y actuan como referencia para que los usuarios y colaboradores obtengan informacion sobre el proyecto.

![[Pasted image 20230524230743.png]]

### Dependencies y devDependencies

Las dependencias y devDependencies son los modulos en los que se basa el proyecto para funcionar correctamente. El package.json permite la separacion de las dependencias necesarias para la produccion y las dependencias necesarias para el desarrollo.

![[Pasted image 20230524230858.png]]

## Comandos esenciales NPM

### npm init

El comando **npm init** es una herramenta que nos permite generar nuestro package.json de nuestro proyecto. Este comando al ejecutarlo nos pedira que ingresemos en el siguiente orden los siguientes dato:

* El nombre del proyecto
* La version inicial del proyecto
* La descripcion del proyecto
* El punto de entrada del proyecto(es decir, el archivo principal del proyecto)
* El comando de prueba del proyecto
* El repositorio git del proyecto
* Las palabras clave del proyecto
* La licencia del proyecto

Podemos presionar Return o Enter para aceptar la sugerencia que proporciona npm init y pasar a la siguiente indicacion.

Una vez realizado estos pasos se generara un archivo package.json en el directorio actual.

Tambien podemos utilizar **npm init --yes** para crear el archivo package.json salteandonos los pasos ya que se completaran con valores predeterminados. Nosotros podemos configrar cuales son estos valores predeterminados con la configuracion de npm.

### npm install

Lo podemos instalar en el entorno global (lo podemos usar en cualquier lugar del equipo) utilizando **-g** o dentro de una carpeta (lo podemos hacer como una dependencia de desarrollo o como una dependencia (para el uso en produccion)) utilizando **--save-dev**.

El comando **npm install nombreModulo** sirve para instalar los modulos y dependencias que estan en package.json. Los modulos se instalaran siempre en el directorio actual. 

Ademas de activar la instalacion de un solo modulos, podemos activar la instalacion de todas las dependencias que se enumeran como dependencies y devDependencies listadas en nuestro package.json en el directorio actual, para ello utilizamos simplemente **npm install**.

Podemos instalar la version de cierto paquete, utilizando **npm install nombreModulo@version**

Podemos tambien indicar si solo queremos instalar las dependencias de produccion utilizando **npm install --production**. Si queremos instalar el paquete globalmente utilizamos **npm install -g**.

**Dato**: Para evitar poner install podemos abreviar con **i**.

#### Guardar modulos instalados como una dependencia

Al utilizar **npm install nombreModulo --save** se agregara el modulo como una dependencia de nuestro proyecto al del proyecto package.json. Si queremos agregar una dependencia de desarrollo utilizamos **--save-dev** (o **-D**).

#### Instalar modulos globalmente en su sistema

Para instalar un modulo desde npm globalmente en lugar del directorio actual, utilizamos **npm install nombreModulo --global** (o **-g**).

**Dato**: Como práctica recomendada, debe cambiar la ubicación de instalación predeterminada de un directorio del sistema a un directorio de usuario. 

#### Listar dependencias instaladas

Para ello utilizamos el comando **npm list -depth 0** para listar las dependencias en nuestro proyecto. Si queremos listar las dependencias instaladas en el ambito global utilizamos **npm list -g -depth 0**. Si quiero ver todas las dependencias instaladas utilizamos **npm list -depth**.

### Eliminar modulos

Para ello utilizamos **npm rm nombreModulo** o para eliminar una dependencia instalada en ambito global utilizamos **npm rm -g nombreModulo**.

### Actualizar modulos

Para actualizar todas nuestras dependencias a la ultima version utilizamos **npm update**

https://www.npmjs.com/

Si uso PNPM va haber conflicto de dependencias ya que movera las dependencias instaladas de pnpm a el archivo ignored.


[[Dependencias]]
[[NPM scripts]]
[[PNPM]]