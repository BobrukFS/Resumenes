# Registro de cambios en el repositorio
Recuerde que cada archivo en su directorio de trabajo puede estar en uno de dos estados: _**rastreado**_ _**(tracked)**_ o _**no rastreado**_ _**(untracked)**_ . Los **archivos rastreados** son archivos que estaban en la última instantánea, así como cualquier archivo recién preparado; pueden ser sin modificar, modificados o escalonados. En resumen, los archivos rastreados son archivos que Git conoce.

Los **archivos sin seguimiento** son todo lo demás: cualquier archivo en su directorio de trabajo que no estaba en su última instantánea y que no está en su área de preparación. Cuando clone un repositorio por primera vez, todos sus archivos serán rastreados y no modificados porque Git los revisó y no ha editado nada.

A medida que edita archivos, Git los ve como modificados, porque los ha cambiado desde su última confirmación. A medida que trabaja, prepara selectivamente estos archivos modificados y luego confirma todos esos cambios preparados, y el ciclo se repite.

![[Pasted image 20221217224120.png]]
## Comprobacion del estado de sus archivos
La herramienta principal que utiliza para determinar qué en qué estado están los archivos es el comando :

* **git status :** Este comando nos muestra el estado de nuestros archivos . En rojo tenemos a los archivos que estan en la working area, y en verde los que estan en la stage area.

* **git status -s** : Es el formato corto de git status donde M significa que el archivo fue modificado, si es rojo no fue agregado al stage y si es verde fue agregado. El ? significa que el archivo no fue agregado para que git haga el seguimiento. Los archivos nuevos que se agregaron al area de preparacion tienen un A.
## Seguimientos de nuevos archivos
Para comenzar a rastrear un nuevo archivo, tenemos los comandos:

* **git add archivo :** Este comando sirve para añadir a nuestra etapa de stage el archivo especificado. Puedo agregar varios separando por espacios los nombres de los archivos.

* **git add `*`** : Agrega todos los archivos en el directorio actual, excepto los archivos cuyo nombre comience con un punto.

* **git add .** : Agrega todos los archivos en el directorio actual incluyendo los archivos cuyo nombre comience con un punto. 

* **git add \*extension :** Este comando añade a todos los archivos de la misma extension del directorio actual para luego ser confirmados sus cambios.

* **git add directorio/\*extension :** Este comando añade a todos los archivos de la misma extension del directorio especificado para luego ser confirmados sus cambios.

* **git add directorio/`*`** : Este comando añade a todos los archivos del directorio especificado para luego ser confirmados sus cambios.

* **git add -i** : Este comando hace que ingresemos a un stage interactivo.

El archivo estará rastreado y listo para ser confirmado. Puede ser útil pensar en ello más como "agregar precisamente este contenido a la próxima confirmación" en lugar de "agregar este archivo al proyecto". Luego de la creación, modificación o eliminación de un archivo, los cambios quedan únicamente en el área de trabajo, por lo tanto es necesario pasarlos al área de preparación mediante el uso del comando git add , para que sea incluido dentro de la siguiente confirmacion.

## Seguimiento de nuevos archivos
Si cambia un archivo previamente rastreado, al poner git status aparece en una sección denominada "Cambios no preparados para confirmación", lo que significa que un archivo del que se realiza un seguimiento se ha modificado en el directorio de trabajo pero aún no está preparado. Para prepararlo, ejecuta el comando git add.
## Visualizacion de sus cambios preparados y no preparados
Si el comando git status es demasiado vago para usted (quiere saber exactamente qué cambió, no solo qué archivos se cambiaron), puede usar el comando **git diff**. Esto nos muestra las diferencias al modificar un archivo. Ese comando compara lo que está en su directorio de trabajo con lo que está en su área de preparación. El resultado le indica los cambios que ha realizado y que aún no ha realizado. Es importante tener en cuenta que git diff por sí solo no muestra todos los cambios realizados desde su última confirmación, solo los cambios que aún no están preparados. Si ha preparado todos los cambios, git diff no obtendrá ningún resultado.

**Git diff --staged** nos muestra todos los cambios que se encuentran en la etapa stage.
