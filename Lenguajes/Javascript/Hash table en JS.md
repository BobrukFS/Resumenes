# Hash table en JS

## Implementaciones

La mejor forma de implementar una Hash Table en JavaScript depende de tus requisitos y de la complejidad que deseas manejar. Si buscas una solución estándar y fácil de usar, utilizar la clase `Map` es la mejor opción, ya que es una implementación nativa de JavaScript y ofrece una API simple para realizar operaciones básicas en pares clave-valor.

Por otro lado, si deseas una implementación personalizada de una Hash Table, puedes crear tu propia clase `HashTable`. Esto te permitirá controlar y ajustar la implementación de acuerdo a tus necesidades específicas. En este caso, es importante prestar atención a aspectos como el manejo de colisiones, redimensionamiento dinámico y la elección de una función hash adecuada. La implementación personalizada de una Hash Table puede ser más compleja, pero también te brinda más flexibilidad y control sobre el rendimiento y la eficiencia,

### Utilizando el objeto Map

```js
const hashTable = new Map();

priceList.set("apple", 5);
priceList.set("orange",7);
priceList.set("mango", "4 USD");
priceList.get("mango");
priceList.get("orange");
priceList.delete("mango");
priceList.size();
priceList.clear();
```
### Utilizando notacion de objetos

```js
class HashTable {
  constructor(size = 50) {
    this.table = new Array(size);
    this.size = 0;
  }

  _hash(key) {
    let hash = 0;
    for (let i = 0; i < key.length; i++) {
      hash += key.charCodeAt(i);
    }
    return hash % this.table.length;
  }

  set(key, value) {
    let index = this._hash(key);
    while (this.table[index] && this.table[index][0] !== key) {
      index = (index + 1) % this.table.length;
    }
    if (!this.table[index]) {
      this.size++;
    }
    this.table[index] = [key, value];
  }

  get(key) {
    let index = this._hash(key);
    while (this.table[index] && this.table[index][0] !== key) {
      index = (index + 1) % this.table.length;
    }
    return this.table[index] ? this.table[index][1] : undefined;
  }
}

```

## Manejo de colisiones

### Open addresing

### Separate chaining