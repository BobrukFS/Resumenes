# Caracteristicas basicas de Tailwind

Las directivas `@tailwind` son utilizadas por Tailwind CSS para cargar los estilos CSS necesarios para tu aplicación. Para utilizar las directivas @tailwind hay que incluirlas de la siguiente manera:

```css
@tailwind base; 
@tailwind components; 
@tailwind utilities; 
/* Tus estilos CSS personalizados */
```

La directiva `@tailwind base` carga los estilos CSS básicos de Tailwind CSS. Estos estilos CSS incluyen cosas como el reseteo de estilos, la tipografía predeterminada y los colores predeterminados.

La directiva `@tailwind components` carga los estilos CSS para los componentes de Tailwind CSS. Los componentes de Tailwind CSS son elementos de HTML predefinidos que tienen estilos CSS aplicados. Por ejemplo, el componente `Button` tiene un estilo CSS que le da un aspecto de botón predeterminado.

La directiva `@tailwind utilities` carga los estilos CSS para las utilidades de Tailwind CSS. Las utilidades de Tailwind CSS son clases CSS que se pueden utilizar para personalizar el estilo de los elementos HTML. Por ejemplo, la clase CSS `mt-4` puede utilizarse para agregar un margen superior de 4 píxeles a un elemento HTML.