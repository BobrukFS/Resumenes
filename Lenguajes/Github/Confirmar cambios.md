
# Confirmar cambios

Ahora que su área de preparación está configurada de la manera que desea, puede confirmar sus cambios. Recuerde que cualquier cosa que aún no esté preparada (cualquier archivo que haya creado o modificado que no haya ejecutado git add desde que los editó) no entrará en esta confirmación. La forma más sencilla de confirmar es escribir **git commit.** Luego toco I y empezamos a escribir descripcion del commit (ya que el commit genera una version), luego tocamos la tecla esc y :wq para salir.

Mas simplificado se puede hacer con **git commit -m “referencia al cambio”**

Cada commit tiene su codigo unico. Con git **checkout codigo** nos podemos ir al commit que hace referencia el codigo unico. Si quiero volver a la rama master el cabezal pongo git checkout master

Cada vez que hagamos un commit estaremos generando una nueva versión del proyecto, o snapshot, la cual podemos revertir o comparar luego. En cada confirmacion de cambios git almacena un punto de control que conserva:

* Un apuntador a la copia puntual de los contenidos preparados (staged).

* Metadatos con el autor y el mensaje explicativo.

* Uno o varios apuntadores a las confirmaciones que sean padres directos de esta.

![[Pasted image 20230702152906.png]]

## Saltarse el área de preparación

Si desea omitir el área de preparación, Git proporciona un atajo simple. Agregar la opción **-a** al comando git commit hace que Git organice automáticamente todos los archivos que ya se rastrean antes de realizar la confirmación, lo que le permite omitir la parte de git add. 

**git commit -am “referencia al cambio”**

## Visualizacion del historial de confirmaciones
La herramienta más básica y poderosa para mirar el historial de confirmaciones es el comando **git log** que muestra los logs de los commits (vemos que las primeras 6 caracteres de codigo es el codigo unico pero que no esta en su version simplificada). Hay otros comandos:

* **git log –oneline** : Muestra los cambios en los commits simplificados.

* **git log –oneline –graph** que muestra graficos de los commits.

De forma predeterminada, sin argumentos, git log enumera las confirmaciones realizadas en ese repositorio en orden cronológico inverso; es decir, las confirmaciones más recientes aparecen primero. Como puede ver, este comando enumera cada confirmación con su suma de verificación SHA-1, el nombre y el correo electrónico del autor, la fecha de escritura y el mensaje de confirmación.

![[Pasted image 20221217224911.png]]
## Git reset

* **git reset codigo de commit --hard** : Este comando va a devolver la version especificada en el codigo de confirmacion y va a eliminar todas las posteriores. Si en vez de –hard utilizamos –soft, las versiones posteriores se eliminaran del commit pero se conservaran los cambios en el area de preparacion.

* **git reset HEAD archivo** : Devuelve el archivo especificado del commit.

* **git reset –soft HEAD^ :** Devuelve el ultimo commit que se hizo y pone los cambios en staging.

* **Git reset –hard HEAD^ :** Devuelve el ultimo commit y todos los cambios.

* **Git reset –hard HEAD^^** : Devuelve los 2 ultimo commit y todos los cambios.

