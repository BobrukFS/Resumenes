# Estructuras de control en Sass

* **@if :** Controla si se evalua o no un bloque.

* **@each :** Evalua un bloque para cada elemento en una lista o cada par en un mapa.

* **@for :** Evalua un bloque un cierto numero de veces. For se utiliza de dos maneras: "de principio hasta el fin" o "de principio a fin".  La principal diferencia es que el "de principio a fin" excluye el numero final como parte de la cuenta, y "de principio hasta el fin" incluye el numero final como parte de la cuenta. 

* **@While :** Evalua un bloque hasta que se cumple una determinada condicion.

```css
/*@if, @else if, @else*/

@mixin border-stroke ($val) {
  @if $val == light {
    border : 1px solid black;
  } 
  @else if $val == medium {
    border : 3px solid black;
  } 
  @else if $val == heavy {
    border : 6px solid black;
  } 
  @else {
    border : none;
  }
}

/*@each*/

$colors: (color1: blue, color2: red, color3: green);

@each $key, $color in $colors { /*key es necesaria para hacer referencia a las claves en el mapa.*/
  .#{$color}-text {color: $color;}
}

/*resultado*/

.blue-text {
  color: blue;
}

.red-text {
  color: red;
}

.green-text {
  color: green;
}


/*@for*/

/*de principio hasta el fin*/

@for $j from 1 through 5{
  .text-#{$j} {
    font-size : 15 * $j;
  }

/*de principio a fin*/

@for $j from 1 through (5 - 1){
  .text-#{$j} {
    font-size : 15 * $j;
  }

/*while*/

$i: 1;
@while $i < 6 {
  .text-#{$i} {
    font-size : 15px * $i;
  }
  $i : $i + 1;
}


```

