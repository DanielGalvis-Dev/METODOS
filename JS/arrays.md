## 📦 Métodos de Arrays en JavaScript

### push()
Agrega uno o más elementos al final del arreglo y devuelve la nueva longitud.  
Modifica directamente el arreglo original, por lo que es útil para construir listas dinámicas.

```js
let frutas = ["manzana", "banana"];
frutas.push("naranja");

console.log(frutas); // ["manzana", "banana", "naranja"]
```

---

### pop()
Elimina el último elemento del arreglo y lo devuelve.  
Si el arreglo está vacío, retorna `undefined`. Es común en estructuras tipo **pila (stack)**.

```js
let tareas = ["estudiar", "hacer ejercicio", "leer"];
let ultima = tareas.pop();

console.log(ultima); // "leer"
console.log(tareas); // ["estudiar", "hacer ejercicio"]
```

---

### shift()
Elimina el primer elemento del arreglo y lo devuelve.  
Modifica el arreglo original y se usa en estructuras tipo **cola (queue)**.

```js
let fila = ["Ana", "Luis", "Carlos"];
let atendido = fila.shift();

console.log(atendido); // "Ana"
console.log(fila); // ["Luis", "Carlos"]
```

---

### unshift()
Agrega uno o más elementos al inicio del arreglo y devuelve la nueva longitud.  
Reorganiza los índices de todos los elementos existentes.

```js
let numeros = [2, 3, 4];
numeros.unshift(1);

console.log(numeros); // [1, 2, 3, 4]
```

---

### splice()
Permite eliminar, reemplazar o insertar elementos en cualquier posición.  
Recibe tres parámetros principales: índice inicial, cantidad de elementos a eliminar y los nuevos elementos a insertar.  
Modifica el arreglo original.

```js
let colores = ["rojo", "verde", "azul"];

// Reemplazar "verde" por "amarillo"
colores.splice(1, 1, "amarillo");

console.log(colores); // ["rojo", "amarillo", "azul"]
```

---

### slice()
Crea una copia parcial del arreglo sin modificar el original.  
Se usa para obtener subarreglos, recibiendo como parámetros el índice inicial y final (no incluido).

```js
let dias = ["lunes", "martes", "miércoles", "jueves"];
let primerosDias = dias.slice(0, 2);

console.log(primerosDias); // ["lunes", "martes"]
console.log(dias); // No cambia
```

---

### indexOf()
Devuelve el índice de la primera aparición de un elemento en el arreglo.  
Si no lo encuentra, retorna `-1`. La comparación es estricta (`===`).

```js
let animales = ["perro", "gato", "pez"];
console.log(animales.indexOf("gato")); // 1
console.log(animales.indexOf("conejo")); // -1
```

---

### forEach()
Ejecuta una función para cada elemento del arreglo.  
No devuelve un nuevo arreglo, solo sirve para recorrer y aplicar operaciones como imprimir o acumular resultados externos.

```js
let precios = [10, 20, 30];

precios.forEach((precio) => {
  console.log(`Precio: $${precio}`);
});
```

---

### map()
Genera un nuevo arreglo aplicando una transformación a cada elemento del original.  
Es ideal para convertir datos sin alterar el arreglo base.

```js
let temperaturasC = [0, 10, 20];
let temperaturasF = temperaturasC.map(c => c * 9/5 + 32);

console.log(temperaturasF); // [32, 50, 68]
```

---

### filter()
Crea un nuevo arreglo con los elementos que cumplen una condición.  
Es útil para seleccionar subconjuntos de datos según criterios definidos.

```js
let edades = [12, 18, 25, 15, 30];
let mayores = edades.filter(edad => edad >= 18);

console.log(mayores); // [18, 25, 30]
```

---

### reduce()
Aplica una función acumuladora sobre los elementos del arreglo para reducirlos a un único valor.  
Se usa para operaciones como suma, producto o concatenación. Recibe un valor inicial opcional.

```js
let compras = [15, 20, 35];
let total = compras.reduce((suma, precio) => suma + precio, 0);

console.log(total); // 70
```

---

### find()
Devuelve el primer elemento que cumple una condición.  
Si no encuentra ninguno, retorna `undefined`. Es útil para búsquedas específicas.

```js
let usuarios = [
  { nombre: "Ana", edad: 17 },
  { nombre: "Luis", edad: 22 }
];

let adulto = usuarios.find(u => u.edad >= 18);

console.log(adulto); // { nombre: "Luis", edad: 22 }
```

---

### findIndex()
Similar a `find()`, pero devuelve el índice del primer elemento que cumple la condición.  
Si no encuentra ninguno, retorna `-1`.

```js
let notas = [3.5, 4.2, 2.8, 4.7];
let indiceAprobado = notas.findIndex(nota => nota >= 3);

console.log(indiceAprobado); // 0
```
