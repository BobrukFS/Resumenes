# Herramientas de ensamblaje


Uno de los beneficios de usar empaquetadores – dan más control sobre cómo se resuelven los módulos, permitiendo módulos simples y mucho más, como los módulos CSS/HTML.

Las herramientas de compilación hacen lo siguiente:

1.  Toman un módulo “principal”, el que se pretende colocar en `<script type="module">` en HTML.
2.  Analiza sus dependencias: las importa y luego importaciones de importaciones etcétera.
3.  Compila un único archivo con todos los módulos (o múltiples archivos, eso es ajustable), reemplazando los llamados nativos de `import` con funciones del empaquetador para que funcione. Los módulos de tipo “Especial” como módulos HTML/CSS también son supported.
4.  Durante el proceso, otras transformaciones y optimizaciones se pueden aplicar:
    -   Se elimina código inaccesible.
    -   Se elimina exportaciones sin utilizar (“tree-shaking”).
    -   Sentencias específicas de desarrollo tales como `console` y `debugger` se eliminan.
    -   La sintaxis JavaScript moderna puede transformarse en una sintaxis más antigua con una funcionalidad similar utilizando [Babel](https://babeljs.io/).
    -   El archivo resultante se minimiza. (se eliminan espacios, las variables se reemplazan con nombres cortos, etc).
-
Si utilizamos herramientas de ensamblaje, entonces, a medida que los scripts se agrupan en un solo archivo (o pocos archivos), las declaraciones `import/export` dentro de esos scripts se reemplazan por funciones especiales de ensamblaje. Por lo tanto, el script “empaquetado” resultante no contiene ninguna `import/export`, no requiere `type="module"`, y podemos ponerla en un script normal:
https://webpack.js.org/concepts/#loaders
[[Webpack]]