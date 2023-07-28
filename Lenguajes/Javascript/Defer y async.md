# Defer y Async

-   Si no se pone ningún atributo, el navegador empezara a interpretar el HTML, luego se pausara para que se descargue el archivo del script, lo ejecutara y luego seguirá con la interpretación del HTML. Esta opcion no se suele utilizar

-   Si el atributo **async** se declara, el archivo se descargara mientras se interpreta el HTML, al descargarse se pausara la interpretación y se ejecutara el script. Tras la ejecución reanuda la interpretación de HTML. No se garantiza la ejecución de los archivos asíncronos en el mismo orden que aparecen en el documento. Este seria ideal para scripts que manipulan o interaccionan con el DOM antes de DOMContentLoaded (Es un evento que se activa cuando el documento HTML se ha analizado por completo y todos los scripts diferidos se han descargado y ejecutado) y/o que no tienen dependientes con otros scrips

-   Si el atributo **defer** se declara en su lugar, el archivo se descargara mientras se interpreta el HTML, y el script se ejecuta luego de interpretarse completamente el HTML. La ejecución de todos los scripts diferidos se realiza en el mismo orden en el que aparecen en el documento. Es la mejor opcion de forma general.

![](https://cybmeta.com/wp-content/uploads/2018/01/defer-y-async.png)