# Checkear el balance de parentesis

**Consigna**: Dada una cadena de caracteres que comprende solo caracteres de apertura y cierre de parentesis, llaves y corchetes, queremos comprobar el equilibrio.

**Example**:

```js
// () Yes
//[()] Yes
//[(]) No
```

**Concepto**: Cada parentesis, llave y corchete de apertura debe encontrar una contraparte de cierre a su derecha.  Cualquier cosa que se habra ultimo, debe cerrarse primero. A medida que exploramos la expresion de izquierda a derecha, cualquier cierre debe ser para el parentesis, corchetes o llaves no cerrada anteriomente. 

**Solucion**:

```js
function balance(string){
    let list = new Stack();

    for(let i = 0; i < string.length; i++){
        if(string[i] === "(" || string[i] === "[" || string[i] === "{"){
            list.push(string[i]);
        } else {
            if(list.peek() === "(" && string[i] === ")" || list.peek() === "[" && string[i] === "]" || list.peek() === "{" && string[i] === "}" ){
                list.pop();
            } else {
                return false;
            }
        }
    }
    return list.isEmpty();
}
```
