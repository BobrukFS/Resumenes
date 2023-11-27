# API Drag and Drop

Las interfaces de arrastrar y soltar HTML permiten a las aplicaciones web arrastrar y soltar archivos en una página web. Este documento describe cómo una aplicación puede aceptar uno o más archivos que se arrastran desde el administrador de archivos de la plataforma subyacente y se eliminan en una página web.

Los pasos principales para arrastrar y soltar son definir una zona de colocación (dropzone: es decir, un elemento de destino para la eliminación del archivo) y definir handlers de eventos para los eventos de drop y dragover.

```HTML
<div id="dropzone">
	<p>Arrastre sus archivos aqui</p>
</div>
<script>
	var dropzone = document.querySelector("#dropzone");
	dropzone.addEventListener("dragover", e=>{
	 e.preventDefault() 
	 e.stopPropagation()
	}) 
	dropzone.addEventListener("drop", e=>{ 
		e.preventDefault() 
		e.stopPropagation() 
		console.log("Archivo soltado!") 
	})
</script>
```

Los objetos evento de los eventos de tipo drag y drop cuentan con una propiedad llamada **dataTransfer** se usa para contener los datos que se arrastran durante una operación de arrastrar y soltar. Contiene pares clave/valor, donde la clave es el tipo de dato del elemento y el valor es la información de dicho elemento.

**dataTransfer.files** contiene una lista de todos los archivos locales disponibles en la transferencia de datos. Si la operación de arrastre no implica arrastrar archivos, esta propiedad es una lista vacía