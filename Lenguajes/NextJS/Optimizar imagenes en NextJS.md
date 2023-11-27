# Optimizar imagenes en NextJS

Contamos con el componente `<Image/>` que lo que hace es:

- Evitar el cambio de diseño automáticamente cuando se cargan las imágenes.
- Cambiar el tamaño de las imágenes para evitar enviar imágenes grandes a dispositivos con una ventana gráfica más pequeña.
- Carga diferida de imágenes de forma predeterminada (las imágenes se cargan a medida que ingresan a la ventana gráfica).
- Servir imágenes en formatos modernos, como [WebP](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#webp)y [AVIF](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#avif_image), cuando el navegador lo admita.