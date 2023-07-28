# Caracteristicas basicas de Github

Es un **sistema de control de versiones.** Estos sistemas son herramientas que permiten realizar un seguimiento de los cambios y también permitir proteger el código de errores humanos accidentales.

Git piensa en sus datos más como una serie de instantáneas de un sistema de archivos en miniatura. Con Git, cada vez que confirma o guarda el estado de su proyecto, Git básicamente toma una imagen de cómo se ven todos sus archivos en ese momento y almacena una referencia a esa instantánea. Para ser eficiente, si los archivos no han cambiado, Git no vuelve a almacenar el archivo, solo un enlace al archivo anterior idéntico que ya ha almacenado. Git piensa en sus datos más como un **flujo de instantáneas** .

Todo en Git se suma antes de que se almacene y luego se hace referencia a esa suma de verificación. Esto significa que es imposible cambiar el contenido de cualquier archivo o directorio sin que Git lo sepa.

El mecanismo que usa Git para esta suma de verificación se llama **hash SHA-1**. Esta es una cadena de 40 caracteres compuesta por caracteres hexadecimales (0–9 y a–f) y calculada en función del contenido de una estructura de archivo o directorio en Git. Un hash SHA-1 se parece a esto:

![[Pasted image 20221217205533.png]]

**El uso de un sistema de control de versiones tiene tres ventajas principales:**

1. Gracias al historial de cambios se puede saber el autor, la fecha y notas escritas sobre los cambios realizados. También permite volver a versiones anteriores para ayudar a analizar causas raíces de errores y es crucial cuando hay que solucionar problemas de versiones anteriores.

2. Creación y fusión de ramas. Al tener varios integrantes del equipo trabajando al mismo tiempo, cada uno en una tarea diferente, pueden beneficiarse de tener flujos de trabajo independientes. Posteriormente se pueden fusionar estos flujos de trabajos o ramas a una principal.

3. Trazabilidad de los cambios que se hacen en el software. Poder conectar el sistema de control con un software de gestión de proyectos y seguimiento de errores, ayuda con el análisis de la causa raíz de los problemas y con la recopilación de información.  

El concepto de **versión** (también llamado revisión o edición) de un proyecto (código fuente) hace referencia al estado en el que se encuentra el mismo en un momento dado de su desarrollo o modificación. Los sistemas de control de versiones utilizan repositorios para almacenar el proyecto actualizado junto a sus cambios históricos. Los **sistemas de control de versiones centralizados** almacenan todo el código en un único repositorio, es decir que un único servidor contiene todos los archivos versionados. Esto representa un único punto de falla dado que si el servidor no está disponible por un tiempo nadie podrá colaborar o guardar cambios en archivos en los que hayan estado trabajando.

**Los sistemas de control de versiones distribuidos** permiten en cambio continuar el trabajo aún cuando el repositorio de referencia no está disponible. En estos sistemas los clientes no solo descargan la última copia del código, sino que se replica completamente el repositorio con los cambios históricos (versiones).

De esta manera, si un servidor deja de funcionar y estos sistemas estaban colaborando a través de él, cualquiera de los repositorios estarán disponibles para los clientes y puede ser copiado al servidor con el fin de restaurarlo.

## Shortcuts en git bash

* SHIFT + INSERT : Me permite pegar.

 * La tecla q sirve para cuando se bloquea la consola.
 
 * Si pongo ; puedo seguir con otro comando sin ejecutarlo. Asi puedo concatenar comandos.
 
 * Si dejo espacio puedo concatenar varias selecciones, etc. Ejemplo git add index.html style.css. Entonces añado a la etapa de stage dos archivos.