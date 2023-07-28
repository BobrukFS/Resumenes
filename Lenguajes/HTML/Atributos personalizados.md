# Atributos personalizados

Se puede crear cualquier atributo personalizado que desee agregando el prefijo **data-**. Puede nombrar su atributo cualquier cosa que comience con data- seguido de cualquier serie de caracteres en minusculas.

Las propiedades personalizadas son una forma excelente de comunicar información específica de la aplicación a través de JavaScript. Agregue atributos personalizados a los elementos en forma de `data-name`y acceda a ellos a través del DOM usando `dataset[name]`el elemento en cuestión.

Puede usar `getAttribute()`el nombre de atributo completo o puede aprovechar la propiedad [`dataset`](https://developer.mozilla.org/docs/Web/API/HTMLElement/dataset) para que sea más simple.