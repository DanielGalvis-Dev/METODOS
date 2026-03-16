
# 📦 Métodos de Listas en Python

## append()

Agrega un elemento al final de la lista.
Modifica directamente la lista original y es uno de los métodos más usados para construir colecciones dinámicamente.

```python
frutas = ["manzana", "banana"]
frutas.append("naranja")

print(frutas)  # ["manzana", "banana", "naranja"]
```

---

## pop()

Elimina y devuelve el último elemento de la lista.
Si se pasa un índice, elimina el elemento en esa posición.

```python
tareas = ["estudiar", "hacer ejercicio", "leer"]
ultima = tareas.pop()

print(ultima)  # "leer"
print(tareas)  # ["estudiar", "hacer ejercicio"]
```

---

## insert()

Inserta un elemento en una posición específica de la lista.
Los elementos posteriores se desplazan hacia la derecha.

```python
numeros = [1, 2, 4]
numeros.insert(2, 3)

print(numeros)  # [1, 2, 3, 4]
```

---

## remove()

Elimina la primera aparición de un valor específico.
Si el valor no existe en la lista, genera un error.

```python
colores = ["rojo", "verde", "azul"]
colores.remove("verde")

print(colores)  # ["rojo", "azul"]
```

---

## extend()

Agrega todos los elementos de otro iterable al final de la lista.
Es útil para combinar listas.

```python
numeros = [1, 2, 3]
numeros.extend([4, 5, 6])

print(numeros)  # [1, 2, 3, 4, 5, 6]
```

---

## index()

Devuelve el índice de la primera aparición de un elemento.
Si no lo encuentra, genera un error.

```python
animales = ["perro", "gato", "pez"]

print(animales.index("gato"))  # 1
```

---

## count()

Cuenta cuántas veces aparece un elemento en la lista.

```python
numeros = [1, 2, 2, 3, 2, 4]

print(numeros.count(2))  # 3
```

---

## sort()

Ordena los elementos de la lista directamente.
Puede ordenarse en forma ascendente o descendente.

```python
numeros = [5, 2, 8, 1]
numeros.sort()

print(numeros)  # [1, 2, 5, 8]
```

Orden descendente:

```python
numeros.sort(reverse=True)
```

---

## reverse()

Invierte el orden de los elementos de la lista.

```python
numeros = [1, 2, 3, 4]
numeros.reverse()

print(numeros)  # [4, 3, 2, 1]
```

---

## clear()

Elimina todos los elementos de la lista.

```python
datos = [1, 2, 3]
datos.clear()

print(datos)  # []
```

---

## copy()

Crea una copia superficial de la lista.

```python
original = [1, 2, 3]
copia = original.copy()

print(copia)  # [1, 2, 3]
```
