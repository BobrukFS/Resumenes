# Verificar si un arbol binario es un arbol binario completo

**Consigna**: Verificar si un arbol binario es un arbol binario completo.

**Concepto**:  Todos los niveles del arbol se llenan por completo, excepto los nodos de nivel mas bajo que se llenan desde la izquierda tanto como sea posible. En caso contrario devuelve false;

**Solucion**:

```js
 isBSTC(){
        let node = this.root;
        if(this.root === null){
            return true;
        }

        let isBSC = function (nodeLeft, nodeRight) {
            if(nodeLeft === null && nodeRight === null){
                return true;
            } else if (nodeLeft !== null && nodeRight !== null){
                let currentLeft = nodeLeft;
                let currentRight = nodeRight;
                return isBSC(currentLeft.left, currentLeft.right) && isBSC(currentRight.left, currentRight.right);
            } else if ((nodeLeft !== null && nodeRight ===null) && nodeLeft.left === null){
                if(complete == false){
                    return false;
                }
                complete = false;
                return true;
            } else {
                return false;
            }
        }

        let complete;
        return isBSC(node.left, node.right);
      }
    }
```
