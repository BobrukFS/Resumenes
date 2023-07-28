# Caracteristicas basicas de Sass

## Instalar Sass

Para instalar sass podemos utilizar npm en la terminal. Ponemos el comando **npm install -g sass.** Y ejecutamos **sass –version** para poder ver la version.

## Preprocesamiento

Una vez que comience a jugar con Sass, tomará su archivo Sass preprocesado y lo guardará como un archivo CSS (lo compilara) normal que puede usar en su sitio web.

La forma más directa de hacer que esto suceda es en su **terminal**. Deberá decirle a Sass a partir de qué archivo compilar y dónde enviar  el archivo compilado a  CSS. Una forma es ejecutar **sass input.scss (archivo de entrada) output.css (archivo de salida)** desde la terminal.

Tambien podemos utilizar **sass –watch input.scss output.css** para observar los archivos de origen en busca de cambios y vuelva a compilar css cada vez que guarde su sass.

Tambien podemos ver y enviar a directorios usando rutas de carpetas como su entrada y salida, separandolas con dos puntos.

![[Pasted image 20221214220126.png]]

**Dato**: Cada vez que cierro la terminal, hay que devuelta hacer el seguimiento para poder compilar.

## Diferencia entre SASS y SCSS

Sass tiene dos sintaxis: 

* La sintaxis **SCSS.scss ( )** se usa con mayor frecuencia. Es un superconjunto de CSS , lo que significa que todo CSS válido también es SCSS VÁLIDO.  

* La sintaxis con **sangría ( .sass)** es más inusual: usa sangría en lugar de llaves para anidar declaraciones y saltos de línea en lugar de punto y coma para separarlas. 

![[Pasted image 20221214224504.png]]
## ¿Que metodologia utilizar en sass?

Podemos utilizar BEM de esta manera:

![[Pasted image 20221214232726.png]]

Para hacerlo mas rapido, nosotros ya cuando tenemos las clases en HTML podemos generar una hoja de estilos css o scss con una extension que se llama BEM helper, tocando shift control p y poniendo generate stylesheet y seleccionando cual queremos.

## Operadores

Sass permite utilizar operadores matematicos para hacer calculos.

![[Pasted image 20230511200732.png]]