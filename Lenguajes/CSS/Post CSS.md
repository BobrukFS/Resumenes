# Post CSS

## Installar PostCSS

Primero obviamente debemos iniciar nuestro archivo package.json con npm init -y.

Creamos una carpeta para nuestro postCSS y desde la terminal lo instalamos con npm install -D postcss. Una vez instalado debemos configurar el package.json para poder proporcionar un archivo de entrada y otro de salida.

Siempre que querramos correr postCSS tenemos que utilizar npm run build (o el nombre que le pongamos).

Asi quedaria nuestro json con solo instalado postCSS.

```json
{
  "name": "climaapp",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build": "postcss src/css/style.css -o postCss/css/style.min.css --no-map"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "postcss": "^8.4.23"
  }
}
```

Al ejecutar npm run build no va a encontrar el comando. Por lo que debemos ejecutar npm install -D postcss-cli .

## Plugins

Antes que instalar un plugin debemos crear un archivo llamado postcss.config.js donde copiamos y pegamos esto: 

```js
const autoprefixer = require("autoprefixer");
module.exports = {
    plugins: [
        require("autoprefixer"),
    ]
};
```
El plugin Autoprefixer CSS se instala de esta forma: npm install -D autoprefixer. Lo que va a hacer este plugin es poner un prefijo a todos nuestras reglas css para que sean compatibles con otros navegadores.

Podemos utilizar esto creando un archivo browserlistrc y configurandolo, ya que postCSS va a lear dicho archivo y poner los prefijos a partir de este.



Mas info en https://postcss.org/