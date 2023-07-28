# Mixins en Sass

Un **mixin** es una funcion que nos permite ahorrar lineas de codigo. Pueden utilizar parametros y @content.

Un mixin permite crear grupos de  declaraciones CSS que desea reutilizar en todo su sitio. Para crear un mixin usas la directiva **@mixin** y le das un nombre. Hemos nombrado nuestro mixin theme. También estamos usando la variable  $theme dentro de los paréntesis para que podamos pasar theme lo que queramos. Después de crear su mixin, puede usarlo como una declaración CSS  que comienza con **@include** seguido del nombre del mixin.

![[Pasted image 20230511200020.png]]
Podemos tener un mixin con **varios parametros**, ejemplo:

![[Pasted image 20221214225911.png]]
Tambien podemos ponerles **argumentos default** por si queremos que un valor sea estandar :

![[Pasted image 20221214225931.png]]

Tambien podemos utilizar mixins con la regla **@content** ya que nos permite introducir multiples propiedades css dentro de un mixin, y es muy usado para responsive design.

![[Pasted image 20221214230518.png]]
![[Pasted image 20221214230522.png]]
