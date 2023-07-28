# Implementacion de un Binary Search Tree

**Consigna**: Implementar un Binary Search Tree

**Concepto**:  El valor de los nodos de la izquierda deben ser menor al del nodo principal. El valor de los nodos de la derecha deben ser mayor al del nodo principal.Todos los nodos de la izquierda deben ser menor al nodo raiz. Todos los nodos de la derecha deben ser mayor al nodo raiz. Ademas ambos subarboles izquierdo y derecho tambien son BST.

## Implementacion en JS

```js 
class Node {
    constructor(data, left = null, right = null) {
        this.data = data;
        this.left = left;
        this.right = right;
    }
}

class BST {
    constructor() {
        this.root = null;
    }

    add(data) {
        const node = this.root;
        if (node === null) {
            this.root = new Node(data);
            return;
        } else {
            const searchTree = function (node) {
                if (data < node.data) {
                    if (node.left === null) {
                        node.left = new Node(data);
                        return;
                    } else if (node.left !== null) {
                        return searchTree(node.left);
                    }
                } else if (data > node.data) {
                    if (node.right === null) {
                        node.right = new Node(data);
                        return;
                    } else if (node.right !== null) {
                        return searchTree(node.right)
                    }

                } else {
                    return null
                }
            };
            return searchTree(node)
        }
    }

    /*
        findMin(){
            const node = this.root;
            if (node === null){
                return;
            } else {
                const searchMin = function(node){
                    if(node.left === null){
                        return node.data;
                    } else {
                        return searchMin(node.left);
                    }
                }
                return searchMin(node);
            }    
        }

        findMax(){
            const node = this.root;
            if (node === null){
                return;
            } else {
                const searchMax = function(node){
                    if(node.right === null){
                        return node.data;
                    } else {
                        return searchMax(node.right);
                    }
                }
                return searchMax(node);
            }
        }
        */

    findMin() {
        let current = this.root;
        while (current.left !== null) {
            current = current.left;
        }
        return current.data;
    }

    findMax() {
        let current = this.root;
        while (current.right !== null) {
            current = current.right;
        }
        return current.data;
    }

    find(data) {
        let current = this.root;
        while (current.data !== data) {
            if (current.data < data) {
                current = current.right;
            } else {
                current = current.left;
            }

            if (current === null) {
                return null;
            }
        }
        return current;
    }

    isPresent(data) {
        let current = this.root;
        while (current.data !== data) {
            if (current.data < data) {
                current = current.right;
            } else {
                current = current.left;
            }
            if (current === null) {
                return false;
            }
        }
        return true;
    }

    //Find min in right or Find max in left.
    
    remove(data) {
        const removeNode = function (node, data) {
            if (node == null) {
                return null;
            }

            if (data == node.data) {
                // Node has no children
                if (node.left == null && node.right == null) {
                    return null;
                }
                //Node has one child
                if (node.left == null) {
                    return node.right;
                }
                //Node has one child
                if (node.right == null) {
                    return node.left;
                }

  

                //Node has two children Find min in right
                let tempNode = node.right;
                while (tempNode.left !== null) {
                    tempNode = tempNode.left;
                }
                node.data = tempNode.data;
                node.right = removeNode(node.right, tempNode.data);
                return node;

                /*//Node has two children Find max in left
                let tempNode = node.left;
                while(tempNode.right !== null){
                    tempNode = tempNode.right;
                }
                node.data = tempNode.data;
                node.left = removeNode(node.left, tempNode.data);
                return node;
                */
            } else if (data < node.data) {
                node.left = removeNode(node.left, data);
                return node;
            } else {
                node.right = removeNode(node.right, data);
                return node;
            }
        }
        this.root = removeNode(this.root, data);
    }
}

  
  

let tree = new BST();
```