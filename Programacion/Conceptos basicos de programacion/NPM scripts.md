# NPM scripts

Los scripts npm son las estradas en el campo scripts en el archivo package.json. El campo de secuencias de comandos contiene un objeto donde puede especificar varios comandos y secuencias de comandos que desea exponer. Estos se pueden ejecutar usando el siguiente comando:

```shell
npm run script-name
```

Se suele utilizar para minificar CSS y JavaScript, contruir projectos, etc. Los scripts de NPM son versátiles y simples y, al aprender menos herramientas, podemos automatizar tareas en nuestro proyecto web.

Ejemplo:

```package.json
	{
		"name": "example",
		"scripts" : {
			"test" : "echo 'Hola mundo'"
		}
	}
```

Si nosotros ahora ponemos npm run test, se mostrara Hola mundo.

Mas info en https://docs.npmjs.com/cli/v8/using-npm/scripts

### Algunas tareas que se pueden automatizar.

**Tareas CSS:**

- Compilando Sass o Less en CSS.
- Ejecutar Autoprefixer para agregar los prefijos de proveedores que se necesitan.
- Minificación: eliminación de caracteres innecesarios (espacios en blanco, líneas nuevas, comentarios) del código fuente sin comprometer la funcionalidad.
- Concatenación

**Tareas de JavaScript:**

- JSHint: Comprobación del código JavaScript en busca de errores y problemas potenciales (análisis de código estático).
- Concatenación
- Uglificación: minificación + mutilación (reducir las variables locales a letras individuales).
- Recomprobación de errores.

**Proyecto de construcción:**

- Se pueden construir proyectos que consisten en todos los archivos y carpetas requeridos y varias dependencias.
- algunos de los paquetes que se utilizan son rimraf, copyfiles, usemin, cssmin, htmlmin, uglifyjs.

**Compresión de imágenes y sincronización del navegador:**

- Las imágenes se comprimen con imagemin.
- El navegador se procesa automáticamente cuando se realizan cambios usando onchange, watch.