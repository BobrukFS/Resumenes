# Etiquetado
Git tiene la capacidad de etiquetar puntos específicos en el historial de un repositorio como importantes. Por lo general, las personas usan esta función para marcar puntos de confirmacion para poderlo identificar o hacer referencia a un problema en especifico ( v1.0, v2.0etc.).
## Listar etiquetas
Simplemente escriba **git tag(**con opcional **-l**  o **--list)** para enumerar las etiquetas:

![[Pasted image 20221224172858.png]]

Este comando enumera las etiquetas en orden alfabético; el orden en que se muestran no tiene importancia real.

También puede buscar etiquetas que coincidan con un patrón en particular. El repositorio fuente de Git, por ejemplo, contiene más de 500 etiquetas. Si solo está interesado en ver la serie 1.8.5, puede ejecutar esto:

![[Pasted image 20221224172915.png]]
## Creacion de etiquetas
Git admite dos tipos de etiquetas: ligeras y anotadas .

Una etiqueta **ligera** es muy parecida a una rama que no cambia: es solo un puntero a una confirmación específica.

Sin embargo, las etiquetas **anotadas** se almacenan como objetos completos en la base de datos de Git. Son sumas de verificación; contener el nombre del etiquetador, correo electrónico y fecha; tener un mensaje de etiquetado; y se puede firmar y verificar con GNU Privacy Guard (GPG). En general, se recomienda que cree etiquetas anotadas para que pueda tener toda esta información; pero si desea una etiqueta temporal o por alguna razón no desea conservar la otra información, también hay disponibles etiquetas ligeras.

**Etiquetas anotadas**

La forma más fácil es especificar **-a** cuándo ejecuta el comando git tag:

![[Pasted image 20221224173016.png]]
El **-m** especifica un mensaje de etiquetado, que se almacena con la etiqueta. Si no especifica un mensaje para una etiqueta anotada, Git inicia su editor para que pueda escribirlo.
Puede ver los datos de la etiqueta junto con la confirmación que se etiquetó con el comando **git show tag:**

![[Pasted image 20221224173039.png]]
Eso muestra la información del etiquetador, la fecha en que se etiquetó la confirmación y el mensaje de anotación antes de mostrar la información de la confirmación.
**Etiquetas ligeras**

Otra forma de etiquetar confirmaciones es con una etiqueta ligera. Esta es básicamente la suma de verificación de confirmación almacenada en un archivo; no se guarda ninguna otra información. Para crear una etiqueta ligera, no proporcione ninguna de las opciones.

![[Pasted image 20221224173118.png]]
**Etiquetado posterior**

También puede etiquetar confirmaciones después de haberlas superado. Supongamos que su historial de confirmación se ve así:

![[Pasted image 20221224173154.png]]
Ahora, suponga que olvidó etiquetar el proyecto en v1.2, que estaba en la confirmación "Actualizar archivo de rake". Puede agregarlo después del hecho. Para etiquetar esa confirmación, especifica la suma de comprobación de la confirmación (o parte de ella) al final del comando:

![[Pasted image 20221224173557.png]]
## Compartir etiquetas
De forma predeterminada, el comando git push no transfiere etiquetas a servidores remotos. Tendrá que enviar etiquetas explícitamente a un servidor compartido después de haberlas creado. Este proceso es como compartir sucursales remotas: puede ejecutar **git push origin tagname**

![[Pasted image 20221224173619.png]]
Si tiene muchas etiquetas que desea empujar hacia arriba a la vez, también puede usar la opción **--tags** del comando git push. Esto transferirá todas sus etiquetas al servidor remoto que aún no están allí. **git push remote --tags** impulsará etiquetas ligeras y anotadas. Actualmente no hay opción para enviar solo etiquetas ligeras, pero si usa **git push remote --follow-tags** solo etiquetas anotadas, se enviarán al control remoto.

![[Pasted image 20221224173644.png]]
## Eliminacion de etiquetas
Para eliminar una etiqueta en su repositorio local, puede usar **git tag -d tagname.** Tenga en cuenta que esto no elimina la etiqueta de ningún servidor remoto. Hay dos variaciones comunes para eliminar una etiqueta de un servidor remoto. La primera variación es **git push remote :refs/tags/tagname**. La segunda (y más intuitiva) forma de eliminar una etiqueta remota es con:

![[Pasted image 20221224173718.png]]
## Echando un vistazo a las etiquetas

Si desea ver las versiones de los archivos a los que apunta una etiqueta, puede hacer una **git checkout** de esa etiqueta.