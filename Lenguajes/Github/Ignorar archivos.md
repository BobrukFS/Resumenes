# Ignorar archivos

A menudo, tendrás una clase de archivos que no deseas que Git agregue automáticamente o que incluso te muestre como sin seguimiento. Por lo general, estos son archivos generados automáticamente, como archivos de registro o archivos producidos por su sistema de compilación. En tales casos, puede crear un archivo **.gitignore** que enumere los patrones para que coincidan con el nombre. Ejemplo:

![[Pasted image 20221223212848.png]]

La primera línea le dice a Git que ignore cualquier archivo que termine en ".o" o ".a": archivos de objetos y archivos que pueden ser el producto de la construcción de su código. La segunda línea le dice a Git que ignore todos los archivos cuyos nombres terminen con una tilde ( ~), que es utilizada por muchos editores de texto como Emacs para marcar archivos temporales.

Otro ejemplo para ignorar archivos html podemos poner **.html y se ignoraran todos los archivos html.

Se puede utilizar esta pagina para crear un archivo .gitignore donde contenga los archivos no deseados.

**https://www.toptal.com/developers/gitignore