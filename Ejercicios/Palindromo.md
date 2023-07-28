# Palindromo

**Consigna**: Un palíndromo, también llamado palíndroma o palindroma, es una palabra o frase que se lee igual en un sentido que en otro. Si se trata de numeros en lugar de letras, se llama capicua.

**Concepto**: Primero antes que todo debo convertir mi frase en una cadena de caracteres sin espacios, y otros caracteres que no sean letras. Luego tengo que tener dos punteros (left, right) donde el primero recorra el string de izquierda a derecha y el otro de derecha a izquierda. Si en algun momento el valor al que apunta el puntero left no coincide con el puntero right, la palabra o frase no es un palindromo.

**Solucion**: 

```js
let a = "";

function isPalindrome(string, start = 0, end = string.length - 1) {

    if (a.length === 0) {
        for (let i = 0; i < string.length; i++) {
            if (string[i] !== " " && string[i] !== "," && string[i] !== "." && string[i] !== ":") {
                a += string[i].toLocaleLowerCase();
            }
        }
        end = a.length - 1;
    }

    if(start < end){
        if (a[start] !== a[end]){
            return false;
        } else {
            return isPalindrome(a, start + 1, end - 1);
        }  
    }
    return true;
}
```

