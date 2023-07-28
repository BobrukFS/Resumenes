# Clip-path

La propiedad **clip-path** crea una región de recorte que establece qué parte de un elemento debe mostrarse. Se muestran las partes que están dentro de la región, mientras que las que están fuera están ocultas. Los valores pueden ser una url(), circle(), inset(), ellipse(), etc.

Ejemplo:

```CSS
.circle {
	clip-path: circle(50px at 0 100px); /*tamaño at posicion*/
}
```

**Dato**: Hay un elemento HTML que se llama clipPath que sirve para encerrar a los elementos rect, circle, etc que estan dentro de la etiqueta svg.