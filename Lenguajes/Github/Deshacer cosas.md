# Deshacer cosas
Uno de los deshacer comunes tiene lugar cuando se confirma demasiado pronto y posiblemente se olvida de agregar algunos archivos, o se estropea el mensaje de confirmación. Si desea rehacer esa confirmación, realice los cambios adicionales que olvidó, organícelos y confirme nuevamente usando la opción **git commit --amend**:

![[Pasted image 20221217225240.png]]
O mismo para especificar un nuevo mensaje podemos utilizar **git commit -–amend -m “texto a especificar”.**

Este comando toma su área de preparación y la usa para la confirmación. Si no ha realizado cambios desde su última confirmación (por ejemplo, ejecuta este comando inmediatamente después de su confirmación anterior), su instantánea se verá exactamente igual y todo lo que cambiará es su mensaje de confirmación.

Se activa el mismo editor de mensajes de confirmación, pero ya contiene el mensaje de su confirmación anterior. Puede editar el mensaje como siempre, pero sobrescribe su confirmación anterior.

Tengamos en cuenta que si ya estamos trabajando con repositorios remotos (lo veremos más adelante en el curso) y hemos subido el último commit a nuestro servidor distribuido, no debemos cambiar nada del último commit, ya que al hacerlo estamos reemplazándolo con uno nuevo, el cual va a diferir del historial de commits que aparece en nuestro repositorio distribuido en el servidor, por lo cual los demás integrantes del proyecto que estén participando van a tener problemas en actualizarse.

Para cambios más drásticos en nuestros commit, como por ejemplo cambiar el mensaje de commits anteriores al último, reordenamiento, borrado o integración de los mismos, necesitamos herramientas de depuración de historial.

## Desmodificar un archivo modificado

**git checkout -- archivo** sirve para tener la ultima versión confirmada (commiteada).
## Desmontar un archivo en etapas con git restore

* **git restore --staged archivo** : se utiliza para deshacer los cambios realizados en el área de preparación (staging area) de Git.

* **git restore archivo :** deshace los cambios realizados en el archivo especificado y lo restaura a la versión más reciente en el repositorio. Esto significa que cualquier cambio no confirmado en el archivo se descarta y se vuelve a la versión previa.