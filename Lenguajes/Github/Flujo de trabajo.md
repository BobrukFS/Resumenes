# Flujo de trabajo

![[Pasted image 20221217210555.png]]
![[Pasted image 20221217210558.png]]
Git tiene tres estados principales en los que pueden residir sus archivos: **modificado (modified), preparado (staged)** y **confirmado(commited)** :

* **Modified** significa que ha cambiado el archivo pero aún no lo ha confirmado en su base de datos.

* **Staged** significa que ha marcado un archivo modificado en su versión actual para pasar a su próxima instantánea de confirmación.

* **Commited** significa que los datos se almacenan de forma segura en su base de datos local.

El **área de preparación** es un archivo, generalmente contenido en su directorio Git, que almacena información sobre lo que se incluirá en su próxima confirmación.

El **directorio de Git** es donde Git almacena los metadatos y la base de datos de objetos para su proyecto. Esta es la parte más importante de Git y es lo que se copia cuando clonas un repositorio desde otra computadora.

El flujo de trabajo básico de Git es algo así:

* Modificas archivos en tu árbol de trabajo.

* Usted organiza selectivamente solo aquellos cambios que desea que sean parte de su próxima confirmación, que agrega solo esos cambios al área de preparación.

* Realiza una confirmación, que toma los archivos tal como están en el área de preparación y almacena esa instantánea de forma permanente en su directorio de Git.

Si una versión particular de un archivo está en el directorio de Git, se considera confirmada.