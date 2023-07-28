# Configuracion de git por primera vez

* **Git config** : Permite obtener y establecer variables de configuración que controlan todos los aspectos de como se ve y opera git. Estas variables se pueden almacenar en tres lugares diferentes:

![[Pasted image 20221217210839.png]]

* **git config --global user.name “nombre” :** Para establecer el nombre de usuario para todos los repositorios.

* **git config --global user.email email** : Para establecer el email para todos los repositorios.

Si desea anular esto con un nombre o dirección de correo electrónico diferente para proyectos específicos, puede ejecutar el comando sin la opción –-global  cuando esté en ese proyecto y poner **--local**.

* **git config --global -e :** Nos muestra la configuración global que tenemos, también se puede utilizar git  config --list. Para salir del modo edición ponemos **:q.**

* **git config --global core.autocrlf true**

* **git config –global init.defaultBranch nombre :** Su nombre de sucursal predeterminado

Por defecto, Git creará una rama llamada master cuando crees un nuevo repositorio con git init. Con este comando podemos cambiar el nombre.

* **Git config -h :** Nos da un listado de todas las configuraciones posibles

* **Git help verbo**: Para ver la lista en lo que nos puede ayudar git, luego agregamos el verbo. Por ejemplo git help config.

Para ver la configuracion de git:

* **git config --list** : Para verificar las configuraciones que se hayan hecho en el sistema.

* **git config --list --show-origin** : Para ver todas las configuraciones y donde se encuentra cada una.