# @rules
Las **@rules** brindan instrucciones sobre lo que CSS debe realizar o cómo debe comportarse.

* **@import** importa una hoja de estilo a otra hoja de estilo CSS. Siempre tiene que ir al principio de una hoja de estilos. Se pueden utilizar @import para relacionar hojas de estilos entre hojas de estilos y asi evitar poner muchos `<link>` en el html.

**Dato:** Utilizando @import para cargar una segunda hoja de estilos, la descarga de la segunda hoja de estilo puede no empezar hasta que se haya descargado la primera hoja de estilo. Si, por el contrario, se hace referencia a ambas hojas de estilo en `<link>` ambas se pueden descargar al mismo tiempo. Mbas hojas de estilo siempre se cargan juntas, por lo que es combeniente hacer todo en una misma hoja de estilo, o utilizar `<link>`, ocasionalmente, hay situaciones en las que @import es apropiado.

* **@media**   se utiliza para crear **media queries** . Los media queries usan lógica condicional para aplicar estilos CSS.