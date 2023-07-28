# Queue en JS

## Formas de implementar un queue en JS

### Mediante arrays  y sus metodos

```js
class Queue {
    constructor(){
        this.items = [];
    }
//Complejidad de tiempo O(1)
    enqueue(item){
        this.items.push(item);
    }
//Complejidad de tiempo O(n)
    dequeue(){
        return this.items.shift();
    }
//Complejidad de tiempo O(º)
    size(){
        return this.items.length;
    }
//Complejidad de tiempo O(1)
    peek(){
        return this.items[0];
    }
//Complejidad de tiempo O(1)
  get printQueue() {
    return this.items;
  }
}
```

### Utilizando un objeto para almacenar los elementos y dos indices

```js
class Queue {
  constructor() {
    this.items = {};
    this.frontIndex = 0;
    this.backIndex = 0;
  }
	//Complejidad de tiempo O(1)
  enqueue(item) {
    this.items[this.backIndex] = item;
    this.backIndex++;
    return item + ' inserted';
  }
//Complejidad de tiempo O(1)
  dequeue() {
    const item = this.items[this.frontIndex];
    delete this.items[this.frontIndex];
    this.frontIndex++;
    return item;
  }
//Complejidad de tiempo O(1)
  peek() {
    return this.items[this.frontIndex];
  }
//Complejidad de tiempo O(1)
  get printQueue() {
    return this.items;
  }
}

```

### Mediante una lista enlazada

```js
class ListNode {
    constructor(data) {
      this.data = data;
      this.next = null;
    }
  }

class Queue {
    constructor(){
        this.front = null;
        this.tail = null;
    }
//Complejidad de tiempo O(1)
    enqueue(item){
        let temp = new ListNode(item);
        if(this.tail == null){
            this.front = this.tail = temp;
            return;
        }
        this.tail.next = temp;
        this.tail = temp;
    }
//Complejidad de tiempo O(1)
    dequeue(){
        if(this.front == null){
            return;
        }
        let temp = this.front;
        this.front = this.front.next;
        if(this.front == null){
            this.tail = null;
        }
        return temp;
    }
}
```

### Queue circular / Buffer circular

```js
class ListNode {
    constructor(data) {
        this.data = data;
        this.next = null;
    }
}

class Queue {
    constructor() {
        this.front = null;
        this.tail = null;
    }

    //Complejidad de tiempo O(1)

    enqueue(item) {
        let temp = new ListNode(item);
        if (this.tail == null) {
            this.front = this.tail = temp;
            this.tail.next = this.front;
            return;
        }

        temp.next = this.tail.next;
        this.tail.next = temp;
        this.tail = temp;

    }

    //Complejidad de tiempo O(1)

    dequeue() {
        if (this.front == null) {
            return;
        }

        let temp = this.front;
        this.front = this.front.next;
        this.tail.next = this.front
        if (this.front == null) {
            this.tail = null;
        }
        return temp;
    }
}
```