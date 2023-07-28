# Verificar si un arbol binario es un arbol binario full

**Consigna**: Verificar si un arbol es un arbol binario full.

**Concepto**: Para que sea un Full binary tree cada nodo principal intero debe teer dos nodos o 0. En caso de que no lo sea devolver false.

**Solucion**: 

```js

 isBTF(){
        let node = this.root;
        if(this.root === null){
            return true;
        }

        let isBF = function (nodeLeft, nodeRight) {
            if(nodeLeft === null && nodeRight ===null) {
                return true;
            } else if (nodeLeft !== null && nodeRight !== null) {
                let currentLeft = nodeLeft;
                let currentRight = nodeRight;
                return isBF(currentLeft.left, currentLeft.right) && isBF(currentRight.left, currentRight.right);
            } else {
                return false;
            }
        }
        return isBF(node.left, node.right);
      }
```