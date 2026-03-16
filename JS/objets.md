## 📦 Métodos de Objetos en JavaScript

### Object.keys()

Devuelve un arreglo con todas las claves (propiedades enumerables) de un objeto.  
Es útil para recorrer las propiedades o verificar qué atributos contiene.

```js
let obj = { a: 1, b: 2 };
console.log(Object.keys(obj)); // ['a', 'b']
```

---

### Object.values()

Devuelve un arreglo con todos los valores de las propiedades enumerables de un objeto.  
Se usa para acceder directamente a los datos sin importar las claves.

```js
let obj = { a: 1, b: 2 };
console.log(Object.values(obj)); // [1, 2]
```

---

### Object.entries()

Devuelve un arreglo de pares `[clave, valor]` del objeto.  
Es ideal para convertir objetos en estructuras iterables como arrays.

```js
let obj = { a: 1, b: 2 };
console.log(Object.entries(obj)); // [['a', 1], ['b', 2]]
```

---

### Object.assign()

Copia las propiedades de uno o más objetos a un objeto destino.  
Modifica el objeto destino y es útil para combinar configuraciones o clonar objetos superficiales.

```js
let target = { a: 1 };
let source = { b: 2 };
Object.assign(target, source);
console.log(target); // { a: 1, b: 2 }
```

---

### Object.freeze()

Congela un objeto, impidiendo cambios en sus propiedades (no se pueden agregar, eliminar ni modificar).  
Es útil para crear objetos inmutables.

```js
let obj = { a: 1 };
Object.freeze(obj);
obj.a = 2; // No tendrá efecto
console.log(obj); // { a: 1 }
```

---

### Object.seal()

Sella un objeto, impidiendo la adición o eliminación de propiedades, pero permite modificar las existentes.  
Es útil para mantener una estructura fija pero editable.

```js
let obj = { a: 1 };
Object.seal(obj);
obj.a = 2; // Esto funciona
delete obj.a; // No tendrá efecto
console.log(obj); // { a: 2 }
```

---

### Object.getPrototypeOf()

Devuelve el prototipo del objeto, es decir, el objeto del cual hereda propiedades y métodos.  
Se usa para inspeccionar la cadena de herencia.

```js
let proto = {};
let obj = Object.create(proto);
console.log(Object.getPrototypeOf(obj)); // proto
```

---

### Object.setPrototypeOf()

Establece el prototipo de un objeto.  
Permite modificar la herencia, aunque no es recomendado por razones de rendimiento.

```js
let proto = {};
let obj = {};
Object.setPrototypeOf(obj, proto);
```

---

### Object.defineProperty()

Define una nueva propiedad en un objeto con configuraciones específicas (valor, si es escribible, enumerable o configurable).  
Es útil para controlar el comportamiento de las propiedades.

```js
let obj = {};
Object.defineProperty(obj, "a", { value: 1, writable: true });
console.log(obj.a); // 1
```

---

### Object.defineProperties()

Define varias propiedades nuevas en un objeto de una sola vez, con configuraciones detalladas.  
Es útil para inicializar objetos con reglas estrictas.

```js
let obj = {};
Object.defineProperties(obj, {
  a: { value: 1, writable: true },
  b: { value: 2, writable: false },
});
console.log(obj.a, obj.b); // 1, 2
```