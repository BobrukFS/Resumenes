
# Eliminacion de archivos
Se puede eliminar un archivo de la carpeta ubicada con **Rm archivo** y luego tenemos que hacer un git add para registrar la eliminación.

Para eliminar un archivo de Git, debe eliminarlo de sus archivos rastreados (más precisamente, eliminarlo de su área de preparación) y luego confirmar. El comando **git rm archivo** hace eso y también elimina el archivo de su directorio de trabajo para que no lo vea como un archivo sin seguimiento la próxima vez.

Si simplemente elimina el archivo de su directorio de trabajo, aparece en el área "Cambios no preparados para confirmación" (es decir, no preparados ).

Otra cosa útil que puede hacer es mantener el archivo en su árbol de trabajo pero eliminarlo de su área de preparación. En otras palabras, es posible que desee mantener el archivo en su disco duro pero que Git no lo rastree nunca más. Esto es particularmente útil si olvidó agregar algo a su .gitignore archivo y accidentalmente lo preparó, como un archivo de registro grande o un montón de .archivos compilados. Para ello, utilice la opción **git rm** **--cached archivo** que lo que hace es remueve el archivo del indice, esto quiere decir, que **Git** ya no le hará seguimiento, es decir estaran untracked. Aunque el archivo seguirá existiendo en tu directorio, tal y como está.

![[Pasted image 20221217225130.png]]
Para eliminar el repositorio .git utilizamos **rm -rf .git** en el directorio donde se encuentra.
