# Estructurar carpetas

Estructurar correctamente los archivos de un sitio web tiene varios beneficios, entre ellos:

1.  Mejora la organización y la legibilidad del código, lo que facilita su mantenimiento y evolución.
    
2.  Facilita la colaboración en equipo, ya que cada miembro del equipo sabe en qué archivos trabajar y cómo están organizados.
    
3.  Permite una carga más rápida del sitio, ya que se pueden utilizar técnicas como la concatenación y la minificación de archivos para reducir su tamaño.
    
4.  Facilita la implementación de herramientas de automatización como Webpack, que pueden ayudar a automatizar tareas como la compilación de CSS y JS, la optimización de imágenes y la generación de archivos de producción.

## Proyecto basico

```markdown
-Sitio web
	-dev or src/
		-index.html
		-about.html
		-contact.html
		-css/
			styles.css
			normalize.css
		-js/
			scripts.js
		-assets/
			images/
			fonts/
	-dist or public
		-index.html
		-css/
			styles.css
		-js/
			scripts.js
		-assets/
			images/
			fonts/
```

Hay que tener dos entornos completamente diferenciados. El primero seria de desarrrollo (dev or src) y el segundo seria el que se sube al servidor (dist o public). Carpeta de desarrollo y carpeta publica o carpeta de distribucion.

* **Src** : Es donde trabajamos, incluimos carpetas de css/scss, js (helpers, modules, index.js), assets(img(tenemos las img sin comprimir), videos, audio).

* **dist or public**: Es donde van los archivos despues que los procesemos. Esto es lo que se sube a nuestro servicio de hoisting.

## Utilizando Sass

```markdown
-Sitio web
	-dev or src/
		-index.html
		-about.html
		-contact.html
		-css/
			styles.css
			normalize.css
		-js/
			scripts.js
		-assets/
			images/
			fonts/
	-scss/
		-main.scss 
		-`_config.scss`
		-`_home.scss`
		-`_menu.scss`
		-`_about.scss`
		-`_contact.scss`
		-`_responsive.scss`
		
	-dist or public
		-index.html
		-css/
			styles.css
		-js/
			scripts.js
		-assets/
			images/
			fonts/
```

En `_config.scss` lo que hacemos es crear nuestras variables, funciones, mixins y resetear nuestro css, utilizando normalize o lo que querramos resetear. En mi opinion me gusta poner normalize.css por separado y linkearlo. En `_responsive.scss` vamos a poner todos nuestras propiedades que hacen que el diseño sean responsivo.

## Utilizando React y vite + Sass

```markdown
-Sitio web

	-index.html
	-dev or src/
		-Components/
			-Header/
				-header.jsx
		-assets/
			images/
			fonts/
	-scss/
		-main.scss 
		-base/
			-`_normalize.scss`
			-`_settings.scss`
		-components/
			-`_header.scss`
		
	-dist or public
		//Cuando ponemos npm run build se crea la carpeta y la estructura
```