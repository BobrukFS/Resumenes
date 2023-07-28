# Anatomia de un documento HTML
Al poner **! + Enter** obtenemos la estructura básica de HTML:

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

</body>
</html>
```

Donde:

* Lo primero en cualquier documento HTML es el preámbulo. Para HTML, todo lo que necesita es **`<!DOCTYPE html>`**. Esto puede parecer un elemento HTML, pero no lo es. Es un tipo especial de nodo llamado "doctype". El doctype le dice al navegador que use el modo estándar. Si se omite, los navegadores utilizarán un modo de representación diferente conocido como [modo peculiar](https://developer.mozilla.org/docs/Web/HTML/Quirks_Mode_and_Standards_Mode).

* El elemento **`HTML`**: Este elemento envuelve todo el contenido de la página. A veces se lo conoce como el **elemento raíz**. El atributo global **lang** participa en la **definición del lenguaje de los elementos**, el lenguaje en que están escritos los elementos no editables o el lenguaje en el cual los elementos editables deberían de estar escritos. Si escribo la pagina en español debe ir **es**.

* El elemento **`<head></head>`**: Este elemento actúa como contenedor para todos los parámetros que desee incluir en el documento HTML que no serán visibles a los visitantes de la página. Este elemento se usa para definir la información necesaria para configurar la página web, como el título, el tipo de codificación de caracteres y los archivos externos requeridos por el documento.

* El elemento **`<body></body>`**: Contiene todo el contenido que quieres mostrar a los usuarios cuando visitan tu página.


## Validacion HTML

Permite validar sus archivos, para detectar si estos efectivamente cumplen con los estandars y para ver el outline si semanticamente los titulos estan bien.

[**https://validator.w3.org/**](https://validator.w3.org/)

