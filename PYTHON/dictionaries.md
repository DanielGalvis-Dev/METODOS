# 📦 Métodos de Diccionarios en Python

## get()

Devuelve el valor asociado a una clave.
Si la clave no existe, devuelve `None` o un valor por defecto.

```python
persona = {"nombre": "Daniel", "edad": 25}

print(persona.get("nombre"))  # Daniel
print(persona.get("ciudad", "No definida"))
```

---

## keys()

Devuelve una vista con todas las claves del diccionario.

```python
persona = {"nombre": "Ana", "edad": 30}

print(persona.keys())
```

Resultado:

```
dict_keys(['nombre', 'edad'])
```

---

## values()

Devuelve todos los valores del diccionario.

```python
persona = {"nombre": "Ana", "edad": 30}

print(persona.values())
```

---

## items()

Devuelve pares `(clave, valor)` del diccionario.
Es muy útil para recorrer diccionarios.

```python
persona = {"nombre": "Ana", "edad": 30}

for clave, valor in persona.items():
    print(clave, valor)
```

---

## update()

Actualiza el diccionario con nuevos pares clave-valor.

```python
persona = {"nombre": "Luis", "edad": 20}

persona.update({"edad": 21, "ciudad": "Bogotá"})

print(persona)
```

Resultado

```
{'nombre': 'Luis', 'edad': 21, 'ciudad': 'Bogotá'}
```

---

## pop()

Elimina una clave específica y devuelve su valor.

```python
persona = {"nombre": "Carlos", "edad": 28}

edad = persona.pop("edad")

print(edad)      # 28
print(persona)   # {'nombre': 'Carlos'}
```

---

## popitem()

Elimina y devuelve el último par clave-valor insertado.

```python
persona = {"nombre": "Ana", "edad": 25}

item = persona.popitem()

print(item)
```

---

## setdefault()

Devuelve el valor de una clave.
Si no existe, la crea con un valor por defecto.

```python
persona = {"nombre": "Ana"}

persona.setdefault("edad", 20)

print(persona)
```

Resultado

```
{'nombre': 'Ana', 'edad': 20}
```

