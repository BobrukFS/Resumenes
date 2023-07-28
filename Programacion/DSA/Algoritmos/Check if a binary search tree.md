# Check if a binary search tree

**Consigna**: Verificar si es un arbol de busqueda binario.

**Concepto**: 

**Solucion**: 

```js
    isBST() {
        let isBSTUtil = function(node, min, max) {
        if (node == null) return true;
        if (node.data < min || node.data > max) return false;
        return (
          isBSTUtil(node.left, min, node.data - 1) &&
          isBSTUtil(node.right, node.data + 1, max)
        );
      }    
        return isBSTUtil(this.node, Number.MIN_VALUE, Number.MAX_VALUE);
      }
    }
```