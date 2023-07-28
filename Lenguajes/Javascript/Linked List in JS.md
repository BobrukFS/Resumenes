# Linked list in JS

En JS a diferencia de otros lenguajes como Java no existe una clase preconstruida de esta estructura de datos, por lo que debemos crear nuestra propia implementacion de la lista enlazada utilizando clases.

```js

class Node {
    constructor(data, next = null) {
        this.data = data;
        this.next = next;
    }
}

class LinkedList {
    constructor() {
        this.head = null;
        this.tail = null;
        this.size = 0;
    }

    //Complexity: O(1)
    // ->[]->[]->[]->[]->[]
    prepend(value) { //Insertar nodo al comienzo
        const newNode = new Node(value, this.head);
        this.head = newNode;
        this.tail = this.tail ? this.tail : newNode;
        this.size++
        return this;
    }

    //Complexity: O(1)
    // ->[]->[]->[]->[]->[]->[]
    append(value) { //Inserta nodo al final
        const newNode = new Node(value, null);
        // Si la lista esta vacia, el nuevo nodo, los punteros head y tail van a apuntar hacia el
        if (!this.head) {
            this.head = newNode;
            this.tail = newNode;
            return;
        }
        //Si la lista no esta vacia:
        this.tail.next = newNode; //Hace que tail apunte al nuevo nodo creado
        this.tail = newNode; //Hace que tail se actualice al nuevo nodo creado
        this.size++
    }

    appendNoTail(value){
        const newNode = new Node(value, null);
        let currentNode;
        if (!this.head){
            this.head = newNode;
        } else {
            currentNode = this.head;
            while(currentNode.next){
                currentNode = currentNode.next
            }
            currentNode.next = newNode;
        }
        this.size++
    }

    insertAt(data, index){
        if (index > 0 && index > this.size){
            return;
        }
        if (index === 0){
            this.prepend(data);
            return;
        }

        const newNode = new Node(data);
        let currentNode, previous;
        currentNode = this.head;
        let count = 0;
        while(count < index){
            previous = currentNode;
            count++;
            currentNode = currentNode.next;
        }
        newNode.next = currentNode;
        previous.next = newNode;
        this.size++;
    }

    getAt(index) {
        let currentNode = this.head;
        let count = 0;
        while(currentNode){
            if (count == index) {
                console.log(currentNode.data);
            }
            count++;
            currentNode = currentNode.next;
        }
        return null;
    }

    //Complexity: O(N)
    traverse() {
        let currentNode = this.head;
        while (currentNode) { //Recorre hasta llegar a null
            currentNode = currentNode.next;
        }
    }

    find(value) {
        let currentNode = this.head;
        while (currentNode) {
            if (currentNode.data === value) {
                return currentNode
            }
            currentNode = currentNode.next;
        }
        return null;
    }

    deleteHead() {
        if (!this.head) {
            return;
        }
        if (this.head.next) {
            this.head = this.head.next;
        } else {
            this.head = null;
            this.tail = null;
        }
        this.size--
    }

    remoteAt(index){
        if (index > 0 && index > this.size){
            return;
        }
        let currentNode = this.head;
        let previous;
        let count = 0;
        if (index === 0){
            this.head = currentNode.next;
        } else {
            while(count < index){
                count++;
                previous = currentNode;
                currentNode = currentNode.next;
            }
            previous.next = currentNode.next;
        }
        this.size--;
    }

    toArray() {
        const items = [];
        let currentNode = this.head;
        while (currentNode) {
            items.push(currentNode.data);
            currentNode = currentNode.next;
        }
        return items;
    }

    printListData(){
        let currentNode = this.head;
        while(currentNode){
            console.log(currentNode.data);
            currentNode = currentNode.next;
        }
    }

    crearList(){
        this.head = null;
        this.tail = null;
        this.size = 0;
    }
}

const list = new LinkedList();
```

