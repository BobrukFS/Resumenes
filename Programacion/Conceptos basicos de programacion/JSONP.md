# JSONP

JSONP, o JSON con Padding, es una técnica JavaScript que permite a los desarrolladores solicitar datos de un dominio diferente al dominio de la página web. Esto se logra utilizando el elemento `<script>` de HTML.

Cuando un navegador carga una página web, descarga todos los recursos de la página, incluidos los archivos JavaScript. Si un archivo JavaScript se solicita desde un dominio diferente al dominio de la página web, el navegador bloqueará la solicitud debido a la política de mismo origen.

La política de mismo origen es una medida de seguridad que impide que los sitios web maliciosos accedan a los datos de otros sitios web. Sin embargo, la política de mismo origen también puede dificultar el desarrollo de aplicaciones web que necesitan acceder a datos de dominios diferentes.

JSONP evita la política de mismo origen utilizando el elemento `<script>`. Cuando un navegador carga un archivo JavaScript, evalúa el código JavaScript del archivo. JSONP aprovecha esto solicitando datos en forma de una llamada a una función JavaScript. El servidor que proporciona los datos devuelve una respuesta JSON, que el navegador evalúa como código JavaScript.

```js
function requestData(callback) { 
	var script = document.createElement('script'); 
	script.src = 'https://api.example.com/data?callback=' + callback;  
	document.body.appendChild(script); 
} 
	
requestData(function(data) { 
		// El código para procesar los datos se puede colocar aquí 
});

//Podemos primero intentar utilizar fetch, y en caso de que no se pueda por las politicas CORS, en el error, utilizamos el codigo de arriba.
```

**Ventajas:**

- JSONP es una forma sencilla de solicitar datos de un dominio diferente al dominio de la página web.
- JSONP es compatible con todos los navegadores modernos.

**Desventajas:**

- JSONP solo permite solicitudes GET.
- JSONP es vulnerable a ataques de inyección de código.