# Variables CSS

Para hacer una paleta de variables utilizamos **:root (es una pseudoclase que hace referencia al elemento raiz, es lo mas especifico)**  y para utilizar las variables utilizamos la funcion **var(--nombre).**

![[Pasted image 20221213152602.png]]

Tambien podemos utilizar las variables en cualquier elemento y reasignar otro valor segun mas nos convenga. Por ejemplo:

```css

p {
	--sizeF : 10px;
	font-size: var(--sizeF);
}

@media(min-width : 468px){
	--sizeF : 20px;
	p {
		font-size: var(--sizeF);
	}
}
```

