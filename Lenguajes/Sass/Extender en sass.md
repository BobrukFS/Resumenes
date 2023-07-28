# Extender en sass
El uso de la regla **@extend** permite compartir un conjunto de propiedad CSS de un selector . Una **clase de marcador de posicion** es un tipo especial de clase que solo se imprime cuando se extiende y puede ayudar a mantener el CSS compilado, ordenado y limpio, para esta clase hay que utilizar **%**.

Ejemplo:

![[Pasted image 20221214231519.png]]
![[Pasted image 20221214231523.png]]
Tambien podemos extender las propiedades de otros selectores.

```scss
  .info{
    width: 200px;
    border: 1px solid black;
    margin: 0 auto;
  }

  .info-important {
    @extend .info;
    background-color : magenta;
  }
```
