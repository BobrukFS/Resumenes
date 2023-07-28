# Stacks en JS

## Formas de implementar un stack en JS

### Con un array

```js
class Stack {
  constructor() {
    this.items = [];
  }

  push(item) {
    this.items.push(item);
  }

  pop() {
    if (this.items.length === 0) {
      return "Stack vacío";
    }
    return this.items.pop();
  }

  peek() {
    return this.items[this.items.length - 1];
  }

  isEmpty() {
    return this.items.length === 0;
  }

  size() { //Devuelve el tamaño de la pila
    return this.items.length;
  }

  clear() { //Limpia la pila
    this.items = [];
  }

  print(){ //Imprime la pila
	 let str = ""
        for(let i = 0; i < this.items.length; i++){
            str += this.items + " ";
        }
        return str;
  }
}

const myStack = new Stack();
```

### Mediante clase personalizada

```js
class Stack {
  constructor() {
    this.count = 0;
    this.storage = {};
  }

  push(item) {
    this.storage[this.count] = item;
    this.count++;
  }

  pop() {
    if (this.count === 0) {
      return "Stack vacío";
    }
    this.count--;
    const item = this.storage[this.count];
    delete this.storage[this.count]; //No se recomienda utilizar delete para un stack
    return item;
  }

  peek() {
    return this.storage[this.count - 1];
  }

  isEmpty() {
    return this.count === 0;
  }

  size() {
    return this.count;
  }

  clear() {
    this.storage = {};
    this.count = 0;
  }
}

const myStack = new Stack();
```

### Mediante lista enlazada

```js
class ListNode {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}

class LinkedList {
  constructor(head = null) {
    this.head = head;
  }

  getLast() {
    let lastNode = this.head;
    if (lastNode) {
      while (lastNode.next) {
        lastNode = lastNode.next;
      }
    }
    return lastNode;
  }
}

class Stack {
  constructor() {
    this.linkedList = new LinkedList();
  }

  push(item) {
    const newNode = new ListNode(item);
    if (this.linkedList.head === null) {
      this.linkedList.head = newNode;
    } else {
      const lastNode = this.linkedList.getLast();
      lastNode.next = newNode;
    }
  }

  pop() {
    if (this.linkedList.head === null) {
      return "Stack vacío";
    }

    if (this.linkedList.head.next === null) {
      const item = this.linkedList.head.data;
      this.linkedList.head = null;
      return item;
    }

    let previousNode = this.linkedList.head;
    let currentNode = this.linkedList.head.next;
    while (currentNode.next !== null) {
      previousNode = currentNode;
      currentNode = currentNode.next;
    }

    previousNode.next = null;
    return currentNode.data;
  }

  peek() {
    const lastNode = this.linkedList.getLast();
    return lastNode ? lastNode.data : null;
  }

  isEmpty() {
    return this.linkedList.head === null;
  }
}

const myStack = new Stack();
```

