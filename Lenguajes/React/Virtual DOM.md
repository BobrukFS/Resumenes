# Virtual DOM

Un Virtual DOM es un objeto que representa el estado deseado de la interfaz, mientras que el DOM real es un objeto que representa el estado actual de la interfaz. React observa cambios en determinadas variables (props y state) y, al haber un cambio en dichas variables, se busca la mejor forma de llegar al DOM deseado desde el DOM actual a través de un algoritmo denominado DOM Diffing

![[Pasted image 20230924223339.png]]