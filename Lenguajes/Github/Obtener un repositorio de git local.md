# Obtener un repositorio de git local

Por lo general, obtiene un repositorio de Git de una de estas dos maneras:

1.  Puede tomar un directorio local que actualmente no está bajo control de versiones y convertirlo en un repositorio de Git, o

2.Puede _**clonar**_ un repositorio remoto Git existente desde otro lugar a tu repositorio local.

En cualquier caso, termina con un repositorio de Git en su máquina local, listo para trabajar.

* **Git init** : Para inicializar un directorio como repositorio git, se ejecutara dentro del directorio del proyecto, y como resultado crea un subdirectorio .git (inicializa la rama master o main, es la rama principal donde despues se van fusionar a ella las otras versiones o ramas) que contiene todos los archivos de repositorio necesarios, esta es una carpeta oculta (todas las carpetas que empiezan con . estan ocultas y se pueden ver activando la opcion de ver elementos ocultos). Si eliminamos esta carpeta .git desaparecera el historial del proyecto.

Si desea comenzar a controlar la versión de los archivos existentes (en lugar de un directorio vacío), probablemente debería comenzar a rastrear esos archivos y realizar una confirmación inicial. Puede lograrlo con algunos comandos git add que especifican los archivos que desea rastrear, seguidos de un git commit para mandarlos al repositorio .git.

·         **Git clone url opcional nombre de un nuevo directorio en donde se agrega** : Si desea obtener una copia de un repositorio de Git existente, por ejemplo, un proyecto al que le gustaría contribuir

## Comandos básicos

* **ls** : Nos da un listado de todas las carpetas y archivos que hay en nuestra ubicación.

* **ls -a** : Muestra las carpetas ocultas, como .git.

* **pwd** : Es para saber en que carpeta nos encontramos.

* **cd carpeta a la cual nos queremos mover** : Para moverse a una carpeta.

* **cd ..** : Sirve para salirnos 1 carpeta.

* **mkdir nombre de la carpeta** : Es para crear una carpeta con dicho nombre.

* **code .** : Abre la carpeta en la que nos ubicamos con visual code studio

* **touch archivo** : Para crear un archivo.

**Dato:** Si el nombre es de dos palabras se puede utilizar ' ' para poner varias palabras.

[[Registro de cambios en el repositorio]]
[[Confirmar cambios]]
[[Eliminacion de archivos]]
[[Mover archivos]]
[[Deshacer cosas]]