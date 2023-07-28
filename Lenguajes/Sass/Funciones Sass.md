# Funciones Sass

Podemos crear funciones con la regla **@function**.

```css
/*main.scss*/
$colors : (
    "azul" : #38158b;
);

@function getV($color-name){
    @return map-get($colors, $color-name);
}

body {
    background-color : getV(azul);
}

/*main.css*/

body {
  background-color: #38158b;
}
```

La regla **@return** sirve para retornar un valor.